# Dominio 5.0: Gestión y supervisión del programa de seguridad (20%)

18 preguntas de opción múltiple. Incluye cálculos de riesgo: tené a mano papel y lápiz.

Fuente: secciones 9 a 13 y 27 de las notas completas.

---

### 1. Un servidor vale USD 50.000. Un incendio destruiría el 40% de su valor y se espera uno cada 5 años. ¿Cuál es el ALE?

A) USD 10.000
B) USD 100.000
C) USD 4.000
D) USD 20.000

<details><summary>Ver respuesta</summary>

**Respuesta: C.** SLE = valor del activo × EF = 50.000 × 0,40 = 20.000. ARO = 1/5 = 0,2. ALE = SLE × ARO = 20.000 × 0,2 = 4.000 por año.

*Sección 9: Quantitative Risk Analysis.*
</details>

### 2. Una empresa contrata un seguro contra ciberataques. ¿Qué estrategia de gestión de riesgo aplica?

A) Aceptación
B) Transferencia
C) Evasión (avoidance)
D) Mitigación

<details><summary>Ver respuesta</summary>

**Respuesta: B.** El seguro transfiere el impacto financiero a otro. Ojo: el riesgo no desaparece, sólo cambia quién paga sus consecuencias.

*Sección 9: Risk Management Strategies.*
</details>

### 3. Un proyecto de app móvil tiene un riesgo legal tan alto que la empresa decide no lanzarlo. ¿Qué estrategia es?

A) Transferencia
B) Mitigación
C) Aceptación
D) Evasión (avoidance)

<details><summary>Ver respuesta</summary>

**Respuesta: D.** Evitar el riesgo implica cambiar planes o abandonar la actividad que lo genera.

*Sección 9: Risk Management Strategies.*
</details>

### 4. ¿Cómo se llama el nivel de riesgo que queda después de aplicar los controles?

A) Riesgo inherente
B) Tolerancia al riesgo
C) Riesgo residual
D) Apetito de riesgo

<details><summary>Ver respuesta</summary>

**Respuesta: C.** El riesgo inherente es el que existe antes de los controles; el residual, el que queda después. El apetito es cuánto riesgo está dispuesta a perseguir la organización.

*Sección 9: Risk Management / Risk Register.*
</details>

### 5. ¿Qué documento lista los riesgos identificados, su probabilidad, impacto, dueño y plan de respuesta?

A) Registro de riesgos (risk register)
B) MOU
C) SLA
D) Política de uso aceptable (AUP)

<details><summary>Ver respuesta</summary>

**Respuesta: A.** El risk register centraliza la información de cada riesgo y su seguimiento. Cada riesgo tiene un dueño (risk owner).

*Sección 9: Risk Register.*
</details>

### 6. Calcular impacto con escalas "bajo, medio, alto" en una matriz de calor es un análisis:

A) Cualitativo
B) Forense
C) Financiero
D) Cuantitativo

<details><summary>Ver respuesta</summary>

**Respuesta: A.** El análisis cualitativo usa categorías subjetivas; el cuantitativo usa valores numéricos y monetarios (SLE, ALE).

*Sección 9: Qualitative Risk Analysis.*
</details>

### 7. Antes de firmar con un proveedor de nube, la empresa revisa su estabilidad financiera, certificaciones y reportes SOC 2. ¿Cómo se llama este proceso?

A) Right-to-audit
B) Due diligence
C) Due care
D) Attestation

<details><summary>Ver respuesta</summary>

**Respuesta: B.** La debida diligencia investiga al proveedor antes de contratarlo. El due care es actuar de forma responsable una vez asumido el compromiso.

*Sección 10: Vendor Assessment.*
</details>

### 8. ¿Qué acuerdo define métricas como disponibilidad del 99,9% y tiempos de respuesta, con penalidades si no se cumplen?

A) SLA
B) BPA
C) NDA
D) MOU

<details><summary>Ver respuesta</summary>

**Respuesta: A.** El Service Level Agreement fija niveles de servicio medibles. El MOU es un acuerdo de intención no vinculante; el NDA protege información confidencial; el MSA establece términos generales para futuros contratos (SOW).

*Sección 10: Contracts and Agreements.*
</details>

### 9. Atacantes comprometen el servidor de actualizaciones de un proveedor de software y distribuyen una versión con backdoor a miles de clientes. ¿Qué ataque es?

A) Ataque a la cadena de suministro (supply chain)
B) Insider threat
C) Phishing masivo
D) Watering hole

<details><summary>Ver respuesta</summary>

**Respuesta: A.** Se compromete a un proveedor confiable para llegar a sus clientes, como en el caso de SolarWinds.

*Sección 10: Supply Chain Attacks.*
</details>

### 10. Ordená de más general a más específico: procedimiento, política, estándar.

A) Política, procedimiento, estándar
B) Procedimiento, estándar, política
C) Política, estándar, procedimiento
D) Estándar, política, procedimiento

<details><summary>Ver respuesta</summary>

**Respuesta: C.** La política define el qué y el por qué a alto nivel; el estándar fija requisitos obligatorios concretos (por ejemplo, AES-256); el procedimiento detalla paso a paso cómo hacerlo.

*Sección 11: Policies / Standards / Procedures.*
</details>

### 11. En el GDPR, ¿qué rol determina los fines y medios del tratamiento de datos personales?

A) Encargado del tratamiento (processor)
B) Custodio de datos
C) Sujeto de datos
D) Responsable del tratamiento (controller)

<details><summary>Ver respuesta</summary>

**Respuesta: D.** El controller decide qué datos se procesan y para qué; el processor los trata en su nombre. El custodio implementa los controles técnicos día a día.

*Sección 7: Data Ownership / Sección 11: Governance Considerations.*
</details>

### 12. ¿Cuál es una consecuencia típica de no cumplir con PCI DSS?

A) Mejor calificación crediticia
B) Multas y pérdida de la capacidad de procesar tarjetas
C) Reducción automática del ALE
D) Ninguna, es voluntario

<details><summary>Ver respuesta</summary>

**Respuesta: B.** El incumplimiento puede traer multas, sanciones, daño reputacional, pérdida de licencias y acciones contractuales.

*Sección 11: Non-compliance Consequences.*
</details>

### 13. Antes de implementar un cambio en un firewall de producción, ¿qué debe existir según la gestión de cambios?

A) Un nuevo registro de riesgos
B) Solicitud aprobada (por ejemplo, por el CAB), análisis de impacto, ventana de mantenimiento y plan de reversión (backout)
C) Un pentest completo
D) Sólo la aprobación verbal del técnico

<details><summary>Ver respuesta</summary>

**Respuesta: B.** El proceso formal incluye aprobación, análisis de impacto, pruebas, ventana de mantenimiento, plan de rollback y documentación.

*Sección 12: Change Management Processes.*
</details>

### 14. Al dar de baja discos con datos sensibles, ¿qué evidencia demuestra que se destruyeron correctamente?

A) El inventario actualizado
B) Un correo del técnico
C) Un ticket cerrado
D) Un certificado de destrucción

<details><summary>Ver respuesta</summary>

**Respuesta: D.** El proveedor de destrucción emite un certificado como prueba. Los métodos incluyen sobrescritura, degaussing, triturado o incineración.

*Sección 12: Asset Disposal and Decommissioning.*
</details>

### 15. Un pentester recibe diagramas de red y código fuente antes de empezar. ¿Qué tipo de prueba es?

A) Caja blanca (known environment)
B) Caja negra (unknown environment)
C) Bug bounty
D) Caja gris (partially known)

<details><summary>Ver respuesta</summary>

**Respuesta: A.** En el entorno conocido el evaluador tiene información completa. En caja negra no sabe nada; en caja gris, información parcial.

*Sección 13: Penetration Testing.*
</details>

### 16. Durante un pentest se buscan datos de la empresa en LinkedIn, registros WHOIS y DNS públicos sin interactuar con sus sistemas. ¿Qué tipo de reconocimiento es?

A) Movimiento lateral
B) Pasivo (OSINT)
C) Activo
D) Explotación

<details><summary>Ver respuesta</summary>

**Respuesta: B.** El reconocimiento pasivo usa fuentes públicas sin tocar los sistemas objetivo. El activo incluye escaneos de puertos o vulnerabilidades.

*Sección 13: Reconnaissance in Pentesting.*
</details>

### 17. ¿Qué documento define formalmente el alcance, horarios y límites de lo que el pentester puede hacer?

A) AUP
B) SLA
C) Registro de riesgos
D) Reglas de enfrentamiento (Rules of Engagement)

<details><summary>Ver respuesta</summary>

**Respuesta: D.** Las RoE fijan alcance, sistemas incluidos y excluidos, horarios, contactos y técnicas permitidas. Sin autorización por escrito, un pentest es ilegal.

*Sección 13: Penetration Testing.*
</details>

### 18. Tras una campaña de phishing simulado, ¿qué métrica indica mejor que la capacitación funciona?

A) Número de políticas publicadas
B) Presupuesto del área de seguridad
C) Aumento de la tasa de reportes y caída de la tasa de clics
D) Cantidad de correos enviados

<details><summary>Ver respuesta</summary>

**Respuesta: C.** El objetivo es cambiar el comportamiento: que menos usuarios hagan clic y más reporten el correo sospechoso.

*Sección 27: Security Awareness / Creating a Culture of Security.*
</details>
