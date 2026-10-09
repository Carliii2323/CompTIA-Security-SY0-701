# Dominio 1.0: Conceptos generales de seguridad (12%)

12 preguntas de opción múltiple. Intentá responder antes de abrir la solución. Los términos técnicos se dejan también en inglés porque el examen se rinde en inglés.

Fuente: secciones 2, 4 y 8 de las notas completas.

---

### 1. Una empresa instala cámaras visibles en el estacionamiento y carteles que dicen "Área bajo vigilancia 24 h". ¿Qué tipo de control representan principalmente los carteles?

A) Preventivo (preventive)
B) Correctivo (corrective)
C) Disuasivo (deterrent)
D) Compensatorio (compensating)

<details><summary>Ver respuesta</summary>

**Respuesta: C.** Un cartel no impide físicamente el acceso; desalienta al atacante haciendo que el esfuerzo parezca más arriesgado. Eso es un control disuasivo. Las cámaras grabando serían además detectivas.

*Sección 2: Security Control Types.*
</details>

### 2. Un sistema legado no admite MFA. Mientras se reemplaza, la empresa lo aísla en una VLAN y exige acceso por un jump server con MFA. ¿Qué tipo de control es?

A) Compensatorio (compensating)
B) Disuasivo (deterrent)
C) Detectivo (detective)
D) Directivo (directive)

<details><summary>Ver respuesta</summary>

**Respuesta: A.** Un control compensatorio es una medida alternativa cuando el control principal no es viable. La segmentación más el jump server compensan la falta de MFA en el sistema.

*Sección 2: Security Control Types.*
</details>

### 3. Una política escrita que indica que todos los empleados deben bloquear su pantalla al alejarse del escritorio es un ejemplo de control de categoría ______ y tipo ______.

A) Gerencial (managerial) / directivo
B) Físico / disuasivo
C) Operativo / detectivo
D) Técnico / preventivo

<details><summary>Ver respuesta</summary>

**Respuesta: A.** Las políticas pertenecen a la categoría gerencial (también llamada administrativa) y su tipo es directivo: guían o exigen un comportamiento. Si el bloqueo se forzara por GPO, sería técnico/preventivo.

*Sección 2: Security Control Categories y Types.*
</details>

### 4. ¿Qué principio garantiza que un remitente no pueda negar haber enviado un mensaje firmado digitalmente?

A) Confidencialidad
B) No repudio (non-repudiation)
C) Autorización
D) Disponibilidad

<details><summary>Ver respuesta</summary>

**Respuesta: B.** El no repudio se logra con firmas digitales: el mensaje se firma con la clave privada del remitente, que sólo él posee, así que no puede negar la autoría.

*Sección 2: Non-repudiation.*
</details>

### 5. En una arquitectura Zero Trust, ¿qué componente toma la decisión de conceder o denegar acceso comparando la solicitud con las políticas definidas?

A) Data Plane
B) Policy Administrator (PA)
C) Policy Engine (PE)
D) Policy Enforcement Point (PEP)

<details><summary>Ver respuesta</summary>

**Respuesta: C.** El Policy Engine evalúa la solicitud contra las políticas y decide. El Policy Administrator establece la sesión y comunica la decisión, y el PEP es donde efectivamente se permite o bloquea el tráfico.

*Sección 2: Zero Trust.*
</details>

### 6. La organización quiere comparar su postura de seguridad actual con la exigida por un marco de referencia antes de una auditoría. ¿Qué proceso debe realizar?

A) Pruebas de penetración
B) Modelado de amenazas
C) Análisis de causa raíz
D) Análisis de brechas (gap analysis)

<details><summary>Ver respuesta</summary>

**Respuesta: D.** El gap analysis mide la diferencia entre el estado actual y el deseado. Sus pasos son: definir el alcance, recolectar datos, analizar y desarrollar un plan (por ejemplo, un POA&M).

*Sección 2: Gap Analysis.*
</details>

### 7. ¿Qué control físico impide que un intruso entre detrás de un empleado autorizado (tailgating), al permitir que sólo una puerta esté abierta a la vez?

A) Vestíbulo de control de acceso (access control vestibule)
B) Iluminación perimetral
C) Cerradura con PIN
D) Bolardos (bollards)

<details><summary>Ver respuesta</summary>

**Respuesta: A.** El access control vestibule (antes llamado mantrap) tiene dos puertas: la segunda no se abre hasta que la primera se cierra, lo que evita el piggybacking y el tailgating.

*Sección 4: Access Control Vestibules.*
</details>

### 8. Un auditor necesita confirmar que un archivo descargado no fue alterado. ¿Qué debe comparar?

A) El tamaño del archivo con el publicado
B) La firma del certificado TLS del sitio
C) El hash SHA-256 del archivo con el publicado por el proveedor
D) La clave simétrica usada para cifrarlo

<details><summary>Ver respuesta</summary>

**Respuesta: C.** El hashing verifica integridad: cualquier cambio en el archivo produce un hash distinto. El tamaño puede coincidir aunque el contenido cambie.

*Sección 8: Hashing.*
</details>

### 9. ¿Qué técnica protege contra ataques de tablas arcoíris (rainbow tables) al almacenar contraseñas?

A) Compresión
B) Salting
C) Cifrado con AES-256
D) Codificación Base64

<details><summary>Ver respuesta</summary>

**Respuesta: B.** Una sal (salt) es un valor aleatorio que se agrega a cada contraseña antes de aplicar el hash, por lo que dos contraseñas iguales generan hashes distintos y las tablas precomputadas dejan de servir. Key stretching (PBKDF2, bcrypt) suma otra capa.

*Sección 8: Increasing Hash Security.*
</details>

### 10. Alice quiere enviarle a Bob un mensaje que sólo Bob pueda leer, usando criptografía asimétrica. ¿Con qué clave cifra Alice?

A) La clave privada de Alice
B) La clave pública de Bob
C) La clave privada de Bob
D) La clave pública de Alice

<details><summary>Ver respuesta</summary>

**Respuesta: B.** Para confidencialidad se cifra con la clave pública del destinatario; sólo su clave privada puede descifrar. Para firmar (no repudio) se usa la clave privada del remitente.

*Sección 8: Asymmetric Algorithms.*
</details>

### 11. ¿Qué mecanismo permite a un navegador verificar en tiempo real si un certificado fue revocado, sin descargar una lista completa?

A) CRL
B) CSR
C) Key escrow
D) OCSP

<details><summary>Ver respuesta</summary>

**Respuesta: D.** OCSP (Online Certificate Status Protocol) consulta el estado de un certificado puntual. La CRL es la lista completa de revocados; el CSR es la solicitud de firma de certificado. OCSP stapling hace que el servidor adjunte la respuesta.

*Sección 8: Digital Certificates.*
</details>

### 12. Un desarrollador reemplaza los números de tarjeta reales por valores sustitutos sin relación matemática, guardando el mapeo en una bóveda segura. ¿Qué técnica usó?

A) Hashing
B) Enmascaramiento (masking)
C) Esteganografía
D) Tokenización

<details><summary>Ver respuesta</summary>

**Respuesta: D.** La tokenización reemplaza el dato sensible por un token y conserva el mapeo en un vault. El masking sólo oculta parte del dato (por ejemplo, ****1234) y la esteganografía esconde datos dentro de otros archivos.

*Sección 8: Obfuscation.*
</details>
