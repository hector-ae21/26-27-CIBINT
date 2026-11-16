# PF · Seguimiento del proyecto

**Estudiante:** Sergio Rodríguez López  
**Caso y título:** Incidente de ciberseguridad en Air Europa (2023-2024): evolución del alcance comunicado y pautas de protección al cliente ante exposición de datos  
**Hito:** P1  
**Fecha y versión del informe:** 9 de noviembre de 2026, v0.2  
**Alcance aprobado:** Aprobado con condiciones el 4 de noviembre de 2026 (sobre la versión del alcance del 27 de octubre de 2026). Condiciones: (1) Añadir al menos una fuente primaria de Air Europa (comunicado o correo a clientes reproducido en fuente verificable); (2) Describir los riesgos de fraude secundario (`PI-03`) como posibilidades justificadas por las fuentes, sin atribuir a esta brecha fraudes posteriores concretos; (3) Limitar el análisis técnico del Tema 4 a la información conocida sobre el incidente, sin consultar la infraestructura actual de Air Europa.

**Canal autorizado:** Pull request público  
**Número de palabras del cuerpo y método de recuento:** ~1.980 palabras en el cuerpo de `informe.md` (sin contar portada, índice, referencias ni anexos; límite máximo de P1: 2.500 palabras), calculado con `wc -w`.  
**Referencia de la entrega y versión:** Pull request `[PF-P1] rodriguezSergio`, versión v0.2 (`entregas/rodriguezSergio/PF/P1/`).

## Estado de las preguntas

| Pregunta | Qué puede responderse ya | Evidencias | Información pendiente | Próximo paso permitido |
| --- | --- | --- | --- | --- |
| PI-01 | Está confirmado que en octubre de 2023 Air Europa notificó solo exposición de datos de tarjetas (número, caducidad y CVV) negando afectación a otros datos personales (`H-01`), y que en marzo de 2024 comunicó que el análisis forense del mismo incidente reveló exposición de datos identificativos y de contacto (`H-02`). | `F-01`, `F-02`, `F-03`, `F-04`, `F-05` | Contrastar en detalle las diferencias de redacción entre el primer correo, el segundo correo y las notas de prensa para elaborar la cronología completa. | Completar la matriz comparativa de afirmaciones por fecha en el avance `PF-P2`. |
| PI-02 | Se observa un cambio claro desde recomendaciones de anulación inmediata de medios de pago en la primera fase hacia medidas de alerta permanente frente a suplantación e ingeniería social en la segunda (`H-03`). | `F-01`, `F-04`, `F-05` | Desglosar pormenorizadamente cada medida recomendada por la aerolínea frente a las añadidas por INCIBE y asociaciones de consumidores. | Construir tabla comparativa de recomendaciones por fase y emisor en `PF-P2`. |
| PI-03 | Las fuentes justifican como posibilidad preventiva el riesgo de *phishing*, *smishing*, *vishing* y cargos no autorizados por la combinación de datos expuestos, pero declaran la ausencia de fraude masivo acreditado (`H-04`). | `F-01`, `F-02`, `F-03`, `F-04`, `F-05` | Relacionar estos escenarios preventivos con técnicas de MITRE ATT&CK (Tema 6) manteniendo la restricción de no atribuir incidentes posteriores reales. | Desarrollar la lectura preliminar de amenazas y escenarios preventivos en `PF-P2`. |

## Correcciones y decisiones

| Hito o fecha | Observación recibida o problema detectado | Cambio realizado y motivo | Apartado o registro | Estado |
| --- | --- | --- | --- | --- |
| 04-11-2026 | Condición 1 del docente: «Añade al menos una fuente primaria de Air Europa (comunicado o correo a clientes reproducido en una fuente verificable) para no depender solo de INCIBE y de la prensa». | Se han incorporado `F-04` (comunicación de Air Europa de octubre de 2023 recogida por OCU) y `F-05` (segundo comunicado de Air Europa de marzo de 2024 recogido por FACUA) tanto en el informe como en `fuentes.csv`. | Apartados 3, 5, 6 y 11 de `informe.md` y `registros/fuentes.csv` | Aplicado |
| 04-11-2026 | Condición 2 del docente: «Los riesgos de fraude secundario (PI-03) se describen como posibilidades justificadas por las fuentes, sin atribuir a esta brecha fraudes posteriores concretos». | Se ha ajustado la redacción de `PI-03`, la tabla de alcance y el hallazgo `H-04` para dejar explícito que los riesgos secundarios se tratan únicamente como escenarios posibles justificados documentalmente. | Apartados 2, 3 y 6 de `informe.md` | Aplicado |
| 04-11-2026 | Condición 3 del docente: «El análisis técnico del Tema 4 se limita a la información que se conoce sobre el incidente: no se consulta la infraestructura actual de Air Europa si no es estrictamente necesario». | Se ha incluido expresamente fuera del alcance cualquier consulta a la infraestructura actual de Air Europa (DNS, CT logs, Shodan), limitando el Tema 4 a los datos publicados del incidente. | Apartado 3 de `informe.md` y tabla de temas de `seguimiento.md` | Aplicado |

## Cambios de alcance

| Fecha | Cambio propuesto | Por qué hace falta | Aprobación y condiciones | Versión a la que se aplica |
| --- | --- | --- | --- | --- |
| 04-11-2026 | Ajuste del alcance inicial para incorporar las 3 condiciones de la resolución de `PF-TEMA` (inclusión de comunicados primarios reproducidos de Air Europa, acotación preventiva de `PI-03` y exclusión de consultas a la infraestructura actual en el Tema 4). | Requerido por el docente en la resolución de aprobación de la propuesta para garantizar independencia de fuentes y rigor metodológico. | Aprobado con condiciones el 04-11-2026 sobre el alcance del 27-10-2026. | v0.2 (`PF-P1`) y siguientes |

Un cambio pendiente de aprobación no se ejecuta.

## Trabajo realizado en clase y entre sesiones

| Fecha | Trabajo realizado | Resultado propio que se puede revisar | Archivo o referencia |
| --- | --- | --- | --- |
| 04-11-2026 | Revisión de la resolución de `PF-TEMA` y análisis de las tres condiciones de aprobación. | Actualización de condiciones en el plan de trabajo y definición de criterios de búsqueda para `F-04` y `F-05`. | `seguimiento.md`, `registros/bitacora.csv` (`B-02`) |
| 06-11-2026 | Búsqueda y verificación de fuentes verificables que reproducen los correos de Air Europa de octubre de 2023 y marzo de 2024. | Incorporación de `F-04` (OCU) y `F-05` (FACUA) al catálogo de fuentes. | `registros/fuentes.csv`, `registros/bitacora.csv` (`B-03`, `B-04`) |
| 08-11-2026 | Redacción de los apartados de requerimiento, alcance, contexto, evaluación OPSEC y primeras observaciones (`H-01` a `H-05`). | Versión v0.2 de `informe.md` y registro inicial en `hallazgos.csv`. | `informe.md`, `registros/hallazgos.csv` |

## Aplicación de los temas

| Tema | Aplicación concreta en este caso o limitación justificada | Apartado y evidencia |
| --- | --- | --- |
| 1. Fundamentos y ciclo | Definición del destinatario, la decisión de comunicación escalonada y las preguntas `PI-01` a `PI-03`, incorporando las condiciones del encargo aprobado. | Apartado 2 de `informe.md` |
| 2. Marco legal, ética y OPSEC | Delimitación estricta de fuentes abiertas, exclusión de datos personales (RGPD) y de tarjetas (PCI-DSS), exclusión de infraestructura actual y fijación de condición de parada. | Apartado 3 de `informe.md` |
| 3. Personas, organizaciones y SOCMINT | Identificación y contraste preliminar entre comunicados de la entidad afectada (`F-04`, `F-05`), avisos de organismos públicos (`F-01`, `F-02`) y verificadores (`F-03`). | Apartados 4, 5 y 6 de `informe.md` y `registros/fuentes.csv` |
| 4. Infraestructura y exposición | Limitado por la Condición 3 del alcance aprobado: no se consulta la infraestructura actual de Air Europa; se documenta únicamente la referencia pública al entorno de pagos web afectado en 2023 (`H-05`). | Apartados 3 y 6 de `informe.md` |
| 5. Fuentes cerradas y dark web | No se accede a foros ilícitos ni filtraciones; se evalúa únicamente lo que las fuentes oficiales (`F-01`, `F-02`) y la empresa (`F-04`, `F-05`) declaran sobre la ausencia de uso fraudulento confirmado. | Apartados 3 y 4 de `informe.md` |
| 6. Threat Intelligence y ATT&CK | Pendiente para `PF-P2` y `PF-P3`: ante la falta de CVE pública (`H-05`), se enfocará en escenarios preventivos derivados de los datos expuestos (p. ej., `T1566` Phishing) sin atribuir ataques posteriores reales (Condición 2). | Apartado 8 de `informe.md` (previsto en `PF-P2`) |
| 7. Análisis e informe | Separación inicial entre hechos comprobados y cuestiones pendientes; formulación de las cinco primeras observaciones verificables (`H-01` a `H-05`). | Apartados 4 y 6 de `informe.md` y `registros/hallazgos.csv` |
| 8. Herramientas y automatización | Estructuración de registros locales en CSV (`fuentes.csv`, `hallazgos.csv`, `bitacora.csv`) para asegurar la trazabilidad documental. | Carpeta `registros/` |

## Revisión de esta entrega

- **Qué ha cambiado desde la anterior:** Se ha pasado de la propuesta inicial (`propuesta.md`) a la estructura completa de `informe.md` (v0.2), incorporando las 3 condiciones de aprobación del 4 de noviembre, ampliando las fuentes de 3 a 5 (añadiendo los dos comunicados de Air Europa reproducidos en `F-04` y `F-05`) y registrando los primeros 5 hallazgos verificables (`H-01` a `H-05`).
- **Limitación más importante:** La ausencia de un informe técnico forense público impide conocer el vector de entrada exacto en la pasarela de pago o el número total oficial de afectados, por lo que ese aspecto se mantiene documentado como no acreditado públicamente (`H-05`).
- **Decisión que necesitas consultar:** Confirmar si el enfoque documental adoptado para cubrir el límite del Tema 4 (conforme a la Condición 3 de aprobación) requiere alguna aclaración adicional en el apartado de análisis de `PF-P2`.
- **Trabajo previsto hasta el siguiente hito:** Elaborar la cronología detallada distinguiendo fechas de hecho, publicación y actualización; completar el contraste de dependencias entre fuentes; formular al menos dos explicaciones plausibles en el apartado 7; y redactar la primera lectura de amenazas (Tema 6) para `PF-P2` (25 de noviembre).

[Volver a proceso y entregas](../../../../proyecto-final/02-proceso-y-entregas.md)
