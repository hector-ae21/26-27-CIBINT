# PF · Seguimiento del proyecto

Estudiante: Eirik Alberto Rosete León  
Caso y título: HSE de Irlanda: ¿qué prioridades de continuidad y controles defensivos se justifican en una red sanitaria interconectada?  
Hito: P1  
Fecha y versión del informe: 11 de noviembre de 2026, v0.1  
Alcance aprobado: 4 de noviembre de 2026, aprobado con condiciones: sustituir F-03; mantener las cifras de cancelaciones y del volumen exfiltrado como afirmaciones atribuidas; concretar en P1 la fecha y las fuentes de revisión de cada pregunta.

Canal autorizado: pull request público  
Número de palabras del cuerpo y método de recuento: 2113 palabras; `node proyecto-final/contar-palabras.mjs entregas/roseteEirik/PF/P1/informe.md`  
Referencia de la entrega y versión: [pull request y commit]

## Estado de las preguntas

| Pregunta | Qué puede responderse ya | Evidencias | Información pendiente | Próximo paso permitido |
|---|---|---|---|---|
| PI-01 | Pendiente | — | Revisión de la cronología de F-01, la alerta del NCSC (F-02) y las informaciones sobre cancelaciones (F-03 y F-04) | Revisión el 13/11/2026 |
| PI-02 | Pendiente | — | Revisión de la parte de respuesta y recuperación de F-01 y los servicios afectados que comunicó el HSE (F-04) | Revisión el 17/11/2026 |
| PI-03 | Pendiente | — | Revisión de la evaluación de controles y las alertas previas descritas en F-01 y de las técnicas que señala el NCSC (F-02) | Revisión el 20/11/2026 |
| PI-04 | Pendiente | — | Revisión de los datos redactados y la pérdida de registros del antivirus que documenta F-01 | Revisión el 23/11/2026 |

## Correcciones y decisiones

| Hito o fecha | Observación recibida o problema detectado | Cambio realizado y motivo | Apartado o registro | Estado |
|---|---|---|---|---|
| TEMA · 04/11/2026 | 1. Sustituye F-03: el enlace pasa por removepaywall.com, un servicio para eludir el muro de pago del medio. | F-03 sustituida por un artículo de The Journal; se añade F-04 (HSE) | Propuesta, apartado 5; informe, apartado 11; `registros/fuentes.csv` | Aplicado |
| TEMA · 04/11/2026 | 2. Mantén las cifras de cancelaciones y del volumen exfiltrado como afirmaciones atribuidas a quien las hace, no como hechos, hasta contrastarlas. | Las cifras se presentan atribuidas a quien las hace | Propuesta, apartado 1; informe, apartado 4 | Aplicado |
| TEMA · 04/11/2026 | 3. En P1, concreta en qué fecha y con qué fuentes revisarás cada pregunta. | Fecha y fuentes de revisión de cada pregunta | Propuesta, apartado 6; informe, apartado 5 | Aplicado |

## Cambios de alcance

| Fecha | Cambio propuesto | Por qué hace falta | Aprobación y condiciones | Versión a la que se aplica |
|---|---|---|---|---|
| | | | | |

Un cambio pendiente de aprobación no se ejecuta.

## Trabajo realizado en clase y entre sesiones

| Fecha | Trabajo realizado | Resultado propio que se puede revisar | Archivo o referencia |
|---|---|---|---|
| | | | |

## Aplicación de los temas

| Tema | Aplicación concreta en este caso o limitación justificada | Apartado y evidencia |
|---|---|---|
| 1. Fundamentos y ciclo | Destinatario, decisión y cuatro preguntas de inteligencia | Informe, apartado 2 |
| 2. Marco legal, ética y OPSEC | Alcance, exclusiones, minimización (art. 5.1.c RGPD) y condición de parada | Informe, apartado 3 |
| 3. Personas, organizaciones y SOCMINT | Pendiente | |
| 4. Infraestructura y exposición | Pendiente. Consultas DNS al HSE excluidas del alcance | Informe, apartado 3 |
| 5. Fuentes cerradas y dark web | Pendiente. Dark web excluida del alcance | Informe, apartado 3 |
| 6. Threat Intelligence y ATT&CK | Pendiente. Primera revisión provisional de MITRE ATT&CK prevista en P2 | Propuesta, apartado 6 |
| 7. Análisis e informe | Pendiente | |
| 8. Herramientas y automatización | Pendiente | |

## Revisión de esta entrega

- Qué ha cambiado desde la anterior: se incorporan las tres condiciones de la resolución del 4 de noviembre de 2026 y se añade F-05.
- Limitación más importante: el informe forense original no es público y en F-01 se han redactado ciertos datos por motivos de seguridad, como el CVE específico explotado en un hospital o los nombres de dominios internos.
- Decisión que necesitas consultar: se consultará al profesorado si el nivel de detalle técnico de F-01 es suficiente para extraer comportamientos y realizar el mapeo necesario para P3.
- Trabajo previsto hasta el siguiente hito: revisión de PI-01 (13/11/2026), PI-02 (17/11/2026), PI-03 (20/11/2026) y PI-04 (23/11/2026); obtención de evidencias, elaboración de una cronología estructurada, contraste de cifras con la prensa y formulación de hipótesis con evidencias a favor, en contra y pendientes.
