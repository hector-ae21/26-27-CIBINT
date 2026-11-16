# PF-TEMA · Propuesta individual

**Estudiante:** Sergio Rodríguez López  
**Fecha y versión:** 27 de octubre de 2026, v0.1  
**Título provisional:** Incidente de ciberseguridad en Air Europa (2023-2024): evolución del alcance comunicado y pautas de protección al cliente ante exposición de datos

**Modalidad:** Incidente documentado  
**Canal de entrega:** Repositorio público mediante pull request  
**Número de palabras y método de recuento:** ~720 palabras (cuerpo del documento sin contar la tabla de referencias ni el apartado 8, calculado mediante contador de palabras estándar `wc -w`)

## 1. Caso real y situación de partida

El 10 de octubre de 2023, la aerolínea Air Europa notificó la detección de un incidente de ciberseguridad en su entorno tecnológico de pagos online que afectó a la confidencialidad de los datos de tarjetas bancarias de determinados clientes (número de tarjeta, fecha de caducidad y código CVV), recomendando inicialmente su bloqueo y sustitución preventiva. Posteriormente, en marzo de 2024, como resultado de la investigación forense continuada, la compañía emitió una ampliación informativa indicando que un segundo conjunto de datos personales y de contacto (nombres, documentos de identidad, correos electrónicos y teléfonos) también se había visto expuesto durante el incidente de octubre de 2023.

Se encuentra confirmado institucionalmente (mediante los avisos de INCIBE e INCIBE-CERT) tanto el hecho de las dos fases de notificación como las recomendaciones preventivas emitidas en cada momento. Por el contrario, permanecen como cuestiones a contrastar la trazabilidad exacta entre las distintas versiones de los comunicados, el desfase temporal entre el incidente y la segunda notificación, y la ausencia de confirmación pública sobre el vector técnico inicial o sobre un uso fraudulento masivo confirmado por la entidad.

## 2. Destinatario y decisión

| Campo | Propuesta |
| --- | --- |
| Destinatario | Dirección de Atención al Cliente y Prevención de Fraude de una compañía del sector transporte o comercio electrónico |
| Condición del destinatario | Supuesto académico |
| Decisión que necesita tomar | Determinar qué criterios de comunicación escalonada y qué recomendaciones de protección trasladar a los usuarios afectados cuando el alcance conocido de una brecha evoluciona de datos de pago a datos identificativos, sin exceder la evidencia confirmada en cada fase |
| Utilidad del informe | Proporcionar un marco basado en evidencia documental para estructurar avisos a clientes, alinear los mensajes de soporte con las alertas de organismos oficiales (INCIBE) y priorizar advertencias contra fraudes derivados (*phishing*, *smishing* o cargos no autorizados) según el tipo de dato expuesto |

## 3. Preguntas de inteligencia

| ID | Pregunta principal | Decisión a la que contribuye |
| --- | --- | --- |
| PI-01 | ¿Qué hechos se dieron por confirmados y qué aspectos quedaron sin acreditar en cada una de las fases de comunicación oficial del incidente de Air Europa entre octubre de 2023 y marzo de 2024? | Definir qué afirmaciones puede sostener un equipo de atención al cliente en cada etapa de una investigación en curso sin especular |
| PI-02 | ¿Cómo variaron las recomendaciones preventivas dirigidas a los usuarios entre la primera notificación (centrada en medios de pago) y la actualización posterior (ampliada a datos personales y de contacto)? | Priorizar las medidas de protección al cliente según la tipología de información comprometida en cada momento |
| PI-03 | ¿Qué riesgos de fraude secundario (*spearphishing*, suplantación de identidad o uso de tarjetas) justifican las fuentes institucionales a partir de los datos expuestos y qué limitaciones existen para atribuir incidentes posteriores a esta brecha? | Orientar los protocolos de verificación de identidad y las alertas antifraude sin asumir relaciones causales no demostradas |

## 4. Alcance y exclusiones

| Límite | Propuesta |
| --- | --- |
| Organización, servicio, campaña o identidad propia | Air Europa; específicamente el incidente en su sistema de comercio electrónico y pasarela de venta web y las comunicaciones derivadas hacia los clientes |
| Periodo de los hechos | Del 10 de octubre de 2023 (primera notificación pública del incidente) al 31 de marzo de 2024 (cierre del periodo de actualización de avisos de INCIBE sobre la ampliación del alcance) |
| Corte previsto de información, con zona horaria | 1 de diciembre de 2026 a las 23:59 (`Europe/Madrid`) |
| Territorio, cuando sea relevante | España y Unión Europea (marco normativo RGPD / LOPDGDD e intervención de INCIBE y AEPD) |
| Fuentes y acciones propuestas | Consulta documental de avisos oficiales de INCIBE e INCIBE-CERT, comunicados institucionales de Air Europa reproducidos en fuentes verificables, análisis de asociaciones de consumidores y resoluciones públicas si existieran |
| Datos que necesitas conservar | Fechas de publicación y actualización, textos de comunicados institucionales, tipologías de datos declaradas como afectadas y recomendaciones oficiales de mitigación |
| Datos que no se recogerán | Números de tarjetas bancarias, datos personales de pasajeros o clientes afectados, correos privados de terceros ni muestras de bases de datos filtradas |
| Autorización disponible y condiciones; si procede, referencia privada al documento | Práctica académica documental sobre fuentes abiertas e institucionales; sujeta a la aprobación del alcance por el docente de la asignatura |
| Motivo de entrega privada, si es un caso personal; canal acordado y acceso habilitado para la revisión | No aplica (modalidad ordinaria de entrega pública en repositorio del curso) |
| Acciones expresamente excluidas | Escaneo o interacción técnica con la infraestructura web de Air Europa, acceso a foros delictivos o *dark web*, descarga de filtraciones y contacto con personal, soporte o clientes de la aerolínea |
| Condición de parada y procedimiento de consulta | Si durante la búsqueda documental aparecieran datos personales reales de clientes o números de tarjeta en alguna fuente secundaria, se detendrá su registro, no se almacenará la evidencia y se consultará por el canal privado de la asignatura |

## 5. Viabilidad y referencias iniciales

| Referencia | Autor u organización | Título y URL | Fecha de publicación y consulta | Primaria o secundaria | Qué pregunta ayuda a responder |
| --- | --- | --- | --- | --- | --- |
| F-01 | INCIBE (Oficina de Seguridad del Internauta / Ciudadanía) | *Air Europa informa de un ciberataque y comunica a sus clientes cancelar su tarjeta* — https://www.incibe.es/ciudadania/avisos/air-europa-informa-de-un-ciberataque-y-comunica-sus-clientes-cancelar-su-tarjeta | Publicación: 11/10/2023 (Act. 22/03/2024) · Consulta: 27/10/2026 | Institucional / Primaria de referencia | PI-01, PI-02, PI-03 |
| F-02 | INCIBE-CERT | *Air Europa sufre un ciberataque y pide a sus clientes que cancelen su tarjeta de crédito (Bitácora de ciberseguridad)* — https://www.incibe.es/incibe-cert/publicaciones/bitacora-de-seguridad/air-europa-sufre-un-ciberataque-y-pide-sus-clientes-que-cancelen-su | Publicación: 30/10/2023 (Act. 22/03/2024) · Consulta: 27/10/2026 | Institucional / Primaria técnica | PI-01, PI-02 |
| F-03 | Maldita.es (Maldita Tecnología) | *El ciberataque a Air Europa y la filtración de datos personales de los clientes: preguntas y respuestas* — https://maldita.es/malditatecnologia/20231011/air-europa-ciberataque-datos/ | Publicación: 11/10/2023 · Consulta: 27/10/2026 | Secundaria | PI-01, PI-03 |

Existe información suficiente y contrastable porque tanto INCIBE como INCIBE-CERT documentaron la notificación inicial de octubre de 2023 y su actualización de marzo de 2024, conservando el historial de cambios. Un dato importante que probablemente no estará disponible en fuentes abiertas es el informe forense interno con el vector de entrada exacto o la CVE específica explotada en la pasarela. El trabajo limitará ese aspecto declarándolo como información no acreditada públicamente y centrará el Tema 6 (MITRE ATT&CK) en los escenarios preventivos documentados derivados de la exposición (uso de datos para phishing dirigido `T1566` y riesgos sobre cuentas/pagos).

## 6. Plan de trabajo

* **PF-P1 (9 de noviembre):** Incorporación de las condiciones de aprobación del alcance, definición detallada del plan de obtención documental, evaluación legal/OPSEC (exclusión estricta de PII y PCI-DSS) y registro inicial de al menos cinco fuentes verificadas en `fuentes.csv`.
* **PF-P2 (25 de noviembre):** Elaboración de la cronología comparada entre las dos oleadas de notificación (octubre 2023 y marzo 2024), tabla de hallazgos (`hallazgos.csv`), contraste entre comunicados e informaciones en prensa, y formulación de hipótesis alternativas sobre las necesidades de comunicación.
* **PF-P3 (9 de diciembre):** Redacción del borrador completo del informe, desarrollo del análisis de amenazas y escenarios preventivos con MITRE ATT&CK, evaluación del nivel de confianza de las conclusiones, recomendaciones priorizadas para el destinatario y anexos de aplicación de los ocho temas.
* **Trabajo en clase y consultas:** Revisión en el aula de la trazabilidad entre fuentes y hallazgos, y consulta previa al docente en caso de requerir ajustar el alcance de los apartados de infraestructura (Tema 4) dada la naturaleza documental del caso.

## 7. Declaración

He leído las condiciones del proyecto. Esta propuesta no me autoriza a acceder a sistemas, contactar con la organización ni ampliar las acciones por mi cuenta. La recogida sistemática comenzará cuando se apruebe el alcance. Entrego mi declaración de uso o ausencia de IA en `registro-ia.md`.

## 8. Resolución de la propuesta

[Pendiente de revisión y resolución por parte del docente.]
