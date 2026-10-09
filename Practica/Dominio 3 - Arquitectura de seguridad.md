# Dominio 3.0: Arquitectura de seguridad (18%)

16 preguntas de opción múltiple. Intentá responder antes de abrir la solución.

Fuente: secciones 7, 14, 15 y 16 de las notas completas.

---

### 1. En el modelo de responsabilidad compartida de una nube IaaS, ¿quién es responsable de parchear el sistema operativo de las máquinas virtuales?

A) El proveedor de nube
B) Ambos por igual
C) El cliente
D) El fabricante del hardware

<details><summary>Ver respuesta</summary>

**Respuesta: C.** En IaaS el proveedor cuida la infraestructura física, la red y el hipervisor; el cliente administra el SO, las aplicaciones y los datos. En SaaS, en cambio, el proveedor parchea casi todo.

*Sección 15: Cloud Security.*
</details>

### 2. Un equipo define la infraestructura de red y servidores en archivos de configuración versionados en Git. ¿Qué concepto es y cuál es un beneficio de seguridad?

A) Infraestructura como código (IaC); despliegues consistentes y auditables
B) Serverless; no hay servidores que administrar
C) Microservicios; aislamiento de fallas
D) SDN; separa plano de control y de datos

<details><summary>Ver respuesta</summary>

**Respuesta: A.** IaC permite desplegar entornos idénticos, revisar cambios como código y evitar la deriva de configuración (configuration drift).

*Sección 15: Infrastructure as Code (IaC).*
</details>

### 3. Un atacante logra salir de una máquina virtual y acceder al hipervisor y a otras VMs del mismo host. ¿Cómo se llama esto?

A) VM sprawl
B) Container breakout por namespace
C) Resource reuse
D) VM escape

<details><summary>Ver respuesta</summary>

**Respuesta: D.** VM escape rompe el aislamiento entre la VM y el hipervisor. VM sprawl es la proliferación de VMs sin control.

*Sección 15: Virtualization and Containerization.*
</details>

### 4. ¿Qué tecnología separa el plano de control del plano de datos para administrar la red de forma centralizada y programable?

A) VLAN
B) SDN (Software-defined Network)
C) NAT
D) SD-WAN

<details><summary>Ver respuesta</summary>

**Respuesta: B.** SDN divide la red en plano de control (decide), plano de datos (reenvía) y plano de gestión.

*Sección 15: Software-defined Network (SDN).*
</details>

### 5. Una planta industrial usa sistemas SCADA con software antiguo que no se puede parchear. ¿Cuál es la mejor protección?

A) Segmentar la red y aislarlos (air gap o red separada con controles estrictos)
B) Instalar antivirus en cada PLC
C) Migrarlos a la nube pública
D) Conectarlos directamente a Internet para recibir actualizaciones

<details><summary>Ver respuesta</summary>

**Respuesta: A.** Los sistemas ICS/SCADA suelen ser legados y críticos. La segmentación o el aislamiento reducen la exposición cuando parchear no es posible.

*Sección 15: ICS and SCADA.*
</details>

### 6. Un firewall que inspecciona el contenido de la aplicación, identifica qué aplicación genera el tráfico y puede integrar IPS es un:

A) Next-Generation Firewall (NGFW)
B) Proxy inverso
C) Firewall de filtrado de paquetes
D) Firewall stateful de capa 4

<details><summary>Ver respuesta</summary>

**Respuesta: A.** El NGFW trabaja hasta capa 7, reconoce aplicaciones y suele incluir IPS, inspección TLS y filtrado por usuario.

*Sección 16: Firewalls.*
</details>

### 7. Un sensor colocado en línea que bloquea automáticamente tráfico malicioso es un ______; uno que sólo alerta a partir de una copia del tráfico es un ______.

A) WAF / NAC
B) IPS / IDS
C) IDS / IPS
D) SIEM / EDR

<details><summary>Ver respuesta</summary>

**Respuesta: B.** El IPS está en línea (inline) y puede bloquear. El IDS recibe una copia (por ejemplo, de un SPAN o TAP) y sólo detecta y alerta.

*Sección 16: IDS and IPS.*
</details>

### 8. ¿Qué dispositivo debería colocarse delante de una aplicación web para filtrar ataques como SQLi y XSS?

A) Proxy forward
B) Balanceador de carga sin reglas
C) Jump server
D) WAF (Web Application Firewall)

<details><summary>Ver respuesta</summary>

**Respuesta: D.** El WAF inspecciona tráfico HTTP/HTTPS y bloquea patrones de ataque contra aplicaciones web.

*Sección 16: Network Appliances.*
</details>

### 9. Una empresa con muchas sucursales y empleados remotos quiere combinar SD-WAN con servicios de seguridad entregados desde la nube (SWG, CASB, ZTNA, FWaaS). ¿Qué modelo es?

A) SOAR
B) SIEM
C) SCADA
D) SASE

<details><summary>Ver respuesta</summary>

**Respuesta: D.** SASE (Secure Access Service Edge) une conectividad de red y seguridad como servicio en la nube.

*Sección 16: SD-WAN and SASE.*
</details>

### 10. ¿Qué protocolo de seguridad para switches evita que un dispositivo no autorizado se conecte a un puerto, exigiendo autenticación contra un servidor RADIUS?

A) ARP
B) SNMPv1
C) 802.1X
D) STP

<details><summary>Ver respuesta</summary>

**Respuesta: C.** 802.1X es control de acceso a red basado en puertos: el suplicante se autentica a través del autenticador (switch o AP) contra un servidor RADIUS.

*Sección 16: Port Security.*
</details>

### 11. ¿En qué estado se encuentran los datos que se están procesando en la memoria RAM de un servidor?

A) En reposo (at rest)
B) Archivados
C) En uso (in use)
D) En tránsito (in transit)

<details><summary>Ver respuesta</summary>

**Respuesta: C.** Datos en uso son los que se procesan en memoria o CPU. En reposo están almacenados en disco; en tránsito viajan por la red.

*Sección 7: Data States.*
</details>

### 12. Una ley exige que los datos de ciudadanos de un país se almacenen y procesen dentro de sus fronteras. ¿Qué concepto es?

A) Clasificación de datos
B) Soberanía de datos (data sovereignty)
C) Retención de datos
D) Minimización de datos

<details><summary>Ver respuesta</summary>

**Respuesta: B.** La soberanía de datos indica que los datos están sujetos a las leyes del país donde se recolectan o almacenan (por ejemplo, el GDPR en la UE).

*Sección 7: Data Sovereignty.*
</details>

### 13. El negocio tolera perder como máximo 4 horas de datos y necesita volver a operar en 8 horas. ¿Qué métricas representan esos valores?

A) RPO = 4 h, RTO = 8 h
B) SLE = 4 h, ALE = 8 h
C) RTO = 4 h, RPO = 8 h
D) MTBF = 4 h, MTTR = 8 h

<details><summary>Ver respuesta</summary>

**Respuesta: A.** El RPO (Recovery Point Objective) es cuánta pérdida de datos se tolera, y define la frecuencia de backup. El RTO (Recovery Time Objective) es en cuánto tiempo hay que restaurar el servicio.

*Sección 14: Data Backups / Cyber Resilience.*
</details>

### 14. ¿Qué tipo de sitio alternativo tiene hardware, software y datos casi en tiempo real, listo para operar de inmediato, pero es el más caro?

A) Cold site
B) Mobile site
C) Warm site
D) Hot site

<details><summary>Ver respuesta</summary>

**Respuesta: D.** El hot site está totalmente equipado y replicado. El warm tiene equipamiento pero requiere cargar datos; el cold es sólo espacio y energía.

*Sección 14: Redundant Site Considerations.*
</details>

### 15. Un backup completo se hace el domingo. ¿Qué tipo de backup diario copia todo lo cambiado desde el último completo, de modo que para restaurar sólo se necesitan el completo y el último de ese tipo?

A) Incremental
B) Copia espejo
C) Diferencial
D) Snapshot

<details><summary>Ver respuesta</summary>

**Respuesta: C.** El diferencial acumula los cambios desde el último completo (restaurar: completo + último diferencial). El incremental copia sólo lo cambiado desde el último backup de cualquier tipo (restaurar: completo + todos los incrementales).

*Sección 14: Data Backups.*
</details>

### 16. ¿Qué nivel de RAID ofrece tolerancia a la falla de un disco usando paridad distribuida y requiere al menos tres discos?

A) RAID 0
B) RAID 5
C) RAID 1
D) RAID 10

<details><summary>Ver respuesta</summary>

**Respuesta: B.** RAID 5 reparte datos y paridad en mínimo 3 discos y soporta la falla de uno. RAID 0 no tiene redundancia; RAID 1 es espejo; RAID 6 tolera dos fallas.

*Sección 14: High Availability / Data Redundancy.*
</details>
