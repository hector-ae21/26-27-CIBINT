# Entrega P2 · Avance 2 del Proyecto Final

- **Estudiante:** Cayetano Castillo Ruiz
- **Caso:** Vulnerabilidades públicas PHP2Shell (`CVE-2026-109618`, `CVE-2026-109619`, `CVE-2026-115560`)
- **Versión del informe:** `v0.3` (27 de noviembre de 2026)
- **Recuento oficial (`informe.md`):** 3923 palabras en el cuerpo (apartados 1 a 10; resumen ejecutivo incluido: 39 palabras), obtenido con `node proyecto-final/contar-palabras.mjs entregas/castilloCayetano/PF/P2/informe.md`

## Contenido de esta entrega

- [`informe.md`](./informe.md): Informe de inteligencia en versión `v0.3` con cronología ampliada, contraste de dependencias (`F-01` a `F-06`), hallazgos `H-01` a `H-06`, análisis provisional con explicaciones alternativas (`PI-01`) y primera lectura provisional de amenazas.
- [`seguimiento.md`](./seguimiento.md): Seguimiento acumulativo, estado de las preguntas de inteligencia y lista de verificación de P2.
- [`registro-ia.md`](./registro-ia.md) y carpeta [`ia/`](./ia/): Declaración y exportaciones locales del uso de IA en P2.
- Carpeta [`registros/`](./registros/):
  - [`fuentes.csv`](./registros/fuentes.csv): Registro actualizado de las seis fuentes (`F-01` a `F-06`), sus dependencias y valoración separada de fiabilidad y credibilidad.
  - [`bitacora.csv`](./registros/bitacora.csv): Histórico continuo de consultas de P1 y P2 con configuración OPSEC e incidencias.
  - [`hallazgos.csv`](./registros/hallazgos.csv): Matriz trazable de hallazgos `H-01` a `H-06`.
  - [`integridad.csv`](./registros/integridad.csv): Huellas SHA-256 y MD5 de las siete evidencias locales (`EV-01` a `EV-07`).
- Carpeta [`recursos/`](./recursos/): Copias estáticas en PDF de las fuentes consultadas (`F-01_php_announcement.pdf`, `F-02_cisa_alert.pdf`, `F-02_cisa_kev.pdf`, `F-03_nvd_cves.pdf`, `F-04_snyk_php2shell.pdf`, `F-05_sygnia_php2shell.pdf` y `F-06_wiz_reasearch.pdf`).