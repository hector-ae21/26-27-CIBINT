# PF · Seguimiento del proyecto

**Estudiante:** Cayetano Castillo Ruiz  
**Caso y título:** Análisis de las vulnerabilidades PHP2Shell: ciclo de vida, evasión de parches y revisión de las evidencias sobre la implicación de la IA.  
**Hito:** P1  
**Fecha y versión del informe:** 27 de noviembre de 2026, v0.2  
**Alcance aprobado:** Propuesta `v0.2` aprobada condicionalmente el 23/11/2026, sujeta a incorporar las URLs reales de todas las referencias y completar los registros obligatorios de P1.

**Canal autorizado:** Pull request público.  
**Número de palabras del cuerpo y método de recuento:** [PEGA_CIFRA] palabras (`node proyecto-final/contar-palabras.mjs`).  
**Referencia de la entrega y versión:** *[Añadir enlace al PR y último commit tras subir los cambios]*

## Estado de las preguntas

| Pregunta | Qué puede responderse ya | Evidencias | Información pendiente | Próximo paso permitido |
|---|---|---|---|---|
| PI-01 | Se han identificado fuentes primarias y secundarias que abordan el ciclo de los fallos; aún no se ha verificado qué pruebas sustentan el papel de la IA. | Avisos de PHP (`F-01`), fichas NVD (`F-03`) y reportes de Snyk (`F-04`) y Sygnia (`F-05`). | Determinar exactamente qué fuente afirma que se usó IA, qué evidencia documental aporta y si es propia o depende de otra fuente. | Contraste sistemático de `F-04` y `F-05` frente a `F-01` y trazado de dependencias en P2. |
| PI-02 | Confirmada la explotación activa de las dos vulnerabilidades iniciales (`CVE-2026-109618` y `CVE-2026-109619`). | Alerta e inclusión en el catálogo CISA KEV del 26/10/2026 (`F-02`, `H-02`). | Comportamientos documentados, posibles indicadores publicados y estado de explotación de `CVE-2026-115560`. | Lectura provisional de amenazas y revisión de indicadores neutralizados en P2. |
| PI-03 | Las actualizaciones oficiales de PHP son la remediación principal y existen mitigaciones documentadas en avisos oficiales y secundarios. | Aviso de PHP Group (`F-01`, `H-01`) y alerta CISA (`F-02`). | Detalle completo de mitigaciones provisionales recomendadas y sus limitaciones técnicas, incluyendo el matiz de `CVE-2026-115560`. | Consolidación comparativa de mitigaciones oficiales y sus límites en P2. |

## Correcciones y decisiones

| Hito o fecha | Observación recibida o problema detectado | Cambio realizado y motivo | Apartado o registro | Estado |
|---|---|---|---|---|
| 09/11/2026 (TEMA) | Objeto no delimitado, sesgo en PI-01/PI-02, corte anterior al trabajo, falta de fechas/aviso oficial de PHP y modalidad imprecisa. | Se delimitó el objeto a las vulnerabilidades PHP2Shell y su ciclo, se reformularon PI-01 a PI-03 sin presuponer el papel de la IA, se fijó corte al 30/11/2026 23:59 Europe/Madrid y se ajustó la modalidad a *Caso de vulnerabilidades públicas*. | `TEMA/propuesta.md` (`v0.2`) y `P1/informe.md` (`v0.1`) | Aplicado |
| 23/11/2026 (P1 · Corr. 1) | Referencias con textos genéricos («Enlace simulado» / «URL pendiente de registro local») no comprobables. | Sustituidos todos los textos genéricos por URLs reales verificadas de PHP Group, CISA, NVD, Snyk y Sygnia con fechas reales de publicación y consulta (`27/11/2026`). | `TEMA/propuesta.md`, `P1/informe.md` (Ap. 11) y `P1/registros/fuentes.csv` | Aplicado |
| 23/11/2026 (P1 · Corr. 2) | Faltaban los registros obligatorios (`fuentes.csv`, `bitacora.csv`), `P1/README.md` y la entrada de P1 en `PF/README.md`. | Creados `P1/registros/fuentes.csv`, `P1/registros/bitacora.csv` y `P1/README.md`, y actualizado el índice general en `PF/README.md`. | `P1/registros/`, `P1/README.md`, `PF/README.md` | Aplicado |
| 23/11/2026 (P1 · Corr. 3) | Los enlaces a Gemini no bastan como evidencia de uso de IA. | Exportadas las conversaciones completas en local dentro de `P1/ia/` (`01-contexto-cronologia.md`, `02-opsec-condiciones-parada.md`) con la misma numeración que `P1/registro-ia.md`. | `P1/ia/` y `P1/registro-ia.md` | Aplicado |
| 23/11/2026 (P1 · Corr. 4) | La condición de parada indicaba «capturar el hallazgo» al encontrar un *Zero-Day* o C2 activo. | Corregido el procedimiento: al activarse una parada no se captura ni descarga nada; se cierra la consulta, se anota únicamente la categoría en `bitacora.csv` y se consulta al profesorado. | `TEMA/propuesta.md` (Ap. 4) y `P1/informe.md` (Ap. 3) | Aplicado |
| 23/11/2026 (P1 · Corr. 5) | Se incluía consulta/descarga de PoC en GitHub (`F-05`) y OPSEC basada en descargar código en VM. | Eliminada la descarga y apertura de repositorios de código PoC; cualquier referencia a PoC públicas se limita a lo documentado por fuentes secundarias y las medidas de OPSEC se ajustaron a OSINT pasivo. | `P1/informe.md` (Ap. 3 y Ap. 5) y `P1/registros/fuentes.csv` | Aplicado |
| 23/11/2026 (P1 · Corr. 6) | Snyk y Sygnia estaban agrupadas en una sola fuente y faltaba la consulta concreta prevista por fuente. | Separadas Snyk (`F-04`) y Sygnia (`F-05`) en dos fuentes independientes y añadido el subapartado *Plan de consultas* especificando consulta exacta, qué se busca y qué pregunta cubre. | `P1/informe.md` (Ap. 5) y `P1/registros/fuentes.csv` | Aplicado |
| 23/11/2026 (P1 · Corr. 7) | El recuento de palabras se había realizado con procesador de texto en lugar del script oficial. | Recalculadas las palabras de `propuesta.md` e `informe.md` con `node proyecto-final/contar-palabras.mjs` y actualizados `propuesta.md`, `P1/README.md` y `P1/seguimiento.md`. | `TEMA/propuesta.md`, `P1/README.md`, `P1/seguimiento.md` | Aplicado |

## Cambios de alcance

| Fecha | Cambio propuesto | Por qué hace falta | Aprobación y condiciones | Versión a la que se aplica |
|---|---|---|---|---|
| 09/11/2026 | Modalidad ajustada a «Caso de vulnerabilidades públicas» y objeto centrado en las vulnerabilidades PHP2Shell, su ciclo y evidencias sobre IA. | Adecuar el alcance a las observaciones recibidas sobre la propuesta inicial. | Aprobado el 23/11/2026 condicionado a incorporar las URLs reales verificadas (cumplido en `v0.2`). | `v0.2` (P1) |

Un cambio pendiente de aprobación no se ejecuta.

## Trabajo realizado en clase y entre sesiones

| Fecha | Trabajo realizado | Resultado propio que se puede revisar | Archivo o referencia |
|---|---|---|---|
| 09/11/2026 | Actualización inicial de propuesta y primera versión del informe (`v0.1`) y hoja de seguimiento. | `TEMA/propuesta.md`, `P1/informe.md` (`v0.1`), `P1/seguimiento.md`. | PR de P1 (commits iniciales) |
| 27/11/2026 | Verificación de URLs reales y fechas de `F-01` a `F-05`, separación de Snyk y Sygnia, corrección de OPSEC y condición de parada, creación de `fuentes.csv`, `bitacora.csv`, `P1/README.md`, `PF/README.md`, exportaciones locales en `P1/ia/` y recuento oficial con `contar-palabras.mjs`. | Conjunto completo de archivos corregidos en la rama del PR de P1 (`v0.2`). | Commit de correcciones de P1 |

## Aplicación de los temas

| Tema | Aplicación concreta en este caso o limitación justificada | Apartado y evidencia |
|---|---|---|
| 1. Fundamentos y ciclo | Requerimiento de inteligencia definido con destinatario, decisión y preguntas sin sesgo (`PI-01` a `PI-03`). | `P1/informe.md`, Ap. 2 |
| 2. Marco legal, ética y OPSEC | Recolección estrictamente pasiva, exclusión de apertura/descarga de código PoC y condición de parada sin captura ni descarga. | `P1/informe.md`, Ap. 3 |
| 3. Personas, organizaciones y SOCMINT | Limitación justificada: no aplica al objeto aprobado (vulnerabilidades públicas y reportes técnicos, no perfiles personales ni SOCMINT). | `P1/informe.md`, Ap. 3 |
| 4. Infraestructura y exposición | Limitación justificada en P1: no se analizan activos concretos de organizaciones víctimas; en P2 se acotará a cifras agregadas citadas por fuentes si aportan contexto. | `P1/informe.md`, Ap. 3 |
| 5. Fuentes cerradas y dark web | Limitación justificada: excluido del alcance aprobado (solo OSINT público). | `P1/informe.md`, Ap. 3 |
| 6. Threat Intelligence y ATT&CK | Pendiente para P2/P3: primera lectura de indicadores neutralizados y comportamientos documentados en reportes técnicos. | `P1/informe.md`, Ap. 8 (pendiente) |
| 7. Análisis e informe | Separación de hechos y afirmaciones pendientes en cronología y columna «Qué no demuestra» en hallazgos iniciales. | `P1/informe.md`, Ap. 4 y Ap. 6 |
| 8. Herramientas y automatización | Uso del script oficial `contar-palabras.mjs` para el control de extensión y consulta estructurada de catálogos públicos (CISA KEV, NVD). | `P1/registros/bitacora.csv` (`B-02`, `B-03`) |

## Revisión de esta entrega

- **Qué ha cambiado desde la anterior:** Se han subsanado las 7 correcciones señaladas el 23/11/2026 sobre el mismo PR de P1: URLs reales y fechas verificadas, registros `fuentes.csv` y `bitacora.csv`, `README.md` de P1 y PF, exportaciones locales en `P1/ia/`, corrección de condición de parada y OPSEC (sin PoCs), plan de consultas con Snyk y Sygnia separados, y recuento con `contar-palabras.mjs`.
- **Limitación más importante:** Las fuentes secundarias (`F-04`, `F-05`) no siempre separan observaciones propias de afirmaciones heredadas de terceros, especialmente respecto al papel atribuido a la IA y la clasificación de `CVE-2026-115560`.
- **Decisión que necesitas consultar:** Confirmación de que las 7 correcciones dejan aprobado el alcance y P1 para abrir la entrega de P2 centrada en `PI-01`.
- **Trabajo previsto hasta el siguiente hito:** Para P2, auditar en detalle `PI-01` (qué fuente afirma el uso de IA, con qué evidencia concreta y sus dependencias), ampliar la cronología de cuatro fechas, redactar explicaciones alternativas y realizar la primera lectura provisional de amenazas.