# Dominio 2.0: Amenazas, vulnerabilidades y mitigaciones (22%)

20 preguntas de opción múltiple. Intentá responder antes de abrir la solución.

Fuente: secciones 3, 5, 6, 18, 19 y 20 de las notas completas.

---

### 1. Un grupo con financiamiento estatal mantiene acceso silencioso a una red durante meses para robar propiedad intelectual. ¿Qué describe mejor a este actor?

A) Hacktivista
B) Amenaza persistente avanzada (APT) de un estado-nación
C) Atacante sin experiencia (unskilled attacker)
D) Crimen organizado

<details><summary>Ver respuesta</summary>

**Respuesta: B.** Recursos altos, financiamiento estatal, objetivos de espionaje y persistencia a largo plazo son las marcas de un actor estado-nación, típicamente asociado al término APT.

*Sección 3: Nation-state Actor.*
</details>

### 2. Un empleado de marketing contrata un servicio de almacenamiento en la nube sin pasar por TI para compartir archivos con clientes. ¿Cómo se llama esto?

A) Pretexting
B) Supply chain attack
C) Shadow IT
D) Insider threat malicioso

<details><summary>Ver respuesta</summary>

**Respuesta: C.** Shadow IT es el uso de sistemas, servicios o dispositivos sin aprobación del área de TI. No suele ser malicioso, pero amplía la superficie de ataque.

*Sección 3: Shadow IT.*
</details>

### 3. Un atacante llama al help desk haciéndose pasar por un gerente en viaje que "necesita urgente" que le reseteen la contraseña. ¿Qué disparadores motivacionales está usando?

A) Simpatía y reciprocidad
B) Miedo y consenso
C) Autoridad y urgencia
D) Prueba social y escasez

<details><summary>Ver respuesta</summary>

**Respuesta: C.** Hacerse pasar por un superior apela a la autoridad, y el "necesito ya" crea urgencia para que la víctima no siga el procedimiento de verificación.

*Sección 5: Motivational Triggers.*
</details>

### 4. Un usuario recibe un SMS que dice ser de su banco con un enlace para "desbloquear la cuenta". ¿Qué tipo de ataque es?

A) Smishing
B) Whaling
C) Vishing
D) Pharming

<details><summary>Ver respuesta</summary>

**Respuesta: A.** Smishing es phishing por SMS. Vishing es por voz, whaling apunta a ejecutivos y pharming redirige tráfico a sitios falsos (por ejemplo, envenenando DNS).

*Sección 5: Phishing Attacks.*
</details>

### 5. Un atacante compromete un sitio web del sector que suelen visitar los empleados de su objetivo e inyecta malware allí. ¿Qué ataque es?

A) Watering hole
B) Brand impersonation
C) Typosquatting
D) Spear phishing

<details><summary>Ver respuesta</summary>

**Respuesta: A.** En un watering hole el atacante infecta un sitio que el grupo objetivo visita con frecuencia, en lugar de atacarlo directamente.

*Sección 5: Other Social Engineering Attacks.*
</details>

### 6. Un malware se propaga por la red de forma autónoma explotando una vulnerabilidad de SMB, sin que ningún usuario lo ejecute. ¿Qué es?

A) Rootkit
B) Gusano (worm)
C) Virus
D) Troyano

<details><summary>Ver respuesta</summary>

**Respuesta: B.** Los gusanos se replican solos a través de la red. Un virus necesita que el usuario ejecute el archivo infectado; un troyano se disfraza de software legítimo.

*Sección 6: Worms.*
</details>

### 7. Un exempleado dejó código que borraría la base de datos si su usuario se eliminaba del sistema de RR. HH. ¿Qué tipo de malware es?

A) Bomba lógica (logic bomb)
B) Backdoor
C) Bloatware
D) Spyware

<details><summary>Ver respuesta</summary>

**Respuesta: A.** Una bomba lógica se activa cuando se cumple una condición (fecha, evento). Este caso además es una amenaza interna.

*Sección 6: Backdoors and Logic Bombs.*
</details>

### 8. Un análisis detecta malware que se ejecuta sólo en memoria usando PowerShell y no deja archivos en disco. ¿Cómo se llama esta técnica?

A) Malware polimórfico
B) Rootkit de kernel
C) Ransomware
D) Malware sin archivos (fileless)

<details><summary>Ver respuesta</summary>

**Respuesta: D.** El malware fileless vive en memoria y abusa de herramientas legítimas del sistema (living off the land), lo que lo hace difícil de detectar con antivirus basados en firmas.

*Sección 6: Malware Attack Techniques.*
</details>

### 9. Un formulario de login recibe `' OR 1=1 --` en el campo usuario y el atacante entra sin contraseña. ¿Cuál es la mejor mitigación?

A) Usar HTTPS
B) Aumentar la longitud mínima de contraseña
C) Cifrar la base de datos
D) Consultas parametrizadas (prepared statements) y validación de entrada

<details><summary>Ver respuesta</summary>

**Respuesta: D.** Es una inyección SQL. Las consultas parametrizadas separan el código de los datos, así la entrada no se interpreta como SQL. HTTPS cifra el transporte pero no evita la inyección.

*Sección 18: SQL and XML Injections.*
</details>

### 10. Un atacante publica un comentario en un foro con un `<script>` que roba la cookie de sesión de cada usuario que ve la página. ¿Qué ataque es?

A) XSS almacenado (stored/persistent)
B) XSS reflejado
C) CSRF/XSRF
D) Directory traversal

<details><summary>Ver respuesta</summary>

**Respuesta: A.** El script queda guardado en el servidor y se ejecuta para todos los visitantes: es XSS persistente. El reflejado requiere que la víctima haga clic en un enlace manipulado. CSRF hace que el navegador de la víctima envíe una petición no deseada a un sitio donde ya está autenticada.

*Sección 18: XSS and XSRF.*
</details>

### 11. En los logs del servidor web aparece la petición `GET /download?file=../../../../etc/passwd`. ¿Qué ataque se intentó?

A) Replay
B) Directory traversal
C) Buffer overflow
D) Inyección de comandos

<details><summary>Ver respuesta</summary>

**Respuesta: B.** La secuencia `../` intenta salir del directorio permitido para leer archivos del sistema. Se mitiga validando y normalizando rutas.

*Sección 19: Directory Traversal Attack.*
</details>

### 12. Un programa verifica que el usuario tiene permiso sobre un archivo y, en el instante entre la verificación y el uso, el atacante reemplaza el archivo por un enlace simbólico. ¿Qué vulnerabilidad es?

A) Condición de carrera TOC/TOU
B) Integer overflow
C) Memory leak
D) Buffer overflow

<details><summary>Ver respuesta</summary>

**Respuesta: A.** Time-of-check to time-of-use (TOCTOU) es una condición de carrera: el estado cambia entre que se verifica y se usa.

*Sección 18: Race Conditions.*
</details>

### 13. Un atacante captura un paquete de autenticación válido y lo reenvía más tarde para obtener acceso. ¿Qué control lo previene mejor?

A) Antivirus
B) RAID 1
C) Firewall de capa 3
D) Tokens de sesión con marca de tiempo y nonces

<details><summary>Ver respuesta</summary>

**Respuesta: D.** Es un ataque de repetición (replay). Los nonces, marcas de tiempo y tokens de un solo uso (como en Kerberos) invalidan mensajes reenviados.

*Sección 19: Replay Attacks.*
</details>

### 14. Muchos equipos de la red interna empiezan a resolver el dominio del banco a una IP desconocida. Sólo pasa dentro de la empresa. ¿Qué ataque es más probable?

A) Session hijacking
B) Bluejacking
C) Envenenamiento de caché DNS (DNS cache poisoning)
D) DDoS amplificado

<details><summary>Ver respuesta</summary>

**Respuesta: C.** El servidor DNS interno tiene registros falsos en caché. DNSSEC ayuda a validar respuestas firmadas.

*Sección 19: Domain Name System (DNS) Attacks.*
</details>

### 15. Un servidor recibe miles de respuestas DNS grandes que nunca solicitó, provenientes de resolvers abiertos. ¿Qué ataque es?

A) DNS tunneling
B) Domain hijacking
C) SYN flood
D) Ataque de amplificación DNS (DDoS reflejado)

<details><summary>Ver respuesta</summary>

**Respuesta: D.** El atacante falsifica la IP de la víctima en consultas pequeñas a resolvers abiertos, que responden con paquetes grandes hacia la víctima.

*Sección 19: Distributed Denial of Service.*
</details>

### 16. Durante una investigación se encuentran viajes imposibles (logins desde Buenos Aires y Tokio con 10 minutos de diferencia) para la misma cuenta. ¿Qué es esto?

A) Una vulnerabilidad de día cero
B) Un indicador de compromiso (IoC)
C) Un control compensatorio
D) Un falso positivo de antivirus

<details><summary>Ver respuesta</summary>

**Respuesta: B.** El viaje imposible (impossible travel) es un IoC clásico de credenciales comprometidas. Otros IoC: bloqueos de cuenta, consumo de recursos inusual, logs faltantes, accesos concurrentes.

*Sección 19: Indicators of Compromise (IoC).*
</details>

### 17. Un usuario sin privilegios explota una falla del kernel y obtiene permisos de root. ¿Qué tipo de ataque es?

A) Escalada horizontal de privilegios
B) Pivoting
C) Movimiento lateral
D) Escalada vertical de privilegios

<details><summary>Ver respuesta</summary>

**Respuesta: D.** La escalada vertical sube de nivel (usuario a admin/root). La horizontal accede a recursos de otro usuario del mismo nivel.

*Sección 19: Execution and Escalation Attacks.*
</details>

### 18. ¿Cuál es la primera medida de hardening al instalar un nuevo router o cámara IP?

A) Instalar un antivirus
B) Habilitar Telnet para administración remota
C) Cambiar las credenciales por defecto y deshabilitar servicios innecesarios
D) Abrir todos los puertos para probar conectividad

<details><summary>Ver respuesta</summary>

**Respuesta: C.** Las credenciales por defecto son públicas y muy explotadas. Cambiarlas, deshabilitar servicios y puertos que no se usan y actualizar el firmware son la base del hardening.

*Sección 20: Changing Default Configurations.*
</details>

### 19. Una empresa quiere que sólo se ejecuten aplicaciones aprobadas en las estaciones de trabajo de contabilidad. ¿Qué control debe usar?

A) Sandboxing
B) Lista de permitidos (allowlist / application whitelisting)
C) DLP
D) Lista de bloqueo (blocklist)

<details><summary>Ver respuesta</summary>

**Respuesta: B.** El allowlisting bloquea todo excepto lo aprobado explícitamente. Es más restrictivo y seguro que una blocklist, que sólo bloquea lo conocido como malo.

*Sección 20: Restricting Applications.*
</details>

### 20. Un atacante en una cafetería se ubica entre la víctima y el punto de acceso para leer y modificar el tráfico. ¿Qué ataque es y qué lo mitiga?

A) Bluesnarfing; desactivar Bluetooth
B) DDoS; usar un CDN
C) On-path; usar VPN o TLS de extremo a extremo
D) Phishing; capacitación de usuarios

<details><summary>Ver respuesta</summary>

**Respuesta: C.** Un ataque on-path (antes man-in-the-middle) intercepta la comunicación, por ejemplo con un evil twin o ARP poisoning. El cifrado de extremo a extremo (VPN, TLS) evita que pueda leer o alterar los datos.

*Sección 19: On-path Attacks.*
</details>
