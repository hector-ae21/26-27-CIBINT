# PF-P1 · Primer avance

- **Estudiante:** Cayetano Castillo Ruiz
- **Caso estudiado:** Vulnerabilidades públicas PHP2Shell (`CVE-2026-109618`, `CVE-2026-109619` y `CVE-2026-115560`) y revisión de evidencias sobre el papel de la IA
- **Hito:** P1 (Primer avance — corrección tras resolución del 23/11/2026)
- **Versión del informe:** `v0.2` (27 de noviembre de 2026)
- **Número de palabras del cuerpo (`informe.md`):** [PEGA_CIFRA] palabras (calculado con `node proyecto-final/contar-palabras.mjs`; máximo permitido en P1: 2.500 palabras)
- **Corte de información previsto:** 30 de noviembre de 2026 a las 23:59, Europe/Madrid

## Archivos incluidos en esta entrega

- [`informe.md`](./informe.md): Versión `v0.2` con encargo y alcance aprobados, evaluación legal/OPSEC corregida, contexto, plan de fuentes y consultas, primeros hallazgos y referencias verificadas.
- [`seguimiento.md`](./seguimiento.md): Hoja de seguimiento actualizada con la resolución del 23/11/2026 y los 7 ajustes aplicados.
- [`registro-ia.md`](./registro-ia.md): Declaración de uso de IA vinculada a las exportaciones locales.
- [`registros/fuentes.csv`](./registros/fuentes.csv): Registro de las 5 fuentes iniciales (`F-01` a `F-05`) con URLs reales, fechas verificadas y valoración.
- [`registros/bitacora.csv`](./registros/bitacora.csv): Registro cronológico de consultas con fecha, hora, zona horaria (`Europe/Madrid`) y búsqueda exacta.
- [`ia/`](./ia/): Exportaciones locales completas de las conversaciones con IA numeradas conforme a `registro-ia.md`.

## Resumen de correcciones aplicadas en `v0.2`

1. Sustituidos todos los enlaces simulados/pendientes por URLs reales verificadas con fecha de publicación y consulta en `propuesta.md` y `P1/informe.md`.
2. Añadidos los registros obligatorios (`fuentes.csv`, `bitacora.csv`, `P1/README.md`) y actualizado el índice en `PF/README.md`.
3. Guardadas las exportaciones completas de las conversaciones de IA en `P1/ia/`.
4. Corregida la condición de parada: ante un hallazgo fuera de alcance no se captura ni descarga contenido; solo se registra la categoría en la bitácora y se consulta.
5. Eliminada la descarga/apertura de repositorios de PoC en GitHub y ajustadas las medidas de OPSEC a recolección estrictamente pasiva.
6. Separadas Snyk (`F-04`) y Sygnia (`F-05`) como fuentes independientes y añadido el plan de consultas concretas por fuente y pregunta.
7. Actualizado el recuento de palabras mediante `node proyecto-final/contar-palabras.mjs` y documentadas todas las correcciones en `seguimiento.md`.