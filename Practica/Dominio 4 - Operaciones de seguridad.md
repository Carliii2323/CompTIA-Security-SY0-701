# Dominio 4.0: Operaciones de seguridad (28%)

24 preguntas de opción múltiple. Es el dominio con más peso, así que vale la pena repasarlo dos veces.

Fuente: secciones 17 y 21 a 26 de las notas completas.

---

### 1. Un usuario inicia sesión con contraseña y un código de una app de autenticación en el celular. ¿Qué factores usa?

A) Algo que sabés + algo que tenés
B) Algo que tenés + algún lugar donde estás
C) Dos factores de "algo que sabés"
D) Algo que sabés + algo que sos

<details><summary>Ver respuesta</summary>

**Respuesta: A.** La contraseña es conocimiento y el celular con el TOTP es posesión. Contraseña más PIN serían dos factores del mismo tipo, así que no sería MFA real.

*Sección 17: Multi-factor Authentication.*
</details>

### 2. Los empleados acceden a varias aplicaciones SaaS con una sola autenticación contra el proveedor de identidad de la empresa, usando aserciones XML. ¿Qué estándar se usa?

A) LDAP
B) Kerberos
C) SAML
D) TACACS+

<details><summary>Ver respuesta</summary>

**Respuesta: C.** SAML intercambia aserciones XML entre el IdP y el proveedor de servicio (SP) para SSO federado en la web. OAuth autoriza acceso delegado y OpenID Connect agrega autenticación sobre OAuth.

*Sección 17: Single Sign-On (SSO) / Federation.*
</details>

### 3. Una app pide permiso para leer tus contactos de Google sin conocer tu contraseña. ¿Qué protocolo se usa normalmente?

A) RADIUS
B) SAML
C) OAuth 2.0
D) NTLM

<details><summary>Ver respuesta</summary>

**Respuesta: C.** OAuth es un marco de autorización: entrega un token de acceso con permisos limitados sin compartir credenciales.

*Sección 17: Single Sign-On (SSO).*
</details>

### 4. En un sistema militar, el acceso se decide comparando la etiqueta de clasificación del dato (Secreto) con la autorización del usuario, y el usuario no puede cambiarla. ¿Qué modelo de control de acceso es?

A) ABAC
B) DAC
C) RBAC
D) MAC

<details><summary>Ver respuesta</summary>

**Respuesta: D.** En el control de acceso obligatorio (MAC) las etiquetas las define el sistema o administrador. En DAC el dueño del recurso decide los permisos.

*Sección 17: Access Control Models.*
</details>

### 5. Una política permite acceder a la nómina sólo si el usuario es de RR. HH., usa un equipo corporativo y está en horario laboral. ¿Qué modelo es?

A) RBAC
B) DAC
C) Rule-based por ACL de router
D) ABAC (basado en atributos)

<details><summary>Ver respuesta</summary>

**Respuesta: D.** ABAC evalúa múltiples atributos (usuario, recurso, entorno, hora, dispositivo). Es el más granular.

*Sección 17: Access Control Models.*
</details>

### 6. Los administradores reciben credenciales de dominio que sólo valen por 1 hora y cuyo uso queda grabado. ¿Qué solución lo implementa?

A) SSO
B) PAM con acceso just-in-time (JIT)
C) Password manager personal
D) Federación

<details><summary>Ver respuesta</summary>

**Respuesta: B.** Privileged Access Management controla las cuentas privilegiadas con permisos temporales (JIT), bóveda de contraseñas y registro de sesiones.

*Sección 17: Privileged Access Management (PAM).*
</details>

### 7. Un atacante prueba la contraseña "Primavera2026!" contra cientos de cuentas distintas para evitar bloqueos. ¿Qué ataque es?

A) Password spraying
B) Diccionario contra una cuenta
C) Fuerza bruta
D) Rainbow table

<details><summary>Ver respuesta</summary>

**Respuesta: A.** El spraying usa pocas contraseñas comunes contra muchas cuentas, evitando el umbral de bloqueo de cada una.

*Sección 17: Password Attacks.*
</details>

### 8. ¿Qué configuración inalámbrica ofrece la mayor seguridad para una red corporativa?

A) WEP con clave de 128 bits
B) WPA2-Personal con PSK
C) Red abierta con portal cautivo
D) WPA3-Enterprise con 802.1X/RADIUS

<details><summary>Ver respuesta</summary>

**Respuesta: D.** WPA3-Enterprise autentica a cada usuario individualmente vía RADIUS y usa cifrado más fuerte. WEP está roto; PSK comparte una sola clave entre todos.

*Sección 21: Wireless Security Settings.*
</details>

### 9. ¿Qué registros DNS permiten que el servidor de correo receptor verifique que un email proviene de un servidor autorizado y no fue alterado, y qué hacer si falla?

A) MX, NS y SOA
B) PTR, TXT y SRV
C) A, AAAA y CNAME
D) SPF, DKIM y DMARC

<details><summary>Ver respuesta</summary>

**Respuesta: D.** SPF lista los servidores autorizados, DKIM firma digitalmente el mensaje y DMARC define la política (rechazar, cuarentena) y los reportes.

*Sección 21: Email Security.*
</details>

### 10. Una laptop se conecta a la red y queda en una VLAN de remediación porque su antivirus está desactualizado. ¿Qué solución hizo esto?

A) NAC
B) DLP
C) WAF
D) SIEM

<details><summary>Ver respuesta</summary>

**Respuesta: A.** Network Access Control verifica la postura (parches, antivirus, configuración) antes de dar acceso a la red. Puede funcionar con agente persistente, agente temporal (dissolvable) o sin agente (agentless).

*Sección 21: Network Access Control (NAC).*
</details>

### 11. ¿Qué herramienta en el endpoint registra procesos, conexiones y cambios de archivos, y permite aislar el equipo de forma remota?

A) EDR
B) Firewall de red
C) Antivirus basado en firmas
D) HIDS solamente

<details><summary>Ver respuesta</summary>

**Respuesta: A.** Endpoint Detection and Response monitorea comportamiento continuo, permite investigar y responder (aislar, matar procesos). XDR extiende esto a red, nube y email.

*Sección 21: Endpoint Detection and Response.*
</details>

### 12. ¿Qué protocolo seguro debería reemplazar a Telnet para administración remota de switches?

A) FTP
B) SNMPv1
C) SSH
D) HTTP

<details><summary>Ver respuesta</summary>

**Respuesta: C.** SSH (puerto 22) cifra la sesión. Telnet (puerto 23) envía todo en texto claro, incluidas las credenciales.

*Sección 21: Selecting Secure Protocols.*
</details>

### 13. Un escáner de vulnerabilidades reporta una falla crítica, pero al revisar el servidor se comprueba que el parche ya está instalado. ¿Qué es este resultado?

A) Falso negativo
B) Falso positivo
C) Verdadero negativo
D) Verdadero positivo

<details><summary>Ver respuesta</summary>

**Respuesta: B.** Se reportó algo que no existe. El falso negativo, más peligroso, es cuando existe la vulnerabilidad y el escáner no la reporta.

*Sección 22: Analyzing Vulnerabilities.*
</details>

### 14. ¿Qué tipo de escaneo de vulnerabilidades da resultados más precisos sobre parches y configuración local?

A) Escaneo sin credenciales
B) Escaneo pasivo de tráfico
C) Escaneo con credenciales (credentialed)
D) Escaneo de puertos con ping

<details><summary>Ver respuesta</summary>

**Respuesta: C.** Con credenciales el escáner puede iniciar sesión y revisar versiones, registro y configuración, reduciendo falsos positivos.

*Sección 22: Identifying Vulnerabilities.*
</details>

### 15. ¿Qué sistema estandariza la puntuación de severidad de vulnerabilidades del 0 al 10?

A) CVE
B) CVSS
C) STIX
D) SCAP

<details><summary>Ver respuesta</summary>

**Respuesta: B.** CVSS (Common Vulnerability Scoring System) puntúa severidad. CVE es el identificador único de cada vulnerabilidad.

*Sección 22: Analyzing Vulnerabilities.*
</details>

### 16. Después de aplicar un parche, ¿cuál es el paso correcto para validar la remediación?

A) Volver a escanear (rescan) y verificar
B) Notificar a los clientes
C) Desactivar el escáner
D) Cerrar el ticket sin más

<details><summary>Ver respuesta</summary>

**Respuesta: A.** La validación incluye re-escanear, auditar y verificar que la vulnerabilidad ya no aparece.

*Sección 22: Validating Vulnerability Remediation.*
</details>

### 17. ¿Qué herramienta centraliza y correlaciona logs de firewalls, servidores y endpoints para generar alertas?

A) HSM
B) SIEM
C) NAC
D) DLP

<details><summary>Ver respuesta</summary>

**Respuesta: B.** El SIEM agrega, normaliza y correlaciona eventos de múltiples fuentes y genera alertas y reportes.

*Sección 23: Security Information and Event Management (SIEM).*
</details>

### 18. ¿Qué versión de SNMP debería usarse porque agrega autenticación y cifrado?

A) Ninguna, SNMP no admite cifrado
B) SNMPv3
C) SNMPv1
D) SNMPv2c

<details><summary>Ver respuesta</summary>

**Respuesta: B.** SNMPv1 y v2c usan community strings en texto claro. SNMPv3 incorpora integridad, autenticación y cifrado.

*Sección 23: Simple Network Management Protocol (SNMP).*
</details>

### 19. Según el modelo de 7 fases de CompTIA, ¿qué fase sigue inmediatamente a la contención?

A) Lecciones aprendidas
B) Erradicación
C) Análisis
D) Recuperación

<details><summary>Ver respuesta</summary>

**Respuesta: B.** Preparación, detección, análisis, contención, erradicación, recuperación y actividad posterior al incidente (lecciones aprendidas).

*Sección 24: Incident Response Process.*
</details>

### 20. Un analista busca proactivamente señales de un atacante en la red aunque ninguna alerta se haya disparado. ¿Qué actividad realiza?

A) Gap analysis
B) Tabletop exercise
C) Threat hunting
D) Pentesting

<details><summary>Ver respuesta</summary>

**Respuesta: C.** El threat hunting parte de una hipótesis y busca amenazas que evadieron las defensas automáticas.

*Sección 24: Threat Hunting.*
</details>

### 21. El equipo reúne a los responsables en una sala para recorrer verbalmente un escenario de ransomware sin tocar sistemas. ¿Qué tipo de prueba es?

A) Failover real
B) Simulación completa
C) Prueba en paralelo
D) Ejercicio de mesa (tabletop)

<details><summary>Ver respuesta</summary>

**Respuesta: D.** El tabletop es una discusión guiada del plan, de bajo costo y sin impacto en producción.

*Sección 24: Incident Response Training and Testing.*
</details>

### 22. Al recolectar evidencia de un equipo comprometido, ¿en qué orden de volatilidad se debe capturar?

A) El orden no importa si se hace un hash
B) Backups, disco, RAM, caché
C) Caché/registros de CPU, RAM, disco, backups/archivos
D) Disco duro, RAM, caché de CPU, backups

<details><summary>Ver respuesta</summary>

**Respuesta: C.** Se recolecta primero lo más volátil (registros y caché de CPU, RAM, tablas de ruteo, procesos) y al final lo más persistente (disco, backups, medios archivados).

*Sección 24: Digital Forensic Procedures.*
</details>

### 23. ¿Qué documento registra quién manipuló la evidencia, cuándo y para qué, de modo que sea admisible en un juicio?

A) Legal hold
B) SLA
C) After-action report
D) Cadena de custodia (chain of custody)

<details><summary>Ver respuesta</summary>

**Respuesta: D.** La cadena de custodia documenta cada transferencia y acceso a la evidencia. El legal hold obliga a conservar datos ante un litigio.

*Sección 24: Digital Forensic Procedures.*
</details>

### 24. Un SOC quiere que, ante una alerta de phishing, se enriquezca la URL con threat intel, se bloquee el remitente y se abra un ticket automáticamente. ¿Qué tecnología lo hace?

A) SOAR
B) SAML
C) SASE
D) SCADA

<details><summary>Ver respuesta</summary>

**Respuesta: A.** SOAR (Security Orchestration, Automation and Response) ejecuta playbooks automatizados que integran varias herramientas por API.

*Sección 26: Automating Security / Integrations and APIs.*
</details>
