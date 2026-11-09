# PF · Seguimiento del proyecto

**Estudiante:** Cayetano Castillo Ruiz  
**Caso y título:** Análisis de las vulnerabilidades PHP2Shell: ciclo de vida, evasión de parches y revisión de las evidencias sobre la implicación de la IA.  
**Hito:** P1  
**Fecha y versión del informe:** 9 de noviembre de 2026, v0.1  
**Alcance aprobado:** 09/11/2026, condicionado a centrar el objeto en los informes sobre vulnerabilidades y verificar las afirmaciones de las fuentes sobre la IA (sin darlas por hecho).

**Canal autorizado:** Pull request público.  
**Número de palabras del cuerpo y método de recuento:** 940 palabras (Procesador de texto, excluyendo portadas, índices y referencias. Límite: 2.500 palabras).  
**Referencia de la entrega y versión:** *[Añadir link del PR/Commit tras subirlo]*

## Estado de las preguntas

| Pregunta | Qué puede responderse ya | Evidencias | Información pendiente | Próximo paso permitido |
|---|---|---|---|---|
| PI-01 | Aún no se puede responder. | | Identificar y evaluar qué evidencias documentales aportan los reportes técnicos sobre el uso real de la IA. | Analizar los reportes de Snyk/Sygnia (F-04). |
| PI-02 | Sí hay explotación activa de las vulnerabilidades originales. | Inclusión en CISA KEV (F-02, H-02). | Determinar los TTPs específicos (ATT&CK) que están utilizando los actores de amenazas. | Mapeo de IoCs y comportamientos en fuentes OSINT (P2). |
| PI-03 | Las actualizaciones oficiales son la medida principal. | Avisos de PHP (F-01, H-01). | Qué configuraciones específicas de mitigación recomienda la comunidad para el CVE-2026-115560. | Revisión de mitigaciones alternativas en foros técnicos. |

## Correcciones y decisiones

| Hito o fecha | Observación recibida o problema detectado | Cambio realizado y motivo | Apartado o registro | Estado |
|---|---|---|---|---|
| 09/11/2026 | El profesor observó que el objeto no estaba delimitado, había sesgos en las preguntas (se daba por hecho que la IA actuó) y el corte temporal era previo al trabajo. | Se ajustó el objeto a las vulnerabilidades públicas, se reformularon PI-01 y PI-02 para buscar evidencias en las fuentes sin sesgos previos, y se cambió la fecha de corte al 30 de noviembre. | Propuesta y apartado 2, 3 y 4 del Informe. | Aplicado |

## Cambios de alcance

| Fecha | Cambio propuesto | Por qué hace falta | Aprobación y condiciones | Versión a la que se aplica |
|---|---|---|---|---|
| 09/11/2026 | Modalidad ajustada a "Caso de vulnerabilidades públicas". | Corrección del profesor para adecuar la nomenclatura a la realidad del objeto de estudio (no es un incidente corporativo aislado). | Aprobado el 09/11/2026. | v0.1 (P1) |

Un cambio pendiente de aprobación no se ejecuta.

## Trabajo realizado en clase y entre sesiones

| Fecha | Trabajo realizado | Resultado propio que se puede revisar | Archivo o referencia |
|---|---|---|---|
| 09/11/2026 | Recepción de correcciones, actualización de la propuesta y volcado de las condiciones aprobadas al informe. Definición del plan OSINT y OPSEC. | `informe.md` inicializado (puntos 1 a 6) y `seguimiento.md` creado. | Commit actual (Avance P1) |

## Aplicación de los temas

| Tema | Aplicación concreta en este caso o limitación justificada | Apartado y evidencia |
|---|---|---|
| 1. Fundamentos y ciclo | Se ha formulado un requerimiento claro y preguntas de inteligencia sin sesgo de confirmación. | `informe.md`, apartado 2. |
| 2. Marco legal, ética y OPSEC | Se ha definido un entorno de recolección OSINT pasivo utilizando VPN/DoH para evitar exposición técnica. | `informe.md`, apartado 3 (Condiciones de parada). |
| 3. Personas, organizaciones y SOCMINT | *(Limitación justificada)*: No aplica, el análisis se centra en infraestructura técnica y vulnerabilidades, no en redes sociales o identidades. | |
| 4. Infraestructura y exposición | *(Pendiente para P2)*: Identificación de la superficie web expuesta vulnerable a PHP2Shell. | |
| 5. Fuentes cerradas y dark web | *(Limitación justificada)*: Fuera del alcance aprobado; solo se usa OSINT público. | `informe.md`, apartado 3. |
| 6. Threat Intelligence y ATT&CK | *(Pendiente para P2)*: Mapeo de tácticas y técnicas empleadas en la explotación de la vulnerabilidad. | |
| 7. Análisis e informe | Volcado estructurado de la plantilla con separación de hechos e interpretaciones. | `informe.md`, apartados 4 y 6. |
| 8. Herramientas y automatización | Uso de catálogos automatizados y bases CVE (KEV, NVD) para extracción de datos en bruto. | `informe.md`, apartado 5 (F-02, F-03). |

## Revisión de esta entrega

- **Qué ha cambiado desde la anterior:** Se ha pasado de la propuesta inicial al comienzo formal del informe, aplicando los ajustes metodológicos requeridos para eliminar el sesgo de confirmación.
- **Limitación más importante:** La alta velocidad a la que se publican análisis (ruido mediático) obligará a ser muy estrictos discriminando entre las fuentes que aportan evidencias técnicas de IA y las que solo usan *buzzwords*.
- **Decisión que necesitas consultar:** Ninguna por el momento; el plan y el alcance están estabilizados.
- **Trabajo previsto hasta el siguiente hito:** Ejecución completa del plan de recolección de fuentes (F-01 a F-05), redacción del análisis (apartado 7) y mapeo de las amenazas identificadas (apartado 8) para el avance P2.