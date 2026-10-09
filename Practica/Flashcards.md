# Flashcards de Security+ SY0-701

117 tarjetas agrupadas por tema. Leé la pregunta, respondé en voz alta y recién después abrí la respuesta.

Para estudiarlas con repetición espaciada, importá [`flashcards-anki.tsv`](flashcards-anki.tsv) en Anki: *Archivo > Importar*, separador tabulación, campos Frente / Reverso / Etiquetas.

## Conceptos generales

<details><summary><b>¿Cuáles son las 4 categorías de controles?</b></summary>

Técnicos, gerenciales (administrativos), operativos y físicos.
</details>

<details><summary><b>¿Cuáles son los 6 tipos de controles?</b></summary>

Preventivo, disuasivo, detectivo, correctivo, compensatorio y directivo.
</details>

<details><summary><b>Control compensatorio</b></summary>

Medida alternativa cuando el control principal no es viable (ej.: segmentar un sistema legado sin MFA).
</details>

<details><summary><b>No repudio</b></summary>

Garantía de que alguien no puede negar una acción. Se logra con firmas digitales.
</details>

<details><summary><b>Zero Trust: plano de control</b></summary>

Define y gestiona políticas: identidad adaptativa, reducción del alcance de amenazas, acceso por políticas, zonas seguras.
</details>

<details><summary><b>Zero Trust: Policy Engine vs Policy Administrator vs PEP</b></summary>

PE decide, PA establece/comunica la sesión, PEP aplica la decisión (permite o bloquea).
</details>

<details><summary><b>Gap analysis: pasos</b></summary>

Definir alcance, recolectar datos, analizar, desarrollar plan (POA&M).
</details>

<details><summary><b>Access control vestibule</b></summary>

Dos puertas que no se abren a la vez. Evita tailgating y piggybacking.
</details>

<details><summary><b>Salting</b></summary>

Valor aleatorio agregado a la contraseña antes del hash. Anula rainbow tables.
</details>

<details><summary><b>Key stretching</b></summary>

Aplicar el hash muchas veces (PBKDF2, bcrypt) para hacer lenta la fuerza bruta.
</details>

<details><summary><b>Cifrar para confidencialidad (asimétrico)</b></summary>

Con la clave PÚBLICA del destinatario.
</details>

<details><summary><b>Firmar digitalmente</b></summary>

Hash del mensaje cifrado con la clave PRIVADA del remitente.
</details>

<details><summary><b>Simétrico vs asimétrico</b></summary>

Simétrico: una clave, rápido, problema de distribución (AES). Asimétrico: par de claves, lento, resuelve distribución (RSA, ECC).
</details>

<details><summary><b>Tokenización vs masking</b></summary>

Tokenización reemplaza el dato por un token con mapeo en un vault. Masking oculta parte del dato (****1234).
</details>

<details><summary><b>Esteganografía</b></summary>

Ocultar datos dentro de otro archivo (imagen, audio).
</details>

<details><summary><b>CRL vs OCSP</b></summary>

CRL: lista completa de revocados. OCSP: consulta en tiempo real de un certificado. OCSP stapling: el servidor adjunta la respuesta.
</details>

<details><summary><b>Certificado wildcard</b></summary>

Cubre todos los subdominios de un nivel: *.ejemplo.com.
</details>

## Amenazas y ataques

<details><summary><b>Actor estado-nación</b></summary>

Recursos muy altos, espionaje o sabotaje, persistencia (APT).
</details>

<details><summary><b>Hacktivista</b></summary>

Motivación ideológica o política. Defacement, DDoS, filtraciones.
</details>

<details><summary><b>Shadow IT</b></summary>

Uso de sistemas o servicios sin aprobación de TI.
</details>

<details><summary><b>Smishing / Vishing / Whaling</b></summary>

Phishing por SMS / por voz / dirigido a ejecutivos.
</details>

<details><summary><b>Watering hole</b></summary>

Comprometer un sitio que el grupo objetivo visita habitualmente.
</details>

<details><summary><b>Typosquatting</b></summary>

Registrar dominios con errores de tipeo de uno legítimo.
</details>

<details><summary><b>Pretexting</b></summary>

Inventar un escenario creíble para obtener información.
</details>

<details><summary><b>Virus vs gusano</b></summary>

El virus necesita que el usuario lo ejecute; el gusano se propaga solo por la red.
</details>

<details><summary><b>Troyano</b></summary>

Malware disfrazado de software legítimo. RAT = troyano de acceso remoto.
</details>

<details><summary><b>Rootkit</b></summary>

Malware que se oculta con privilegios elevados (kernel). Difícil de detectar.
</details>

<details><summary><b>Bomba lógica</b></summary>

Código que se activa cuando se cumple una condición (fecha, evento).
</details>

<details><summary><b>Malware fileless</b></summary>

Vive en memoria y abusa de herramientas legítimas (PowerShell). Living off the land.
</details>

<details><summary><b>SQL injection: mitigación</b></summary>

Consultas parametrizadas, validación de entrada, mínimo privilegio en la BD, WAF.
</details>

<details><summary><b>XSS almacenado vs reflejado</b></summary>

Almacenado: queda en el servidor y afecta a todos. Reflejado: viaja en un enlace que la víctima abre.
</details>

<details><summary><b>CSRF</b></summary>

Hace que el navegador autenticado de la víctima envíe una petición no deseada. Mitigación: tokens anti-CSRF.
</details>

<details><summary><b>Buffer overflow</b></summary>

Escribir más datos de los que caben en un buffer para sobrescribir memoria. Mitigación: validar límites, ASLR, DEP.
</details>

<details><summary><b>TOCTOU</b></summary>

Condición de carrera entre la verificación y el uso de un recurso.
</details>

<details><summary><b>Directory traversal</b></summary>

Usar ../ para salir del directorio permitido.
</details>

<details><summary><b>Replay attack</b></summary>

Reenviar una transmisión válida capturada. Mitigación: nonces, timestamps, tokens de un uso.
</details>

<details><summary><b>On-path (MITM)</b></summary>

Interceptar y alterar la comunicación. Mitigación: TLS, VPN, verificar certificados.
</details>

<details><summary><b>Amplificación DNS</b></summary>

Consultas pequeñas con IP falsificada a resolvers abiertos que devuelven respuestas grandes a la víctima.
</details>

<details><summary><b>Password spraying vs fuerza bruta</b></summary>

Spraying: pocas contraseñas contra muchas cuentas. Fuerza bruta: muchas contraseñas contra una cuenta.
</details>

<details><summary><b>Escalada vertical vs horizontal</b></summary>

Vertical: subir a admin/root. Horizontal: acceder a recursos de otro usuario del mismo nivel.
</details>

<details><summary><b>Indicadores de compromiso (IoC)</b></summary>

Viaje imposible, bloqueos de cuenta, consumo inusual de recursos, logs faltantes, accesos concurrentes.
</details>

<details><summary><b>Bluesnarfing vs bluejacking</b></summary>

Bluesnarfing: robo de datos por Bluetooth. Bluejacking: envío de mensajes no solicitados.
</details>

<details><summary><b>Allowlist vs blocklist</b></summary>

Allowlist: sólo lo aprobado se ejecuta (más seguro). Blocklist: se bloquea lo conocido como malo.
</details>

## Arquitectura

<details><summary><b>Responsabilidad compartida en IaaS</b></summary>

Proveedor: físico, red, hipervisor. Cliente: SO, apps, datos, identidades.
</details>

<details><summary><b>VM escape</b></summary>

Salir de una VM para acceder al hipervisor u otras VMs.
</details>

<details><summary><b>SDN: planos</b></summary>

Control (decide), datos (reenvía), gestión (administra).
</details>

<details><summary><b>IaC</b></summary>

Infraestructura definida en código versionado. Consistencia, auditoría, evita configuration drift.
</details>

<details><summary><b>IDS vs IPS</b></summary>

IDS: pasivo, copia del tráfico, alerta. IPS: en línea, bloquea.
</details>

<details><summary><b>NGFW</b></summary>

Firewall de capa 7: identifica aplicaciones, integra IPS e inspección TLS.
</details>

<details><summary><b>WAF</b></summary>

Firewall de aplicaciones web: bloquea SQLi, XSS, etc.
</details>

<details><summary><b>802.1X</b></summary>

Control de acceso por puerto: suplicante, autenticador (switch/AP) y servidor de autenticación (RADIUS).
</details>

<details><summary><b>SASE</b></summary>

SD-WAN + seguridad en la nube (SWG, CASB, ZTNA, FWaaS).
</details>

<details><summary><b>Estados de los datos</b></summary>

En reposo (disco), en tránsito (red), en uso (memoria/CPU).
</details>

<details><summary><b>Soberanía de datos</b></summary>

Los datos quedan sujetos a las leyes del país donde se recolectan o almacenan.
</details>

<details><summary><b>RPO vs RTO</b></summary>

RPO: cuántos datos podés perder (frecuencia de backup). RTO: en cuánto tiempo hay que volver a operar.
</details>

<details><summary><b>Hot / warm / cold site</b></summary>

Hot: listo ya, caro. Warm: equipado, faltan datos. Cold: sólo espacio y energía, barato.
</details>

<details><summary><b>Backup incremental vs diferencial</b></summary>

Incremental: cambios desde el último backup (restaurar: completo + todos los incrementales). Diferencial: cambios desde el último completo (completo + último diferencial).
</details>

<details><summary><b>RAID 0 / 1 / 5 / 6 / 10</b></summary>

0: striping sin redundancia. 1: espejo. 5: paridad, tolera 1 disco (mín. 3). 6: doble paridad, tolera 2. 10: espejo + striping.
</details>

<details><summary><b>ICS/SCADA legado</b></summary>

Segmentar o aislar (air gap) cuando no se puede parchear.
</details>

## Operaciones

<details><summary><b>Factores de autenticación</b></summary>

Algo que sabés, algo que tenés, algo que sos, algún lugar donde estás, algo que hacés.
</details>

<details><summary><b>SAML vs OAuth vs OIDC</b></summary>

SAML: SSO federado con XML. OAuth: autorización delegada con tokens. OIDC: autenticación sobre OAuth.
</details>

<details><summary><b>DAC / MAC / RBAC / ABAC</b></summary>

DAC: decide el dueño. MAC: etiquetas del sistema. RBAC: por rol. ABAC: por atributos (más granular).
</details>

<details><summary><b>PAM</b></summary>

Gestión de cuentas privilegiadas: bóveda de contraseñas, JIT, grabación de sesiones.
</details>

<details><summary><b>WPA3-Enterprise</b></summary>

Autenticación individual vía 802.1X/RADIUS. WPA3 usa SAE en vez de PSK.
</details>

<details><summary><b>SPF / DKIM / DMARC</b></summary>

SPF: servidores autorizados. DKIM: firma del mensaje. DMARC: qué hacer si fallan y reportes.
</details>

<details><summary><b>NAC</b></summary>

Verifica la postura del dispositivo antes de darle acceso a la red.
</details>

<details><summary><b>EDR vs XDR</b></summary>

EDR: detección y respuesta en endpoints. XDR: extiende a red, nube y correo.
</details>

<details><summary><b>Falso positivo vs falso negativo</b></summary>

FP: alerta de algo que no existe. FN: no alerta algo que sí existe (más peligroso).
</details>

<details><summary><b>Escaneo con credenciales</b></summary>

Inicia sesión en el host y da resultados más precisos que un escaneo sin credenciales.
</details>

<details><summary><b>CVE vs CVSS</b></summary>

CVE: identificador de la vulnerabilidad. CVSS: puntaje de severidad 0-10.
</details>

<details><summary><b>SNMPv3</b></summary>

Única versión de SNMP con autenticación y cifrado.
</details>

<details><summary><b>Fases de IR (CompTIA)</b></summary>

Preparación, detección, análisis, contención, erradicación, recuperación, lecciones aprendidas.
</details>

<details><summary><b>Orden de volatilidad</b></summary>

Caché/registros CPU, RAM, estado de red y procesos, disco, logs remotos, backups/medios archivados.
</details>

<details><summary><b>Cadena de custodia</b></summary>

Registro de quién manejó la evidencia, cuándo y para qué.
</details>

<details><summary><b>Legal hold</b></summary>

Obligación de conservar datos relevantes para un litigio.
</details>

<details><summary><b>Threat hunting</b></summary>

Búsqueda proactiva de amenazas a partir de una hipótesis, sin esperar alertas.
</details>

<details><summary><b>Tabletop exercise</b></summary>

Discusión guiada de un escenario, sin tocar sistemas.
</details>

<details><summary><b>SOAR</b></summary>

Orquesta herramientas y automatiza respuestas con playbooks.
</details>

<details><summary><b>SIEM</b></summary>

Agrega, normaliza y correlaciona logs para generar alertas.
</details>

## Gestión del programa

<details><summary><b>SLE</b></summary>

Valor del activo × EF.
</details>

<details><summary><b>ALE</b></summary>

SLE × ARO.
</details>

<details><summary><b>Estrategias de riesgo</b></summary>

Transferir (seguro), aceptar, evitar, mitigar.
</details>

<details><summary><b>Riesgo inherente vs residual</b></summary>

Inherente: antes de los controles. Residual: después de los controles.
</details>

<details><summary><b>Apetito vs tolerancia al riesgo</b></summary>

Apetito: cuánto riesgo se está dispuesto a perseguir. Tolerancia: la variación aceptable alrededor de ese nivel.
</details>

<details><summary><b>Risk register</b></summary>

Lista de riesgos con probabilidad, impacto, dueño y respuesta.
</details>

<details><summary><b>Due diligence vs due care</b></summary>

Diligence: investigar antes de comprometerse. Care: actuar responsablemente después.
</details>

<details><summary><b>SLA / MOU / MSA / SOW / NDA</b></summary>

SLA: niveles de servicio. MOU: intención no vinculante. MSA: contrato marco. SOW: trabajo concreto. NDA: confidencialidad.
</details>

<details><summary><b>Política vs estándar vs procedimiento</b></summary>

Política: qué y por qué. Estándar: requisito obligatorio concreto. Procedimiento: paso a paso.
</details>

<details><summary><b>Controller vs processor (GDPR)</b></summary>

Controller decide fines y medios. Processor trata los datos en su nombre.
</details>

<details><summary><b>Gestión de cambios</b></summary>

Solicitud, análisis de impacto, aprobación del CAB, pruebas, ventana de mantenimiento, plan de backout, documentación.
</details>

<details><summary><b>Certificado de destrucción</b></summary>

Prueba de que los medios se destruyeron correctamente.
</details>

<details><summary><b>Pentest caja blanca / gris / negra</b></summary>

Known / partially known / unknown environment.
</details>

<details><summary><b>Reconocimiento pasivo vs activo</b></summary>

Pasivo: OSINT sin tocar el objetivo. Activo: escaneos e interacción directa.
</details>

<details><summary><b>Rules of Engagement</b></summary>

Alcance, horarios, sistemas incluidos y excluidos, técnicas permitidas de un pentest.
</details>

## Puertos

<details><summary><b>Puerto 21</b></summary>

FTP (TCP)
</details>

<details><summary><b>Puerto 22</b></summary>

SSH, SCP, SFTP (TCP)
</details>

<details><summary><b>Puerto 23</b></summary>

Telnet (TCP)
</details>

<details><summary><b>Puerto 25</b></summary>

SMTP (TCP)
</details>

<details><summary><b>Puerto 53</b></summary>

DNS (TCP/UDP)
</details>

<details><summary><b>Puerto 69</b></summary>

TFTP (UDP)
</details>

<details><summary><b>Puerto 80</b></summary>

HTTP (TCP)
</details>

<details><summary><b>Puerto 88</b></summary>

Kerberos (UDP)
</details>

<details><summary><b>Puerto 110</b></summary>

POP3 (TCP)
</details>

<details><summary><b>Puerto 143</b></summary>

IMAP (TCP)
</details>

<details><summary><b>Puerto 161 / 162</b></summary>

SNMP / SNMP Trap (UDP)
</details>

<details><summary><b>Puerto 389</b></summary>

LDAP (TCP)
</details>

<details><summary><b>Puerto 443</b></summary>

HTTPS (TCP)
</details>

<details><summary><b>Puerto 445</b></summary>

SMB (TCP)
</details>

<details><summary><b>Puerto 465 / 587</b></summary>

SMTPS / envío SMTP (TCP)
</details>

<details><summary><b>Puerto 514</b></summary>

Syslog (UDP)
</details>

<details><summary><b>Puerto 636</b></summary>

LDAPS (TCP)
</details>

<details><summary><b>Puerto 993</b></summary>

IMAPS (TCP)
</details>

<details><summary><b>Puerto 995</b></summary>

POP3S (TCP)
</details>

<details><summary><b>Puerto 1433</b></summary>

Microsoft SQL (TCP)
</details>

<details><summary><b>Puerto 1812 / 1813</b></summary>

RADIUS (UDP)
</details>

<details><summary><b>Puerto 3389</b></summary>

RDP (TCP)
</details>

<details><summary><b>Puerto 6514</b></summary>

Syslog sobre TLS (TCP)
</details>

