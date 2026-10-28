# PF-TEMA · Propuesta individual

**Estudiante:** Saúl de Cos Sánchez
**Fecha y versión:** 26-10-2026, v0.1
**Título provisional:** Incidente ADIF–Renfe: ¿qué se sabe sobre los datos de usuarios de Renfe que pudieron verse afectados?

**Modalidad:** Incidente documentado  
**Canal de entrega:** Repositorio público mediante pull request  
**Número de palabras y método de recuento:** 695 palabras, contadas con el script `contar-palabras.mjs`

## 1. Caso real y situación de partida (F-01)

El 25 de septiembre de 2026, Renfe comunicó que estaba investigando un incidente de ciberseguridad relacionado, según los indicios disponibles, con sistemas externos de ADIF que previamente mantenían interconexión con los propios de Renfe, resultando en un posible acceso a información de usuarios.

Según el comunicado, Renfe activó inmediatamente los protocolos de respuesta, se aislaron los entornos afectados y se desplegaron medidas extraordinarias de protección. Los indicios iniciales apuntan a un acceso limitado a nombres y direcciones de correo electrónico, sin identificar evidencias de acceso a datos bancarios, DNI ni métodos de pago.

El comunicado confirma que Renfe reconoció públicamente el incidente y las medidas adoptadas, quedando la causa y el número de usuarios afectados pendientes de confirmación.

El proyecto estudiará qué información pública existe sobre los datos de usuarios que pudieron verse afectados. También se separarán las afirmaciones de Renfe y ADIF de las interpretaciones de fuentes secundarias. La investigación se limitará a fuentes públicas autorizadas y no incluirá accesos, consultas o comprobaciones sobre los sistemas actuales de ADIF o Renfe.

## 2. Destinatario y decisión

| Campo                       | Propuesta                                                                                                                                                                   |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Destinatario                | Responsable de ciberseguridad de Renfe                                                                                                                                      |
| Condición del destinatario  | Supuesto académico                                                                                                                                                          |
| Decisión que necesita tomar | Determinar si la información pública disponible justifica adoptar medidas adicionales de comunicación o protección para los usuarios y qué aspectos deben comprobarse antes |
| Utilidad del informe        | Distinguir los posibles datos afectados en los accesos o publicaciones realmente confirmados y dar una respuesta apropiada para los usuarios                                |

## 3. Preguntas de inteligencia

| ID    | Pregunta principal                                                                                       | Decisión a la que contribuye                                                                |
| ----- | -------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| PI-01 | ¿Qué datos de usuarios de Renfe fueron mencionados públicamente como posiblemente afectados?             | Identificar qué información requeriría tomar medidas de protección si se confirma el acceso |
| PI-02 | ¿Qué evidencias públicas confirman o no el acceso o publicación de esos datos?                           | Determinar qué consecuencias puede haber y cuáles continúan siendo posibilidades            |
| PI-03 | ¿Qué medidas de comunicación o protección para los usuarios se justifican con la información confirmada? | Adoptar una respuesta proporcionada sin presentar como ciertos efectos no demostrados       |

## 4. Alcance y exclusiones

| Límite                                                                                                 | Propuesta                                                                                                                                                              |
| ------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Organización, servicio, campaña o identidad propia                                                     | Renfe y ADIF                                                                                                                                                           |
| Periodo de los hechos                                                                                  | Del 25 de septiembre al 30 de noviembre de 2026.                                                                                                                       |
| Corte previsto de información, con zona horaria                                                        | 30 de noviembre de 2026, 23:59, `Europe/Madrid`.                                                                                                                       |
| Territorio, cuando sea relevante                                                                       | España.                                                                                                                                                                |
| Fuentes y acciones propuestas                                                                          | Comunicados de Renfe, ADIF y organismos públicos, junto con fuentes secundarias.                                                                                       |
| Datos que necesitas conservar                                                                          | Autor, título, URL, fechas, afirmaciones sobre los datos posiblemente afectados y relación entre fuentes.                                                              |
| Datos que no se recogerán                                                                              | Datos personales de usuarios, credenciales, muestras filtradas, información interna o datos de trabajadores y terceros no necesarios.                                  |
| Autorización disponible y condiciones; si procede, referencia privada al documento                     |                                                                                                                                                                        |
| Motivo de entrega privada, si es un caso personal; canal acordado y acceso habilitado para la revisión | No aplica                                                                                                                                                              |
| Acciones expresamente excluidas                                                                        | Escaneos, consultas técnicas a la infraestructura, acceso a filtraciones, contacto con las organizaciones o posibles actores y tratamiento de datos personales.        |
| Condición de parada y procedimiento de consulta                                                        | Si aparece información personal, material filtrado o una acción que requiera acceder a sistemas, se detendrá la consulta y se avisará al docente por el canal privado. |

## 5. Viabilidad y referencias iniciales

| Referencia | Autor u organización | Título y URL                                                                                                                                                                                                                                     | Fecha de publicación y consulta                       | Primaria o secundaria | Qué pregunta ayuda a responder |
| ---------- | -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------- | --------------------- | ------------------------------ |
| F-01       | Renfe                | [Renfe investiga un incidente de ciberseguridad vinculado a sistemas externos de ADIF](https://grupo.renfe.com/es/es/sala-de-prensa/noticias/2026/09/renfe-investiga-un-incidente-de-ciberseguridad-vinculado-a-sistemas-externos-de-adif)       | Publicación: 25-09-2026; consulta: 26-10-2026         | Primaria              | PI-01, PI-02 y PI-03           |
| F-02       | ADIF                 | [Información sobre incidentes de ciberseguridad](https://www.adif.es/informacion-incidente-ciberseguridad)                                                                                                                                       | Publicación: sin fecha indicada; consulta: 26-10-2026 | Primaria              | PI-02 y PI-03                  |
| F-03       | El País              | [Renfe investiga un ciberataque vinculado a sistemas de Adif que expuso datos básicos de usuarios](https://elpais.com/economia/2026-09-25/renfe-investiga-un-ciberataque-vinculado-a-sistemas-de-adif-que-expuso-datos-basicos-de-usuarios.html) | Publicación: 25-09-2026; consulta: 26-10-2026         | Secundaria            | PI-01, PI-02 y PI-03           |

F-01 y F-02 recogen las versiones oficiales de Renfe y ADIF. F-03 es una fuente secundaria que reúne información de ambas, aunque depende principalmente de sus declaraciones. Estas referencias permiten iniciar el análisis.

## 6. Plan de trabajo

En el P1, se redactará el plan, se hará una evaluación de los límites legales y de OPSEC relacionados con el tema, se revisarán las fuentes iniciales más profundamente y se redactarán los primeros hallazgos.

En el P2, se hará una cronología detallada, se contrastarán las fuentes, se determinará qué información está confirmada y cuál está pendiente.

En el P3, se completará el borrador del informe y se redactarán las conclusiones y recomendaciones finales, junto con limitaciones.

## 7. Declaración

He leído las condiciones del proyecto. Esta propuesta no me autoriza a acceder a sistemas, contactar con la organización ni ampliar las acciones por mi cuenta. La recogida sistemática comenzará cuando se apruebe el alcance. Entrego mi declaración de uso o ausencia de IA en `registro-ia.md`.

## 8. Resolución de la propuesta

[No completar como si fuera una aprobación. Después de recibirla, anota su fecha, las condiciones indicadas y la versión del alcance aprobada.]

[Volver a tema y alcance](../../../../proyecto-final/01-tema-y-alcance.md) · [Calendario](../../../../proyecto-final/02-proceso-y-entregas.md)
