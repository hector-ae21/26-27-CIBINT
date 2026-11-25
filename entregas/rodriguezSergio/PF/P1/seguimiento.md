# PF · Seguimiento del proyecto

**Estudiante:** Sergio Rodríguez López  
**Caso y título:** Incidente de ciberseguridad en Air Europa (2023-2024): evolución del alcance comunicado y pautas de protección al cliente ante exposición de datos  
**Hito:** P1  
**Fecha y versión del informe:** 9 de noviembre de 2026 (revisión 25 de noviembre de 2026), v0.2  
**Alcance aprobado:** Aprobado con condiciones el 4 de noviembre de 2026 (sobre la versión del alcance del 27 de octubre de 2026). Condiciones: (1) Añadir al menos una fuente primaria de Air Europa (comunicado o correo a clientes reproducido en fuente verificable); (2) Describir los riesgos de fraude secundario (`PI-03`) como posibilidades justificadas por las fuentes, sin atribuir a esta brecha fraudes posteriores concretos; (3) Limitar el análisis técnico del Tema 4 a la información conocida sobre el incidente, sin consultar la infraestructura actual de Air Europa.

**Canal autorizado:** Pull request público  
**Número de palabras del cuerpo y método de recuento:** 2.184 palabras en el cuerpo de `informe.md` (apartados 1 a 10; límite máximo de P1: 2.500 palabras), calculado mediante `node proyecto-final/contar-palabras.mjs entregas/rodriguezSergio/PF/P1/informe.md`.  
**Referencia de la entrega y versión:** Pull request `[PF-P1] rodriguezSergio`, versión v0.2 (`entregas/rodriguezSergio/PF/P1/`).

## Estado de las preguntas

| Pregunta | Qué puede responderse ya | Evidencias | Información pendiente | Próximo paso permitido |
| --- | --- | --- | --- | --- |
| PI-01 | Está confirmado que en octubre de 2023 Air Europa notificó solo exposición de datos de tarjetas (número, caducidad y CVV) negando afectación a otros datos personales (`H-01`), y que en marzo de 2024 comunicó que el análisis forense del mismo incidente reveló exposición de datos identificativos y de contacto (`H-02`). | `F-01`, `F-02`, `F-03`, `F-04`, `F-05` | Contrastar literalmente los fragmentos de ambos comunicados y estructurar la cronología con las cuatro fechas (hecho, publicación, actualización y consulta). | Completar la matriz comparativa literal y la cronología en `PF-P2`. |
| PI-02 | Se observa un cambio desde recomendaciones de anulación inmediata de medios de pago en octubre de 2023 hacia medidas de alerta frente a suplantación e ingeniería social en marzo de 2024 (`H-03`). | `F-01`, `F-04`, `F-05` | Desglosar cada recomendación por emisor (Air Europa, INCIBE, asociaciones de consumidores) y fase. | Construir tabla comparativa de recomendaciones por fase en `PF-P2`. |
| PI-03 | Las fuentes justifican como posibilidad preventiva el riesgo de *phishing*, *smishing*, *vishing* y cargos no autorizados por los datos expuestos, pero declaran la ausencia de fraude acreditado (`H-04`). | `F-01`, `F-02`, `F-03`, `F-04`, `F-05` | Relacionar estos escenarios preventivos con técnicas de MITRE ATT&CK (Tema 6) sin atribuir fraudes concretos. | Desarrollar la lectura preliminar de amenazas en `PF-P2`. |

## Correcciones y decisiones

| Hito o fecha | Observación recibida o problema detectado | Cambio realizado y motivo | Apartado o registro | Estado |
| --- | --- | --- | --- | --- |
| 04-11-2026 | Condición 1 del docente: añadir fuente con comunicado o correo de Air Europa reproducido en fuente verificable. | Incorporadas `F-04` (OCU, resumen del comunicado de octubre de 2023) y `F-05` (FACUA, resumen y citas del comunicado de marzo de 2024), sumadas a `F-03` (Maldita.es, citas literales del correo de octubre). | Apartados 3, 5, 6 y 11 de `informe.md` y `registros/fuentes.csv` | Aplicado |
| 04-11-2026 | Condición 2 del docente: tratar los riesgos de fraude secundario (`PI-03`) como posibilidades justificadas sin atribuir fraudes concretos. | Acotada la redacción de `PI-03`, tabla de alcance y `H-04` exclusivamente a escenarios preventivos documentados. | Apartados 2, 3 y 6 de `informe.md` | Aplicado |
| 04-11-2026 | Condición 3 del docente: limitar el Tema 4 a la información conocida del incidente sin consultar la infraestructura actual de Air Europa. | Excluida del alcance cualquier consulta DNS, CT logs o Shodan sobre la infraestructura actual de la aerolínea. | Apartado 3 de `informe.md` y tabla de temas de `seguimiento.md` | Aplicado |
| 23-11-2026 | Revisión docente de `PF-P1`: (1-2) PR borraba archivos ajenos por desactualización del fork; (3) restaurar resolución en `TEMA/propuesta.md`; (4) usar encabezados exactos de plantillas CSV; (5) detallar zona horaria, herramienta y términos de búsqueda en bitácora; (6) precisar dependencia de INCIBE/INCIBE-CERT y si OCU/FACUA resumen o citan literalmente; (7) unificar recuento con `contar-palabras.mjs`. | Sincronizada la rama sobre `upstream/main` restaurando archivos ajenos; ajustados los encabezados de los 4 CSV; completada `bitacora.csv` con consultas exactas; aclarada la dependencia de `F-01`/`F-02` y el carácter de resumen/cita de `F-04`/`F-05`; unificado recuento a 2.184 palabras. | Toda la rama `pf-p1-rodriguezSergio` (`informe.md`, `seguimiento.md`, `registros/*.csv`) | Aplicado |

## Cambios de alcance

| Fecha | Cambio propuesto | Por qué hace falta | Aprobación y condiciones | Versión a la que se aplica |
| --- | --- | --- | --- | --- |
| 04-11-2026 | Ajuste del alcance inicial para incorporar las 3 condiciones de la resolución de `PF-TEMA` (inclusión de fuentes con comunicados de Air Europa, acotación preventiva de `PI-03` y exclusión de consultas a infraestructura actual en el Tema 4). | Requerido por el docente en la resolución de aprobación de la propuesta. | Aprobado con condiciones el 04-11-2026 sobre el alcance del 27-10-2026. | v0.2 (`PF-P1`) y siguientes |

Un cambio pendiente de aprobación no se ejecuta.

## Trabajo realizado en clase y entre sesiones

| Fecha | Trabajo realizado | Resultado propio que se puede revisar | Archivo o referencia |
| --- | --- | --- | --- |
| 04-11-2026 | Revisión de la resolución de `PF-TEMA` y análisis de las tres condiciones de aprobación. | Actualización de condiciones en el plan y criterios de búsqueda para `F-04` y `F-05`. | `seguimiento.md`, `registros/bitacora.csv` |
| 06-11-2026 | Búsqueda y verificación de fuentes que recogen los correos de Air Europa de octubre de 2023 y marzo de 2024. | Incorporación de `F-04` (OCU) y `F-05` (FACUA) al catálogo de fuentes. | `registros/fuentes.csv`, `registros/bitacora.csv` |
| 08-11-2026 | Redacción de requerimiento, alcance, contexto, evaluación OPSEC y primeras observaciones (`H-01` a `H-05`). | Versión v0.2 de `informe.md` y registro inicial en `hallazgos.csv`. | `informe.md`, `registros/hallazgos.csv` |
| 25-11-2026 | Corrección de observaciones de revisión de `PF-P1` (encabezados CSV, trazabilidad de bitácora, valoración de dependencias y recuento oficial con `contar-palabras.mjs`). | Versión revisada v0.2 en la rama `pf-p1-rodriguezSergio`. | `informe.md`, `seguimiento.md`, `registros/*.csv` |

## Aplicación de los temas

| Tema | Aplicación concreta en este caso o limitación justificada | Apartado y evidencia |
| --- | --- | --- |
| 1. Fundamentos y ciclo | Definición del destinatario, decisión de comunicación escalonada y preguntas `PI-01` a `PI-03` incorporando las condiciones aprobadas. | Apartado 2 de `informe.md` |
| 2. Marco legal, ética y OPSEC | Delimitación estricta de fuentes abiertas, exclusión de datos personales (RGPD) y de tarjetas (PCI-DSS), exclusión de infraestructura actual y condición de parada. | Apartado 3 de `informe.md` |
| 3. Personas, organizaciones y SOCMINT | Identificación y valoración de dependencia entre comunicaciones de Air Europa (`F-03`, `F-04`, `F-05`) y avisos institucionales (`F-01`, `F-02`). | Apartados 4, 5 y 6 de `informe.md` y `registros/fuentes.csv` |
| 4. Infraestructura y exposición | Limitado por la Condición 3 del alcance aprobado: no se consulta la infraestructura actual de Air Europa; se documenta únicamente la referencia pública al entorno de pagos web afectado (`H-05`). | Apartados 3 y 6 de `informe.md` |
| 5. Fuentes cerradas y dark web | No se accede a foros ilícitos ni filtraciones; se registra lo declarado públicamente sobre ausencia de fraude acreditado (`H-04`). | Apartados 3 y 4 de `informe.md` |
| 6. Threat Intelligence y ATT&CK | Pendiente para `PF-P2` y `PF-P3`: ante la falta de CVE pública (`H-05`), se enfocará en escenarios preventivos derivados de los datos expuestos sin atribuir ataques concretos. | Apartado 8 de `informe.md` (previsto en `PF-P2`) |
| 7. Análisis e informe | Separación inicial entre hechos comprobados y cuestiones pendientes; formulación de cinco primeras observaciones verificables (`H-01` a `H-05`). | Apartados 4 y 6 de `informe.md` y `registros/hallazgos.csv` |
| 8. Herramientas y automatización | Estructuración de registros locales en CSV con encabezados normalizados y verificación automática del recuento de palabras con `contar-palabras.mjs`. | Carpeta `registros/` |

## Revisión de esta entrega

- **Qué ha cambiado desde la anterior:** Se ha pasado de la propuesta inicial (`propuesta.md`) a `informe.md` (v0.2), incorporando las 3 condiciones de aprobación del 4 de noviembre, ampliando las fuentes de 3 a 5 (`F-01` a `F-05`) y registrando las primeras 5 observaciones (`H-01` a `H-05`), además de aplicar todas las correcciones técnicas señaladas en la revisión del 23 de noviembre.
- **Limitación más importante:** La ausencia de un informe técnico forense público impide conocer el vector de entrada exacto o el número total de afectados (`H-05`).
- **Decisión que necesitas consultar:** Ninguna adicional; el plan permite continuar hacia `PF-P2`.
- **Trabajo previsto hasta el siguiente hito:** Elaborar la cronología completa con las cuatro fechas (hecho, publicación, actualización y consulta), la comparación literal de ambos comunicados, las explicaciones alternativas y la primera lectura de amenazas en `PF-P2`.

[Volver a proceso y entregas](../../../../proyecto-final/02-proceso-y-entregas.md)