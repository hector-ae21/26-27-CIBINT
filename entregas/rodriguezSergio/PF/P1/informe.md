# Incidente de ciberseguridad en Air Europa (2023-2024): evolución del alcance comunicado y pautas de protección al cliente ante exposición de datos

## Portada y control del documento

| Campo | Contenido |
| --- | --- |
| Autor | Sergio Rodríguez López · Estudiante de Grado en Ingeniería Informática (Ciberinteligencia) |
| Destinatario | Dirección de Atención al Cliente y Prevención de Fraude de una compañía del sector transporte o comercio electrónico (Supuesto académico) |
| Organización o caso estudiado | Air Europa (incidente en el entorno de pagos web de octubre de 2023 y ampliación de alcance sobre datos personales de marzo de 2024) |
| Fecha y versión | 9 de noviembre de 2026 (revisión 25 de noviembre de 2026), v0.2 (Avance PF-P1) |
| Periodo de los hechos | Del 10 de octubre de 2023 al 31 de marzo de 2024 |
| Corte de información | 1 de diciembre de 2026 a las 23:59 (`Europe/Madrid`) |
| Condiciones de difusión | Entrega académica pública mediante repositorio del curso; TLP:CLEAR (información procedente íntegramente de fuentes abiertas e institucionales) |
| Referencia del encargo y alcance aprobado | Propuesta `PF-TEMA` (versión del alcance del 27 de octubre de 2026), aprobada con condiciones el 4 de noviembre de 2026 |

### Historial de versiones

| Versión | Fecha | Cambio principal | Responsable |
| --- | --- | --- | --- |
| 0.1 | 28-10-2026 | Propuesta inicial del tema y delimitación preliminar (`PF-TEMA`) | Sergio Rodríguez López |
| 0.2 | 09-11-2026 | Primer avance (`PF-P1`): incorporación de las 3 condiciones de aprobación, contexto, plan de obtención, evaluación legal/OPSEC, 5 fuentes iniciales y primeras observaciones (corregido el 25-11-2026 conforme a revisión docente) | Sergio Rodríguez López |

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

El objeto de estudio se circunscribe exclusivamente a los hechos documentados y a las comunicaciones dirigidas a los clientes de Air Europa entre el **10 de octubre de 2023** (primera notificación pública sobre tarjetas bancarias) y el **31 de marzo de 2024** (cierre del periodo de actualización de avisos tras la segunda notificación de marzo de 2024 sobre datos identificativos). El corte de información se fija el **1 de diciembre de 2026 a las 23:59 (`Europe/Madrid`)**.

La práctica cuenta con aprobación académica con condiciones de fecha **4 de noviembre de 2026** (sobre la versión del alcance del 27 de octubre de 2026), incorporando tres condiciones obligatorias:

1. **Incorporación de fuentes con comunicaciones de Air Europa (`F-04` y `F-05`):** Se añaden noticias de organizaciones de consumidores (OCU y FACUA) que recogen los avisos remitidos por la aerolínea a sus clientes en octubre de 2023 y marzo de 2024 para contrastar lo comunicado por la entidad y no depender únicamente de INCIBE.
2. **Delimitación analítica de `PI-03`:** Los riesgos de fraude secundario se analizan exclusivamente como escenarios y posibilidades preventivas justificadas por las fuentes, sin atribuir ningún fraude posterior concreto a esta brecha.
3. **Restricción del análisis técnico (Tema 4):** El análisis de infraestructura se limita estrictamente a la información documental publicada sobre el incidente; se excluye consultar o analizar la infraestructura actual de Air Europa.

| Dentro del alcance | Fuera del alcance | Motivo |
| --- | --- | --- |
| Avisos e historial de actualizaciones de INCIBE (`F-01`) e INCIBE-CERT (`F-02`) sobre el incidente. | Infraestructura técnica actual de Air Europa (consultas DNS directas, CT logs, Shodan o visitas a servicios actuales). | Condición expresa nº 3 de aprobación del alcance y normas de OPSEC. |
| Comunicados y correos de Air Europa de octubre de 2023 (`F-03`, `F-04`) y marzo de 2024 (`F-05`) recogidos en fuentes verificables. | Acceso a foros delictivos, *dark web*, mercados clandestinos o descarga de muestras filtradas. | Restricción legal y ética; trabajo estrictamente documental sobre fuentes abiertas autorizadas. |
| Análisis de asociaciones de consumidores y verificadores (`F-03`, `F-04`, `F-05`) sobre pautas de protección. | Recopilación de datos personales reales de pasajeros (PII), números de tarjetas (PAN/CVV) o identificación de víctimas. | Cumplimiento de normativa RGPD/LOPDGDD y minimización de datos. |
| Estudio de riesgos de fraude derivado como posibilidades preventivas (`PI-03`). | Atribución de campañas de *phishing* o fraudes posteriores concretos a esta brecha o atribución a actores de amenaza sin evidencia oficial. | Condición expresa nº 2 de aprobación del alcance y rigor metodológico. |

### Datos, seguridad y condiciones de parada

* **Datos conservados:** Metadatos de las publicaciones (autor, organización, título, URL, fechas de publicación, actualización y consulta), citas y resúmenes de comunicados institucionales, categorías abstractas de datos expuestos y recomendaciones preventivas.
* **Datos excluidos:** Nombres de clientes afectados, correos personales de pasajeros, documentos de identidad y numeraciones de tarjetas.
* **Evaluación legal y de OPSEC:** Consulta pasiva de documentos públicos en organismos oficiales y organizaciones de consumidores/medios verificados, sin contacto con la entidad ni reconocimiento técnico sobre activos de red.
* **Condición de parada:** Si apareciese una captura sin censurar con datos personales reales o números de tarjeta, se detendrá la extracción, no se guardará copia y se notificará al docente por el canal privado de la asignatura.

## 4. Contexto y cronología

### Contexto documentado del caso

El incidente estudiado afecta a Air Europa y se caracteriza por haberse comunicado en **dos etapas diferenciadas separadas por cinco meses** a raíz de un suceso detectado internamente en septiembre de 2023:

1. **Primera etapa (Octubre de 2023 · Entorno de pagos):** El 10 de octubre de 2023, Air Europa remitió un correo electrónico a clientes afectados (`F-03`, `F-04`) informando de un ataque de ciberseguridad en su entorno de pagos web. El 11 de octubre de 2023, INCIBE publicó su aviso (`F-01`), indicando que la detección interna ocurrió el 29 de septiembre de 2023. En esta fase, la compañía afirmó que la filtración afectaba únicamente a datos de tarjetas bancarias (número, fecha de caducidad y CVV) y aseguró que no se había visto comprometido ningún otro dato personal (`F-03`, `F-04`).
2. **Segunda etapa (Marzo de 2024 · Ampliación a datos personales):** El 21 de marzo de 2024, tras continuar la investigación forense del incidente de octubre de 2023, Air Europa envió una segunda comunicación (`F-05`), reflejada en la actualización del 22 de marzo de 2024 de INCIBE (`F-01`) e INCIBE-CERT (`F-02`), notificando la exposición adicional de datos identificativos y de contacto (nombre, apellidos, DNI/pasaporte, nacionalidad, fecha de nacimiento, teléfono, correo electrónico y número *Air Europa SUMA*), excluyendo contraseñas.

### Separación entre hechos conocidos y afirmaciones pendientes

* **Hechos respaldados documentalmente:** La notificación inicial del 10-10-2023 (`F-03`, `F-04`); la afirmación inicial de que solo afectaba a tarjetas y ningún otro dato personal (`F-03`, `F-04`); la ampliación del 21/22-03-2024 sobre datos personales (`F-01`, `F-02`, `F-05`); y el giro de recomendaciones desde la cancelación de tarjetas hacia la alerta ante ingeniería social (`F-01`, `F-04`, `F-05`).
* **Afirmaciones pendientes o no acreditadas:** El vector técnico inicial o vulnerabilidad CVE específica (`F-01`, `F-02`); el número exacto de clientes afectados; y la existencia de uso fraudulento confirmado, dado que la aerolínea declaró no tener constancia de ello (`F-02`, `F-03`, `F-05`).

### Cronología preliminar (Avance P1)

*Nota: La cronología completa con las cuatro fechas (hecho, publicación, actualización y consulta) y el contraste literal de comunicados se desarrollará en `PF-P2`.*

| Fecha y zona horaria del hecho | Publicación u observación | Hecho o afirmación atribuida | Fuente | Limitación |
| --- | --- | --- | --- | --- |
| 29-09-2023 (`Europe/Madrid`) | Publicado el 11-10-2023 | Detección interna por Air Europa del acceso no autorizado en su entorno de pagos web, según el aviso de INCIBE. | `F-01` | No consta públicamente desde qué fecha previa estuvo activo el acceso. |
| 10-10-2023 (`Europe/Madrid`) | Observado el 10/11-10-2023 | Air Europa remite el primer correo a clientes afectados informando sobre tarjetas (número, caducidad, CVV), negando otros datos personales y pidiendo cancelar la tarjeta. | `F-03`, `F-04` | Conocido mediante citas y resúmenes en prensa y asociaciones de consumidores. |
| 11-10-2023 (`Europe/Madrid`) | Publicado el 11-10-2023 | INCIBE publica la alerta inicial recomendando bloquear/sustituir la tarjeta usada en la web y revisar movimientos. | `F-01` | Depende de la información preliminar trasladada por Air Europa. |
| 21-03-2024 (`Europe/Madrid`) | Publicado el 21/22-03-2024 | Air Europa envía un segundo comunicado informando de que la investigación forense del incidente de octubre de 2023 reveló exposición de datos personales y de contacto. | `F-05`, `F-01` | No se explica públicamente la causa técnica del desfase de cinco meses. |
| 22-03-2024 (`Europe/Madrid`) | Actualizado el 22-03-2024 | INCIBE e INCIBE-CERT actualizan sus publicaciones añadiendo los datos personales expuestos y pautas frente a *phishing* y *vishing*. | `F-01`, `F-02` | Mantiene sin publicar indicadores técnicos (IoC) ni CVE. |

## 5. Fuentes y método

### Plan de fuentes y consultas

Se ha constituido un registro inicial de **cinco fuentes pertinentes (`F-01` a `F-05`)** vinculadas a las preguntas de inteligencia, evaluando expresamente su procedencia y dependencia:

| Fuente o grupo | Pregunta que cubre | Criterio de selección, dependencia y evaluación | Limitación |
| --- | --- | --- | --- |
| **Organismos institucionales:** INCIBE (`F-01`) e INCIBE-CERT (`F-02`). | `PI-01`, `PI-02`, `PI-03` | Fuentes institucionales de referencia en España, pero **no son la fuente primaria del incidente**: dependen de lo que notificó Air Europa. Además, la bitácora de INCIBE-CERT (`F-02`) agrega enlaces a cobertura de medios del 10-10-2023 (*El País*, *El Confidencial*, *La Vanguardia*, *Xataka*). | No aportan verificación forense independiente ni publican IoC o CVE. |
| **Medios y consumidores con comunicados de Air Europa:** Maldita.es (`F-03`), OCU (`F-04`) y FACUA (`F-05`). | `PI-01`, `PI-02`, `PI-03` | Cumplen la Condición 1 de aprobación del alcance. `F-03` reproduce citas literales entrecomilladas del correo del 10-10-2023 (*«los datos sustraídos son únicamente los relacionados con las tarjetas bancarias y que no se ha visto afectado ningún otro dato personal»*); `F-04` (OCU) **resume** el comunicado inicial sin transcribirlo íntegramente; y `F-05` (FACUA) **resume** el comunicado del 21-03-2024 incluyendo citas parciales (*«investigación forense»* y exclusión de contraseñas y tarjetas). | Ninguna publica una captura íntegra de cabecera a pie del correo original; su comparación literal detallada se abordará en `PF-P2`. |

### Ubicación de registros y convención de identificadores

* **Registro de fuentes:** `registros/fuentes.csv` (`F-01` a `F-05`), siguiendo los encabezados oficiales de `proyecto-final/plantillas/fuentes.csv`.
* **Registro de hallazgos:** `registros/hallazgos.csv` (`H-01` a `H-05`), siguiendo los encabezados de `proyecto-final/plantillas/hallazgos.csv`.
* **Bitácora de trabajo:** `registros/bitacora.csv`, con zona horaria, herramienta y términos de búsqueda exactos, siguiendo `proyecto-final/plantillas/bitacora.csv`.
* **Registro de integridad:** `registros/integridad.csv`, siguiendo `proyecto-final/plantillas/integridad.csv`.

## 6. Resultados y evidencias

### Primeras observaciones verificadas (Avance P1)

| Hallazgo | Pregunta | Observación verificable | Fuente y fecha | Qué no demuestra |
| --- | --- | --- | --- | --- |
| H-01 | PI-01 | En la comunicación inicial del 10-10-2023, Air Europa informó que el ataque en su entorno de pagos web solo comprometió datos de tarjetas (número, caducidad y CVV) y afirmó que *«no se ha visto afectado ningún otro dato personal»*, pese a que la investigación continuaba abierta. | `F-03` (11-10-2023), `F-04` (11-10-2023) | No demuestra que la compañía ocultara información deliberadamente; acredita lo afirmado antes de concluir el análisis forense. |
| H-02 | PI-01 | El 21-03-2024, Air Europa envió una segunda comunicación (recogida por INCIBE el 22-03-2024) indicando que la investigación forense posterior del incidente de octubre de 2023 reveló la exposición de datos identificativos y de contacto (nombre, DNI/pasaporte, fecha de nacimiento, nacionalidad, teléfono, correo y nº SUMA), sin afectar a contraseñas. | `F-01` (Act. 22-03-2024), `F-02` (Act. 22-03-2024), `F-05` (21-03-2024) | No demuestra un segundo ciberataque independiente en 2024, sino una ampliación del alcance conocido del suceso de 2023. |
| H-03 | PI-02 | Las recomendaciones preventivas cambiaron de la cancelación/sustitución inmediata de la tarjeta en octubre de 2023 a pautas de vigilancia y verificación frente a ingeniería social (*phishing*, *smishing*, *vishing*) en marzo de 2024. | `F-01` (11-10-2023 y Act. 22-03-2024), `F-04`, `F-05` | No demuestra qué porcentaje de clientes ejecutó las medidas ni su eficacia real. |
| H-04 | PI-03 | Las fuentes institucionales y los comunicados de la compañía justifican como posibilidades preventivas el riesgo de *phishing*, *smishing*, *vishing* o uso indebido de tarjetas según los datos expuestos, pero señalan que no consta evidencia acreditada de uso fraudulento. | `F-01`, `F-02`, `F-03`, `F-04`, `F-05` | Conforme a la Condición 2 del alcance, no permite atribuir ningún fraude posterior concreto sufrido por un cliente a esta brecha. |
| H-05 | PI-01 | Ninguna de las fuentes consultadas publica el vector técnico inicial, una vulnerabilidad CVE concreta ni la cifra total de afectados. | `F-01`, `F-02`, `F-04`, `F-05` | Impide realizar atribuciones técnicas o asociar el caso a una CVE, acotando el Tema 4 y el Tema 6 al plano documental y preventivo. |

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
| F-04 | OCU (Organización de Consumidores y Usuarios) | *Filtración de datos en Air Europa: cancela tu tarjeta (resumen del comunicado de Air Europa a clientes)* | 11-10-2023 | https://www.ocu.org/tecnologia/internet-telefonia/noticias/ciberataque-air-europa | 09-11-2026 |
| F-05 | FACUA (Consumidores en Acción) | *Air Europa sufre un nuevo acceso ilícito a datos personales de sus clientes, aunque asegura que no hay contraseñas ni tarjetas afectadas (resumen y citas del comunicado de Air Europa)* | 21-03-2024 | https://facua.org/noticias/air-europa-sufre-un-nuevo-acceso-ilicito-a-datos-personales-de-sus-clientes-aunque-asegura-que-no-hay-contrasenas-ni-tarjetas-afectadas/ | 09-11-2026 |

## 12. Anexos

### Anexo A. Evaluación de fuentes y evidencias

El registro estructurado de las cinco fuentes iniciales se encuentra en [`registros/fuentes.csv`](registros/fuentes.csv) y la relación de integridad en [`registros/integridad.csv`](registros/integridad.csv). En esta fase `PF-P1` todas las consultas se han efectuado sobre publicaciones web oficiales y verificadas sin descarga de muestras.

### Anexo B. Bitácora y cambios del alcance

El detalle cronológico de las consultas y decisiones ejecutadas hasta el primer avance se documenta en [`registros/bitacora.csv`](registros/bitacora.csv). Las condiciones impuestas en la resolución de aprobación del 4 de noviembre de 2026 se han incorporado en los apartados 2, 3 y 5 de este informe.

### Anexo C. Aplicación de los temas

En este avance `PF-P1` se han aplicado el **Tema 1** (definición del requerimiento), el **Tema 2** (evaluación legal, ética y de OPSEC) y el inicio del **Tema 3** (clasificación y dependencia de fuentes). El desglose completo de los ocho temas se recoge en [`seguimiento.md`](seguimiento.md) y se completará en `PF-P3`.

### Anexo D. Seguimiento y herramientas

La evolución del trabajo entre `PF-TEMA` y `PF-P1` y el cumplimiento de las condiciones del docente se detallan en [`seguimiento.md`](seguimiento.md).

### Anexo E. Autoría, colaboración y uso de IA

El trabajo es de elaboración individual. La declaración y el registro acumulado de uso de inteligencia artificial conforme al Nivel C de la asignatura se documentan en [`registro-ia.md`](registro-ia.md) y sus evidencias en la carpeta `ia/`.