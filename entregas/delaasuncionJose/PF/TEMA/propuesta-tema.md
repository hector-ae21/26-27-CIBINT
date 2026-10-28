# PF-TEMA · Propuesta individual

**Estudiante:** Jose Luis de la Asuncion Saura
**Fecha y versión:** 28/10/2026, v0.1
**Título provisional:** Investigación e informe sobre la huella digital de una empresa a lo largo de los años.

**Modalidad:** Exposición / Caso personal autorizado  
**Canal de entrega:** (tanto a la empresa como al profesor se les entregará el informe)   
**Número de palabras y método de recuento:** 789


## 1. Caso real y situación de partida

El caso real es el siguiente: la empresa quiere analizar qué huella digital ha dejado a lo largo de todos sus años de operación; cuenta con una página web y con cuentas de redes sociales donde se difunde su actividad empresarial.

El problema a investigar consiste en auditar y mapear de forma pasiva la huella digital acumulada de la organización mediante técnicas OSINT (*Open Source Intelligence*), con el fin de identificar información sensible disponible públicamente que represente un vector de riesgo. El informe final tendrá un carácter defensivo y preventivo, y se entregará tanto al tutor académico como al responsable de la organización para su remediación.

### 1.1. Hechos confirmados vs. por confirmar

* **Hechos confirmados:**
    * Tienen una actividad online (web + R. S.).
    * Empresa desconoce su huella digital.
    * Actividad económica no es estrictamente digital.
    * Acotado estrictamente a reglas OSINT.


* **Hechos por confirmar:**
    * Dominios y subdominios pertenecientes a la empresa.
    * Si hay existencia de documentos online.
    * Búsqueda de correos corporativos.
    * Posibilidad de ataques de *phishing*, etc., más sofisticados basándose en información OSINT.



## 2. Destinatario y decisión

| Campo | Propuesta |
| --- | --- |
| Destinatario | Profesor y presidente de la empresa investigada |
| Condición del destinatario | Encargo acreditado |
| Decisión que necesita tomar | Decidir qué limpieza de información hay que llevar a cabo para reducir la huella digital de la empresa y, de esta manera, reducir posibles ángulos de ataque. |
| Utilidad del informe | Permite aportar una perspectiva de un ataque pasivo a la empresa que puede realizar cualquiera desde fuentes públicas y fácilmente accesibles. |

## 3. Preguntas de inteligencia

| ID | Pregunta principal | Decisión a la que contribuye |
| --- | --- | --- |
| PI-01 | ¿Qué información, documentos, emails, nombres, credenciales, son accesibles de manera pública y cuáles deberían ser retirados? | Decidir qué información debería quitarse de fuentes públicas. |
| PI-02 | ¿Qué subdominios, servidores, servicios tiene la empresa visibles de manera pública que puedan ser accesibles? | Recoger los servicios y recursos digitales que tiene la empresa y decidir si hay alguno que ya no se use y se deba eliminar. |
| PI-03 | ¿Cuánta cantidad de exposición digital ha tenido la empresa y desde cuándo ha comenzado dicha digitalización? | Ayuda a tener un seguimiento de todo el recorrido digital de la empresa a lo largo de los años y toda su actividad detallada. |

## 4. Alcance y exclusiones

| Límite | Propuesta |
| --- | --- |
| Organización, servicio, campaña o identidad propia | REDACTED |
| Periodo de los hechos | 2018-Actualidad (estimación en base al registro del dominio; probablemente vaya más allá de 2018). |
| Corte previsto de información, con zona horaria | **14** de diciembre de 2026, a las **23:59** GMT+2 |
| Territorio, cuando sea relevante | España / Unión Europea (marco regulatorio). |
| Fuentes y acciones propuestas | Desde la vista de fuentes públicas, un análisis profundo de búsqueda usando las herramientas vistas en clase. |
| Datos que necesitas conservar | Emails de empresa, dominios, documentos, links de interés, *hashes* de la información, marcas temporales y metadatos. |
| Datos que no se recogerán | Credenciales/contraseñas, información sensible (números privados, nombres ajenos, documentos delicados), información financiera o bancaria de los clientes/empresa. |
| Autorización disponible y condiciones; si procede, referencia privada al documento | Confirmado por el presidente, falta una última confirmación de la junta directiva. |
| Motivo de entrega privada, si es un caso personal; canal acordado y acceso habilitado para la revisión | Debido a que es un informe que va a contener información sensible, haré un repo con el informe en privado donde invitaré al profesor como colaborador. |
| Acciones expresamente excluidas | Cualquier ataque activo, escaneo de puertos, DoS, *phishing*, cualquier método no público para conseguir información. |
| Condición de parada y procedimiento de consulta | Cuando se encuentre información sensible se contactará de inmediato tanto a la empresa como al profesor para solucionarlo cuanto antes. |

## 5. Viabilidad y referencias iniciales

| Referencia | Autor u organización | Título y URL | Fecha de publicación y consulta | Primaria o secundaria | Qué pregunta ayuda a responder |
| --- | --- | --- | --- | --- | --- |
| F-01 | Empresa | Web de empresa (en el repo privado se adjunta) | 2018-Actualidad | Primaria | PI-02 |
| F-02 | Empresa | Cuentas de R. S. (en el repo privado se adjunta) | 2015-2019 (X) / 2026 (FB) | Primaria | PI-01, PI-03 |
| F-03 | Empresa | Documentos con emails, etc. | 2014 | Primaria | PI-01 |

Hay más que suficiente información para un análisis; aquí no se han puesto los enlaces por seguridad, se adjuntan en el repo privado.

## 6. Plan de trabajo

* P1. Para responder la primera pregunta se necesitará recabar todo tipo de información, cuanto más mejor, y luego ya organizarla y escoger cuál será útil o no.
* P2. Para responder a la segunda pregunta se usará la información de la pregunta 1 y se indagará mucho más en el aspecto informático, DNS, IPs, etc., cualquier información disponible pero sin hacer ningún ataque.
* P3. Con la recogida de la información de P1 y P2, luego se hará un análisis con una línea temporal de la exposición de información disponible de la empresa en la web.

## 7. Declaración

He leído las condiciones del proyecto. Esta propuesta no me autoriza a acceder a sistemas, contactar con la organización ni ampliar las acciones por mi cuenta. La recogida sistemática comenzará cuando se apruebe el alcance. Entrego mi declaración de uso o ausencia de IA en `registro-ia.md`.

## 8. Resolución de la propuesta

Aún por determinar

[No completar como si fuera una aprobación. Después de recibirla, anota su fecha, las condiciones indicadas y la versión del alcance aprobada.]