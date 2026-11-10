# Incidente de ciberseguridad en Air Europa (2023-2024): evolución del alcance comunicado y pautas de protección al cliente ante exposición de datos

## Portada y control del documento

| Campo | Contenido |
| --- | --- |
| Autor | Sergio Rodríguez López · Estudiante de Grado en Ingeniería Informática (Ciberinteligencia) |
| Destinatario | Dirección de Atención al Cliente y Prevención de Fraude de una compañía del sector transporte o comercio electrónico (Supuesto académico) |
| Organización o caso estudiado | Air Europa (incidente en el entorno de pagos web de octubre de 2023 y ampliación de alcance sobre datos personales de marzo de 2024) |
| Fecha y versión | 9 de noviembre de 2026, v0.2 (Avance PF-P1) |
| Periodo de los hechos | Del 10 de octubre de 2023 al 31 de marzo de 2024 |
| Corte de información | 1 de diciembre de 2026 a las 23:59 (`Europe/Madrid`) |
| Condiciones de difusión | Entrega académica pública mediante repositorio del curso; TLP:CLEAR (información procedente íntegramente de fuentes abiertas e institucionales) |
| Referencia del encargo y alcance aprobado | Propuesta `PF-TEMA` (versión del alcance del 27 de octubre de 2026), aprobada con condiciones el 4 de noviembre de 2026 |

### Historial de versiones

| Versión | Fecha | Cambio principal | Responsable |
| --- | --- | --- | --- |
| 0.1 | 28-10-2026 | Propuesta inicial del tema y delimitación preliminar (`PF-TEMA`) | Sergio Rodríguez López |
| 0.2 | 09-11-2026 | Primer avance (`PF-P1`): incorporación de las 3 condiciones de aprobación, contexto, plan de obtención, evaluación legal/OPSEC, 5 fuentes iniciales y primeras observaciones | Sergio Rodríguez López |

## Índice

1. [Resumen ejecutivo](#1-resumen-ejecutivo)
2. [Requerimiento de inteligencia](#2-requerimiento-de-inteligencia)
3. [Alcance, límites y condiciones de trabajo](#3-alcance-límites-y-condiciones-de-trabajo)
4. [Contexto y cronología](#4-contexto-y-cronología)
5. [Fuentes y método](#5-fuentes-y-método)
6. [Resultados y evidencias](#6-resultados-y-evidencias)
7. [Análisis](#7-análisis)
8. [Amenazas, indicadores y comportamientos](#8-amenazas-indicadores-y-comportamientos)
9. [Confianza y limitaciones](#9-confianza-y-limitaciones)
10. [Conclusiones y recomendaciones](#10-conclusiones-y-recomendaciones)
11. [Referencias](#11-referencias)
12. [Anexos](#12-anexos)

## 1. Resumen ejecutivo

*Pendiente de elaboración (se redactará en el tercer avance `PF-P3` al finalizar el análisis, conforme a la plantilla oficial).*

## 2. Requerimiento de inteligencia

| Elemento | Definición para este trabajo |
| --- | --- |
| Destinatario y necesidad | Dirección de Atención al Cliente y Prevención de Fraude de una entidad de transporte o comercio electrónico (supuesto académico). Necesita comprender cómo evoluciona la información confirmada en un incidente real de exposición de datos en dos fases para orientar las comunicaciones y pautas de soporte. |
| Decisión que se debe apoyar | Determinar qué criterios de comunicación escalonada y qué recomendaciones de protección trasladar a los usuarios afectados cuando el alcance conocido de una brecha evoluciona de datos de pago a datos identificativos, sin exceder la evidencia confirmada en cada fase ni atribuir fraudes posteriores no demostrados. |
| Objeto | El incidente de ciberseguridad notificado por Air Europa en octubre de 2023 sobre su pasarela de pagos web y la ampliación informativa comunicada en marzo de 2024 relativa a datos personales y de contacto. |
| Plazo | Primer avance (`PF-P1`): 9 de noviembre de 2026. Segundo avance (`PF-P2`): 25 de noviembre de 2026. Borrador completo (`PF-P3`): 9 de diciembre de 2026. Informe definitivo (`PF-FINAL`): 14 de diciembre de 2026. |
| Resultado solicitado | Informe de inteligencia documental en Markdown respaldado por registros trazables (`fuentes.csv`, `hallazgos.csv`, `bitacora.csv`) que responda a las tres preguntas de inteligencia e incorpore recomendaciones priorizadas. |

### Preguntas

| ID | Pregunta de inteligencia | Decisión a la que contribuye |
| --- | --- | --- |
| PI-01 | ¿Qué hechos se dieron por confirmados y qué aspectos quedaron sin acreditar en cada una de las fases de comunicación oficial del incidente de Air Europa entre octubre de 2023 y marzo de 2024? | Definir qué afirmaciones puede sostener un equipo de atención al cliente en cada etapa de una investigación en curso sin especular ni afirmar prematuramente que otros datos están a salvo. |
| PI-02 | ¿Cómo variaron las recomendaciones preventivas dirigidas a los usuarios entre la primera notificación (centrada en medios de pago) y la actualización posterior (ampliada a datos personales y de contacto)? | Priorizar las medidas de protección al cliente según la tipología de información comprometida en cada momento. |
| PI-03 | ¿Qué riesgos de fraude secundario (*spearphishing*, suplantación de identidad o uso de tarjetas) se describen como posibilidades justificadas por las fuentes a partir de los datos expuestos y qué limitaciones existen para atribuir incidentes posteriores a esta brecha? | Orientar los protocolos de verificación de identidad y las alertas antifraude tratando dichos riesgos como posibilidades justificadas, sin atribuir a esta brecha fraudes posteriores concretos. |

## 3. Alcance, límites y condiciones de trabajo

El objeto de estudio se circunscribe exclusivamente a los hechos documentados y a las comunicaciones dirigidas a los clientes de Air Europa entre el **10 de octubre de 2023** (primera notificación pública y envío de correos sobre tarjetas bancarias) y el **31 de marzo de 2024** (cierre del periodo de actualización de avisos tras la segunda notificación de marzo de 2024 sobre datos identificativos). El corte de información se fija el **1 de diciembre de 2026 a las 23:59 (`Europe/Madrid`)**.

La práctica cuenta con aprobación académica con condiciones de fecha **4 de noviembre de 2026** (sobre la versión del alcance del 27 de octubre de 2026). Se incorporan de forma estricta las tres condiciones dictadas por el docente:

1. **Incorporación de fuentes primarias de Air Europa (`F-04` y `F-05`):** Se añaden los comunicados y correos electrónicos remitidos por la propia aerolínea a sus clientes en octubre de 2023 y marzo de 2024 (reproducidos íntegramente en fuentes verificables como OCU, FACUA y prensa con capturas del comunicado oficial) para contrastar directamente lo dicho por la empresa y no depender únicamente de INCIBE o de resúmenes periodísticos.
2. **Delimitación analítica de `PI-03`:** Los riesgos de fraude secundario se analizan exclusivamente como escenarios y posibilidades preventivas justificadas por las fuentes institucionales, sin atribuir ningún fraude posterior concreto a esta brecha.
3. **Restricción del análisis técnico (Tema 4):** El análisis de infraestructura se limita estrictamente a la información documental publicada sobre el incidente (afectación del entorno de pagos web); se excluye consultar, resolver o analizar la infraestructura actual de Air Europa.

| Dentro del alcance | Fuera del alcance | Motivo |
| --- | --- | --- |
| Avisos oficiales e historial de actualizaciones de INCIBE (`F-01`) e INCIBE-CERT (`F-02`) sobre el incidente de Air Europa. | Infraestructura técnica actual de Air Europa (consultas DNS directas, CT logs, Shodan o visitas a servicios técnicos actuales). | Condición expresa nº 3 de aprobación del alcance y normas de OPSEC de la asignatura. |
| Textos de los correos electrónicos y comunicados oficiales de Air Europa de octubre de 2023 (`F-04`) y marzo de 2024 (`F-05`) reproducidos en fuentes verificables. | Acceso a foros delictivos, *dark web*, mercados clandestinos o descarga de muestras de datos filtrados. | Restricción legal y ética de la asignatura; el trabajo es estrictamente documental sobre fuentes abiertas autorizadas. |
| Análisis de organizaciones de consumidores y verificadores (`F-03`, `F-04`, `F-05`) que recogen las comunicaciones a afectados y las recomendaciones preventivas. | Recopilación de datos personales reales de pasajeros (PII), números de tarjetas bancarias (PAN/CVV) o identificación de víctimas concretas. | Cumplimiento de normativa de protección de datos (RGPD/LOPDGDD) y minimización de datos. |
| Estudio de los riesgos de fraude derivado como posibilidades preventivas justificadas por el tipo de dato expuesto (`PI-03`). | Atribución de campañas de *phishing* o fraudes bancarios posteriores concretos a la brecha de Air Europa, o atribución del ataque a un actor de amenazas sin evidencia oficial. | Condición expresa nº 2 de aprobación del alcance y rigor metodológico de inteligencia. |

### Datos, seguridad y condiciones de parada

* **Datos que se conservan:** Metadatos de las publicaciones (autor, organización, título, URL, fecha de publicación original, fecha de actualización y fecha de consulta), afirmaciones literales o sintetizadas de los comunicados de Air Europa e INCIBE, categorías abstractas de datos declarados como expuestos (p. ej., «número de tarjeta», «DNI», «teléfono») y recomendaciones de protección asociadas.
* **Datos expresamente excluidos:** Ningún registro del proyecto contendrá nombres de clientes afectados, direcciones de correo personales de pasajeros, números de documento de identidad ni numeraciones de tarjetas bancarias.
* **Evaluación legal y de OPSEC:** La investigación se realiza íntegramente mediante consulta pasiva de documentos públicos en organismos oficiales (INCIBE) y organizaciones de consumidores/medios verificados. No se establece contacto con Air Europa, con sus proveedores tecnológicos ni con clientes afectados. No se ejecutan scripts de reconocimiento ni consultas sobre activos de red de la aerolínea.
* **Condición de parada y procedimiento de consulta:** Si durante la consulta de fuentes secundarias o repositorios documentales apareciese una captura sin censurar que muestre datos personales de un pasajero real o numeración de tarjetas, se detendrá inmediatamente la extracción, no se guardará copia ni captura del dato en el repositorio y se notificará al docente por el canal privado de la asignatura para acordar el descarte de la fuente.

## 4. Contexto y cronología

### Contexto documentado del caso

El incidente estudiado afecta a la aerolínea española Air Europa y se caracteriza desde el punto de vista de la inteligencia documental por haberse comunicado en **dos etapas diferenciadas separadas por cinco meses**, a raíz de un mismo suceso originado en septiembre de 2023:

1. **Primera etapa (Octubre de 2023 · Entorno de pagos):** El 10 de octubre de 2023, Air Europa comenzó a remitir una comunicación oficial por correo electrónico a determinados clientes (`F-04`) informando de la detección de un ataque de ciberseguridad en su entorno de pagos web. Al día siguiente, 11 de octubre de 2023, INCIBE publicó su aviso de seguridad (`F-01`), precisando que la detección interna se produjo el 29 de septiembre de 2023. En esta primera fase, la aerolínea afirmó en su comunicación que la filtración se limitaba exclusivamente a los datos de las tarjetas bancarias utilizadas en la web (número de tarjeta, fecha de caducidad y CVV) y aseguró inicialmente que no se había visto afectado ningún otro dato personal (`F-03`, `F-04`).
2. **Segunda etapa (Marzo de 2024 · Ampliación a datos personales):** El 21 de marzo de 2024, como resultado de la continuación de la investigación forense sobre el incidente de octubre de 2023, Air Europa remitió un segundo comunicado a sus clientes (`F-05`), reflejado en la actualización del 22 de marzo de 2024 de los avisos de INCIBE (`F-01`) e INCIBE-CERT (`F-02`). En esta segunda comunicación se notificó que un segundo conjunto de datos identificativos y de contacto (nombre, apellidos, DNI/pasaporte, nacionalidad, fecha de nacimiento, teléfono, correo electrónico y número de socio *Air Europa SUMA*) también había resultado comprometido, excluyendo contraseñas.

### Separación entre hechos conocidos y afirmaciones pendientes

* **Hechos conocidos y respaldados documentalmente:**
  * La existencia del incidente en el entorno de pagos web de Air Europa y su notificación inicial a clientes el 10 de octubre de 2023 (`F-01`, `F-04`).
  * La afirmación inicial de la compañía de que únicamente se habían sustraído datos de tarjetas y ningún otro dato personal (`F-03`, `F-04`).
  * La rectificación o ampliación de alcance del 21-22 de marzo de 2024 confirmando la exposición de datos personales y de contacto vinculados al mismo incidente (`F-01`, `F-02`, `F-05`).
  * El cambio en las recomendaciones oficiales: de la anulación y sustitución preventiva de tarjetas en octubre de 2023 (`F-01`, `F-04`) a la alerta frente a campañas de suplantación e ingeniería social (*phishing*, *smishing*, *vishing*) en marzo de 2024 (`F-01`, `F-05`).
* **Afirmaciones pendientes o no acreditadas en fuentes abiertas:**
  * El mecanismo técnico exacto del compromiso inicial (vector de entrada, vulnerabilidad CVE específica o fallo concreto en la pasarela de pago) no ha sido publicado en los avisos de INCIBE ni en los comunicados de la aerolínea (`F-01`, `F-02`).
  * El volumen total exacto de clientes afectados en cada una de las dos fases no consta de forma oficial en los avisos institucionales consultados.
  * La existencia de un uso fraudulento masivo confirmado a partir de los datos: la compañía declaró en ambas comunicaciones no tener constancia acreditada de que la información se hubiera empleado para cometer fraude (`F-02`, `F-04`, `F-05`).

### Cronología preliminar (Avance P1)

*Nota: La cronología exhaustiva con el contraste completo se desarrollará en el segundo avance (`PF-P2`). Se adelantan los hitos estructurales verificados en las fuentes iniciales:*

| Fecha y zona horaria del hecho | Publicación u observación | Hecho o afirmación atribuida | Fuente | Limitación |
| --- | --- | --- | --- | --- |
| 29-09-2023 (`Europe/Madrid`) | Publicado el 11-10-2023 | Fecha en la que Air Europa detecta internamente el acceso no autorizado en su entorno de pagos web, según recoge el aviso institucional de INCIBE. | `F-01` | No consta públicamente desde qué fecha previa permaneció activo el acceso no autorizado. |
| 10-10-2023 (`Europe/Madrid`) | Observado el 10/11-10-2023 | Air Europa envía el primer correo oficial a clientes afectados indicando la exposición de número de tarjeta, caducidad y CVV, afirmando que no afecta a otros datos personales y recomendando cancelar la tarjeta. | `F-03`, `F-04` | El texto del correo se conoce a través de reproducciones verificadas en prensa y asociaciones de consumidores. |
| 11-10-2023 (`Europe/Madrid`) | Publicado el 11-10-2023 | INCIBE publica la alerta inicial recomendando identificar la tarjeta empleada en la web, solicitar su bloqueo/sustitución al banco y vigilar movimientos. | `F-01` | Se basa en la notificación preliminar de la compañía cuando la investigación forense seguía abierta. |
| 21-03-2024 (`Europe/Madrid`) | Publicado el 21/22-03-2024 | Air Europa remite un segundo comunicado a clientes informando que el análisis forense posterior al incidente de octubre de 2023 reveló la exposición de datos personales y de contacto. | `F-05`, `F-01` | No se detalla públicamente el motivo técnico por el que la exposición de estos datos se determinó cinco meses después. |
| 22-03-2024 (`Europe/Madrid`) | Actualizado el 22-03-2024 | INCIBE e INCIBE-CERT actualizan sus avisos oficiales añadiendo la lista de datos personales expuestos y orientando las pautas hacia la prevención de suplantación e ingeniería social. | `F-01`, `F-02` | Las actualizaciones confirman las categorías de datos, pero mantienen sin publicar indicadores técnicos (IoC) del incidente. |

## 5. Fuentes y método

### Plan de fuentes y consultas (Vinculación con preguntas de inteligencia)

Para cumplir con los requisitos del primer avance (`PF-P1`) y con la **Condición 1 de aprobación del alcance**, se ha estructurado un registro inicial de **cinco fuentes pertinentes (`F-01` a `F-05`)**, combinando dos fuentes institucionales de ciberseguridad (`F-01`, `F-02`), dos fuentes que reproducen de forma verificable los comunicados/correos primarios enviados por Air Europa a sus clientes en octubre de 2023 (`F-04`) y marzo de 2024 (`F-05`), y una fuente secundaria de verificación documental (`F-03`).

Cada consulta documental responde a una pregunta de inteligencia definida:

| Fuente o grupo | Pregunta que cubre | Criterio de selección y evaluación | Limitación |
| --- | --- | --- | --- |
| **Grupo Institucional:** Avisos de INCIBE (`F-01`) e INCIBE-CERT (`F-02`) en sus versiones de octubre de 2023 y marzo de 2024. | `PI-01`, `PI-02`, `PI-03` | Organismos oficiales de referencia en España. Permiten contrastar qué se dio por confirmado institucionalmente en cada fecha y cómo cambiaron las pautas de protección al ciudadano. | Dependen en origen de los hallazgos notificados por Air Europa; no publican el informe forense interno ni vectores de ataque técnicos. |
| **Grupo Primario Reproducido (Comunicados de Air Europa):** Correo de Air Europa de octubre de 2023 (`F-04`) y correo de ampliación de marzo de 2024 (`F-05`), recogidos por OCU/FACUA y medios con captura del texto oficial. | `PI-01`, `PI-02` | Cumple la Condición 1 de aprobación del alcance: permite analizar las afirmaciones literales de la aerolínea hacia sus clientes en cada fase sin depender únicamente del resumen de INCIBE. | Al ser comunicaciones directas por correo a clientes, se accede a su contenido íntegro a través de su reproducción en organizaciones de consumidores y prensa verificada. |
| **Grupo Secundario y Análisis de Riesgo:** Artículos de verificación y asociaciones de consumidores (`F-03`, `F-04`, `F-05`). | `PI-02`, `PI-03` | Aportan el contraste independiente sobre las recomendaciones de protección al usuario y explican las posibilidades teóricas de ingeniería social (*spearphishing* / *vishing*) derivadas de los datos expuestos. | No permiten atribuir fraudes reales posteriores a la brecha (Condición 2 del alcance); solo justifican escenarios preventivos. |

### Ubicación de registros y convención de identificadores

* **Registro de fuentes:** Ubicado en `registros/fuentes.csv`. Utiliza los identificadores `F-01` a `F-05`.
* **Registro de hallazgos:** Ubicado en `registros/hallazgos.csv`. Utiliza los identificadores `H-01`, `H-02`, etc., vinculados a cada pregunta (`PI-01` a `PI-03`) y a las fuentes que los sostienen.
* **Bitácora de trabajo:** Ubicada en `registros/bitacora.csv`. Registra cronológicamente las acciones de búsqueda, verificaciones y decisiones metodológicas con identificadores `B-01`, `B-02`, etc.
* **Registro de integridad:** Ubicado en `registros/integridad.csv`. En este avance se mantiene con sus encabezados oficiales indicando su condición de consulta documental en línea.

## 6. Resultados y evidencias

### Primeras observaciones verificadas (Avance P1)

Sin anticipar las conclusiones del análisis final, se documentan las cinco primeras observaciones verificables extraídas de las fuentes iniciales:

| Hallazgo | Pregunta | Observación verificable | Fuente y fecha | Qué no demuestra |
| --- | --- | --- | --- | --- |
| H-01 | PI-01 | En la primera comunicación remitida a los clientes el 10-10-2023, Air Europa informó que el incidente en el entorno de pagos web solo había comprometido datos de tarjetas (número, caducidad y CVV) y afirmó expresamente que no se había visto afectado ningún otro dato personal, pese a indicar que la investigación seguía en curso. | `F-03` (11-10-2023), `F-04` (11-10-2023) | No demuestra que en octubre de 2023 la empresa conociera ya la filtración de datos identificativos; solo acredita que la afirmación de exclusión se emitió antes de concluir el análisis forense. |
| H-02 | PI-01 | El 21-03-2024, Air Europa envió una segunda comunicación oficial a clientes (recogida por INCIBE el 22-03-2024) confirmando que la investigación forense posterior sobre el mismo incidente de octubre de 2023 detectó la exposición de un segundo bloque de datos personales (nombre, DNI/pasaporte, fecha de nacimiento, nacionalidad, teléfono, correo y nº de socio SUMA), sin afectar a contraseñas. | `F-01` (Act. 22-03-2024), `F-02` (Act. 22-03-2024), `F-05` (22-03-2024) | No demuestra que se produjera un segundo ciberataque independiente en marzo de 2024; las fuentes lo vinculan al análisis forense del incidente de otoño de 2023. |
| H-03 | PI-02 | Las recomendaciones oficiales evolucionaron de una acción de contención financiera directa en octubre de 2023 (identificar la tarjeta usada en la web y solicitar su cancelación/sustitución bancaria) a pautas de vigilancia pasiva y verificación de canales en marzo de 2024 ante posibles engaños dirigidos, dado que un DNI o teléfono no pueden sustituirse como una tarjeta. | `F-01` (11-10-2023 y Act. 22-03-2024), `F-04`, `F-05` | No demuestra qué porcentaje de clientes llegó a cancelar efectivamente su tarjeta ni la eficacia real de las medidas en los usuarios. |
| H-04 | PI-03 | Tanto en octubre de 2023 como en marzo de 2024, los comunicados de Air Europa y los avisos de INCIBE recogen que no existía constancia de que la información expuesta se hubiera utilizado para cometer fraude, pero justifican el riesgo de campañas de *phishing*, *smishing*, *vishing* o suplantación por la combinación de datos reales en poder de terceros. | `F-01`, `F-02`, `F-03`, `F-04`, `F-05` | No demuestra que ningún intento de estafa recibido posteriormente por un cliente proceda de esta brecha concreta (Condición 2 del alcance). |
| H-05 | PI-01 | Ninguna de las fuentes públicas oficiales (`F-01`, `F-02`) ni las reproducciones de los comunicados de la aerolínea (`F-04`, `F-05`) detallan el vector de entrada técnico, la vulnerabilidad explotada (CVE) ni el actor responsable del acceso al entorno de pagos. | `F-01`, `F-02`, `F-04`, `F-05` | No permite realizar atribuciones técnicas ni asociar el caso a una CVE concreta, limitando el Tema 4 y el Tema 6 al plano documental y preventivo. |

## 7. Análisis

*Pendiente de desarrollo en los avances `PF-P2` (análisis provisional y contraste de explicaciones plausibles) y `PF-P3` (análisis definitivo y revisión de sesgos).*

### Explicaciones alternativas

*Pendiente de elaboración para el segundo avance (`PF-P2`).*

| Explicación | Evidencia a favor | Evidencia en contra | Información pendiente | Valoración |
| --- | --- | --- | --- | --- |
| *Pendiente en P1* | *Pendiente en P1* | *Pendiente en P1* | *Pendiente en P1* | *Pendiente en P1* |

### Revisión de sesgos y contradicciones

*Pendiente de elaboración en los avances `PF-P2` y `PF-P3`.*

## 8. Amenazas, indicadores y comportamientos

*Pendiente de desarrollo (la primera lectura provisional se incorpora en `PF-P2` y se completa en `PF-P3`, respetando la Condición 2 y Condición 3 del alcance aprobado).*

| Indicador o comportamiento | Fuente y fecha | Relación con el caso | Técnica, si procede | Limitación |
| --- | --- | --- | --- | --- |
| *Pendiente en P1* | *Pendiente en P1* | *Pendiente en P1* | *Pendiente en P1* | *Pendiente en P1* |

## 9. Confianza y limitaciones

*Pendiente de elaboración para el tercer avance (`PF-P3`).*

| Valoración | Confianza alta, media o baja | Evidencia y razonamiento | Limitación que puede cambiarla |
| --- | --- | --- | --- |
| *Pendiente en P1* | *Pendiente en P1* | *Pendiente en P1* | *Pendiente en P1* |

## 10. Conclusiones y recomendaciones

### Respuesta al encargo

*Pendiente de elaboración para el tercer avance (`PF-P3`).*

### Prioridades

*Pendiente de elaboración para el tercer avance (`PF-P3`).*

| ID | Recomendación | Hallazgo que la sostiene | Responsable propuesto | Prioridad y plazo orientativo | Comprobación de cumplimiento |
| --- | --- | --- | --- | --- | --- |
| *Pendiente en P1* | *Pendiente en P1* | *Pendiente en P1* | *Pendiente en P1* | *Pendiente en P1* | *Pendiente en P1* |

### Próxima revisión

*Pendiente de elaboración para el tercer avance (`PF-P3`).*

## 11. Referencias

| ID | Autor u organización | Título | Fecha de publicación | URL o referencia | Fecha de consulta |
| --- | --- | --- | --- | --- | --- |
| F-01 | INCIBE (Oficina de Seguridad del Internauta / Ciudadanía) | *[Actualización] Air Europa informa de un ciberataque y comunica a sus clientes cancelar su tarjeta* | 11-10-2023 (Act. 22-03-2024) | https://www.incibe.es/ciudadania/avisos/air-europa-informa-de-un-ciberataque-y-comunica-sus-clientes-cancelar-su-tarjeta | 09-11-2026 |
| F-02 | INCIBE-CERT | *Air Europa sufre un ciberataque y pide a sus clientes que cancelen su tarjeta de crédito (Bitácora de ciberseguridad)* | 30-10-2023 (Act. 22-03-2024) | https://www.incibe.es/incibe-cert/publicaciones/bitacora-de-seguridad/air-europa-sufre-un-ciberataque-y-pide-sus-clientes-que-cancelen-su | 09-11-2026 |
| F-03 | Maldita.es (Maldita Tecnología) | *El ciberataque a Air Europa y la filtración de datos personales de los clientes: preguntas y respuestas* | 11-10-2023 | https://maldita.es/malditatecnologia/20231011/air-europa-ciberataque-datos/ | 09-11-2026 |
| F-04 | Air Europa (comunicado a clientes de octubre de 2023 reproducido por OCU) | *Ciberataque a Air Europa: si estás afectado, cancela tu tarjeta (incluye comunicación remitida por Air Europa a clientes)* | 11-10-2023 | https://www.ocu.org/tecnologia/internet-telefonia/noticias/ciberataque-air-europa | 09-11-2026 |
| F-05 | Air Europa (segundo comunicado a clientes de marzo de 2024 reproducido por FACUA) | *Air Europa informa de una segunda filtración de datos personales de clientes sufrida en el ciberataque de octubre (reproducción del correo oficial de la aerolínea)* | 22-03-2024 | https://facua.org/noticias/air-europa-informa-de-una-segunda-filtracion-de-datos-personales-de-clientes-sufrida-en-el-ciberataque-de-octubre/ | 09-11-2026 |

## 12. Anexos

### Anexo A. Evaluación de fuentes y evidencias

El registro estructurado de las cinco fuentes iniciales se encuentra en [`registros/fuentes.csv`](registros/fuentes.csv) y la relación de integridad en [`registros/integridad.csv`](registros/integridad.csv). En esta fase `PF-P1` todas las consultas se han efectuado sobre publicaciones web oficiales y verificadas sin descarga de muestras.

### Anexo B. Bitácora y cambios del alcance

El detalle cronológico de las consultas y decisiones ejecutadas hasta el primer avance se documenta en [`registros/bitacora.csv`](registros/bitacora.csv). Las condiciones impuestas en la resolución de aprobación del 4 de noviembre de 2026 se han incorporado en los apartados 2, 3 y 5 de este informe.

### Anexo C. Aplicación de los temas

En este avance `PF-P1` se han aplicado el **Tema 1** (definición y ajuste del requerimiento de inteligencia conforme a las condiciones aprobadas), el **Tema 2** (evaluación legal, ética y de OPSEC, fijando exclusiones de datos PCI-DSS/PII y condiciones de parada) y el inicio del **Tema 3** (identificación y clasificación de fuentes institucionales, primarias reproducidas y secundarias). El desglose completo de los ocho temas se recoge en [`seguimiento.md`](seguimiento.md) y se completará en `PF-P3`.

### Anexo D. Seguimiento y herramientas

La evolución del trabajo entre `PF-TEMA` y `PF-P1` y el cumplimiento de las condiciones del docente se detallan en [`seguimiento.md`](seguimiento.md).

### Anexo E. Autoría, colaboración y uso de IA

El trabajo es de elaboración individual. La declaración y el registro acumulado de uso de inteligencia artificial conforme al Nivel C de la asignatura se documentan en [`registro-ia.md`](registro-ia.md) y sus evidencias en la carpeta `ia/`.
