# Seguimiento del proyecto · Avance 2 (P2)

- **Estudiante:** Cayetano Castillo Ruiz
- **Hito:** P2 (Avance 2 · Análisis provisional, evidencias con integridad y primera lectura de amenazas)
- **Fecha y versión del informe:** 27 de noviembre de 2026, `v0.3`
- **Número de palabras del cuerpo y método de recuento:** 3923 palabras en el cuerpo (apartados 1 a 10; resumen ejecutivo incluido: 39 palabras), medido con `node proyecto-final/contar-palabras.mjs entregas/castilloCayetano/PF/P2/informe.md`
- **Corte de información previsto:** 30 de noviembre de 2026 a las 23:59, `Europe/Madrid`

## Estado de las preguntas de inteligencia

| ID | Pregunta | Estado en P2 | Evidencias y hallazgos clave | Qué falta para P3 |
|---|---|---|---|---|
| PI-01 | Papel de la IA en el descubrimiento de PHP2Shell y en `CVE-2026-115560` | **Avanzada (contraste principal resuelto)** | `H-03`, `H-04` (`F-01`, `F-04`, `F-05`, `F-06`; `EV-01`, `EV-05`, `EV-06`, `EV-07`). Trazada la dependencia `F-05 → F-06` y refutada la atribución de IA a `CVE-2026-115560`. | Verificar antes del 30/11/2026 si aparecen trazas reproducibles de Wiz o comunicados de los reportadores de `115560` y cerrar valoración definitiva de confianza. |
| PI-02 | Evidencias verificables de explotación activa | **Avanzada** | `H-02`, `H-05` (`F-01`, `F-02`, `F-05`, `F-06`; `EV-02`, `EV-03`, `EV-06`, `EV-07`). Confirmada explotación activa en CISA KEV y tráfico de ataque observado sin atribución ni IoCs de red. | Contrastar la referencia de Cloudflare citada por `F-05`, depurar la tabla del Apartado 8 tras el Tema 6 y afinar el mapeo MITRE ATT&CK. |
| PI-03 | Mitigaciones oficiales y limitaciones documentadas | **Avanzada** | `H-01`, `H-06` (`F-01`, `F-02`, `F-04`, `F-05`; `EV-01`, `EV-05`, `EV-06`). Documentadas directivas `php.ini`, advertencia de que solo actualizar resuelve el fallo y límites WAF. | Resolver la discrepancia secundaria sobre `PHP_SESSION_UPLOAD_PROGRESS` en los textos íntegros de los `GHSA` y redactar recomendaciones accionables por horizonte en el Apartado 10. |

## Registro de sesiones de trabajo (acumulativo)

| Fecha | Hito | Actividad realizada | Resultado o artefacto generado |
|---|---|---|---|
| 09/11/2026 | TEMA / P1 | Definición de propuesta, encargo, OPSEC inicial y primer borrador `v0.1` de `informe.md`. | `TEMA/propuesta.md`, `P1/informe.md` (`v0.1`). |
| 27/11/2026 | P1 | Aplicación de las 7 correcciones del 23/11/2026: URLs reales verificadas, creación de `fuentes.csv`, `bitacora.csv`, `P1/README.md`, `PF/README.md`, exportaciones en `P1/ia/`, corrección de condición de parada, exclusión de PoCs, separación de Snyk/Sygnia y recuento con `contar-palabras.mjs`. | `P1/informe.md` (`v0.2`), registros de P1 y actualización del PR de P1. |
| 27/11/2026 | P2 | Recolección pasiva en Opera GX (ventana privada, VPN con bypass de buscadores desactivado, DoH) de `F-01` a `F-05`; detección de dependencia en `F-05` e incorporación de la fuente origen Wiz Research (`F-06`). Preservación de 7 PDFs locales en `P2/recursos/` y cálculo de huellas SHA-256 y MD5. | `P2/recursos/` (`EV-01` a `EV-07`), `P2/registros/integridad.csv`, `fuentes.csv`, `bitacora.csv`, `hallazgos.csv`. |
| 27/11/2026 | P2 | Ampliación de `P2/informe.md` a `v0.3` (cronología de 4 fechas, contraste de dependencias, `H-01` a `H-06`, análisis provisional con explicaciones alternativas `E-01`/`E-02` y primera lectura provisional del Apartado 8), ajuste de extensión por debajo de 4.500 palabras y verificación con `contar-palabras.mjs`. | `P2/informe.md` (`v0.3`, 3923 palabras), `P2/seguimiento.md`, `P2/README.md`, `P2/registro-ia.md`. |

## Revisión de esta entrega (P2)

- [x] `P2/informe.md` en versión `v0.3`, respetando la plantilla oficial y dentro del límite de 4.500 palabras (3923 palabras medidas con `contar-palabras.mjs`, sin avisos de apartados faltantes).
- [x] Cronología ampliada distinguiendo fecha del hecho, publicación, observación técnica y consulta, separando hechos verificados de afirmaciones atribuidas.
- [x] Contraste de dependencias entre fuentes documentado (`F-05 → F-06`, `F-03 → F-01/F-02`, `F-04 → F-01` sin mención a IA) y valoración separada de fiabilidad y credibilidad en `P2/registros/fuentes.csv`.
- [x] Hallazgos `H-01` a `H-06` registrados en `P2/registros/hallazgos.csv` y vinculados a evidencias locales preservadas en `P2/recursos/` con huellas SHA-256 y MD5 reales en `P2/registros/integridad.csv`.
- [x] Explicaciones alternativas (`E-01` y `E-02`) sobre `PI-01`, revisión de sesgos/contradicciones y justificación explícita de apartados sin datos (organizaciones víctimas, fuentes cerradas/PoC e infraestructura propia).
- [x] Primera lectura provisional del Apartado 8 (*Amenazas, indicadores y comportamientos*) con sus límites declarados y sin IoCs no verificados ni enlaces activos.
- [x] Uso de IA documentado en `P2/registro-ia.md` con exportaciones locales en `P2/ia/` y `PF/README.md` actualizado con enlace a `P2`.