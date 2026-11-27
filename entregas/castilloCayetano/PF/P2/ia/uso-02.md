# Exportación de uso de IA · Uso 02 (P2)

- **Fecha y hora:** 27/11/2026 21:10 (`Europe/Madrid`)
- **Herramienta y modelo:** Gemini Pro 3.1
- **Hito:** P2 (`v0.3`) · Estructuración de `P2/informe.md`, análisis provisional y control de extensión

## Prompt

Estoy ampliando mi informe de ciberinteligencia sobre PHP2Shell desde la versión de P1 (`v0.2`) al Avance 2 (`P2/informe.md`, `v0.3`). Debo mantener intactos los 11 apartados y tablas de mi plantilla original, no superar el límite de 4.500 palabras en el cuerpo (apartados 1 a 10) y dejar pendientes el Resumen ejecutivo (apartado 1) y los apartados 9 y 10 para P3.

Ya he recogido y verificado los datos reales de 6 fuentes (`F-01` a `F-06`) con 7 copias PDF locales (`EV-01` a `EV-07`):
- Wiz Research (`F-06`) es la fuente origen de la afirmación sobre IA (descubrimiento el 19/08/2026 usando Wiz Atlas, Gemini 4 Argon y GPT-5.6 Sol; RCE pre-auth en Drupal/WordPress el 20-21/08). PHP Group (`F-01`) acredita en los GHSA de CVE-2026-109618 y CVE-2026-109619 a `@sagitzadik-wiz`, `@amyb-oai`, `@lcfr-hax` y `@tomash-areion`, pero no audita el papel de la IA.
- Sygnia (`F-05`) cita a Wiz (`F-06`) sobre la IA, reporta tráfico de ataque observado (compromisos reales desconocidos) y advierte de no depender solo de reglas WAF sobre `PHP_SESSION_UPLOAD_PROGRESS`.
- Snyk (`F-04`) no menciona la IA, describe CVE-2026-115560 como evasión parcial de CVE-2026-109619 y recoge las mitigaciones temporales de PHP advirtiendo que solo actualizar es seguro.
- PHP Group (`F-01`, `GHSA-658j-r8rw-q6mx` del 19/11/2026, CVSS 4.0 9.2, CWE-20/CWE-502) aclara que CVE-2026-115560 exige cambiar `session.serialize_handler` en tiempo de ejecución con `ini_set()` antes de `session_start()` con upload progress activo, y acredita a 7 reportadores distintos de los de octubre.
- CISA (`F-02`) incluyó CVE-2026-109618 y CVE-2026-109619 en KEV el 26/10/2026 (plazo 29/10/2026), sin atribución ni IoCs de red.

¿Cómo me recomiendas estructurar la ampliación de los apartados 4 (cronología de 4 fechas), 5 (contraste de dependencias), 6 (hallazgos H-01 a H-06), 7 (análisis provisional, explicaciones alternativas E-01/E-02 sobre PI-01, apartados sin datos justificados y revisión de sesgos/contradicciones sobre `PHP_SESSION_UPLOAD_PROGRESS`) y 8 (primera lectura provisional de amenazas) manteniendo rigor analítico y sin pasarme de las 4.500 palabras?

## Respuesta completa

Para ampliar `P2/informe.md` (`v0.3`) respetando intactos los 11 apartados de tu plantilla y quedándote con margen por debajo de las **4.500 palabras** (objetivo seguro: **3.800–4.100 palabras**), conviene evitar repetir en el Apartado 7 lo ya tabulado en los Apartados 4 y 6, y recordar que `contar-palabras.mjs` suele dividir fechas e identificadores con guiones (`CVE-2026-109618`, `GHSA-...`) en varias palabras. Mantén los apartados 1, 9 y 10 con una nota breve de «Pendiente para P3» y concentra la ampliación en los cinco bloques siguientes:

---

### Apartado 4 · Contexto y cronología (4 fechas)
Mantén la separación estricta entre **Hecho** y **Afirmación atribuida**, pero amplía la tabla de P1 para distinguir las cuatro dimensiones temporales exigidas en P2 (*Fecha del hecho*, *Publicación*, *Observación técnica* y *Consulta*):

| Fecha del hecho | Publicación | Observación técnica | Fecha de consulta | Hecho o afirmación atribuida | Fuente | Limitación |
|---|---|---|---|---|---|---|
| 19–21/08/2026 (Global) | 21/10/2026 | 19–21/08/2026 *(autodeclarada)* | 27/11/2026 (`Europe/Madrid`) | **Afirmación atribuida:** Wiz Research declara haber descubierto el fallo inicial el 19/08 con Wiz Atlas, Gemini 4 Argon y GPT-5.6 Sol, logrando RCE pre-auth en Drupal/WordPress el 20–21/08. | F-06 | Fuente parte interesada; sin trazas reproducibles ni auditoría externa sobre el peso real de la IA. |
| 21/10/2026 (UTC) | 21/10/2026 | N/A | 27/11/2026 (`Europe/Madrid`) | **Hecho:** PHP Group publica los parches y avisos de CVE-2026-109618 y CVE-2026-109619, acreditando a `@sagitzadik-wiz`, `@amyb-oai`, `@lcfr-hax` y `@tomash-areion`. | F-01, F-03 | Confirma autoría humana/organizativa y parcheo, pero no audita el uso de IA ni documenta ataques. |
| 22/10/2026 (Global) | 22/10/2026 | 22/10/2026 *(secundaria)* | 27/11/2026 (`Europe/Madrid`) | **Afirmación atribuida:** Sygnia reporta tráfico de ataque observado y RCE en laboratorio, cita a Wiz respecto a la IA y alerta sobre los límites del WAF con `PHP_SESSION_UPLOAD_PROGRESS`. | F-05 | No aporta independencia sobre la IA (depende de F-06) y declara desconocido el alcance real de compromisos. |
| 23/10/2026 (UTC) | 23/10/2026 | N/A | 27/11/2026 (`Europe/Madrid`) | **Hecho:** PHP difunde aviso informativo previo para CVE-2026-115560 y CISA actualiza su alerta inicial. | F-01, F-02 | Aún no existía el parche definitivo ni el aviso completo `GHSA-658j-r8rw-q6mx`. |
| 26/10/2026 (UTC) | 26/10/2026 | ≤ 26/10/2026 *(telemetría CISA)* | 27/11/2026 (`Europe/Madrid`) | **Hecho:** CISA incluye CVE-2026-109618 y CVE-2026-109619 en el catálogo KEV (plazo límite: 29/10/2026). | F-02 | Confirma explotación activa, pero no aporta fecha exacta del primer ataque, atribución ni IoCs de red. |
| 26/10/2026 (Global) | 26/10/2026 | 26/10/2026 *(secundaria)* | 27/11/2026 (`Europe/Madrid`) | **Afirmación atribuida:** Snyk describe CVE-2026-115560 como evasión parcial de CVE-2026-109619 y recoge las mitigaciones temporales de PHP sin mencionar la IA. | F-04 | Diverge del encuadre final de F-01 (19/11) y no incluye telemetría propia de explotación. |
| 19/11/2026 (UTC) | 19/11/2026 | N/A | 27/11/2026 (`Europe/Madrid`) | **Hecho:** PHP Group publica `GHSA-658j-r8rw-q6mx` (CVE-2026-115560, CVSS 4.0 9.2, CWE-20/CWE-502), acotándolo a cambios de `session.serialize_handler` con `ini_set()` antes de `session_start()` y acreditando a 7 reportadores distintos de los de octubre. | F-01, F-03 | No consta inclusión en KEV ni evidencia pública de explotación masiva. |

---

### Apartado 5 · Fuentes y método (contraste de dependencias)
Conserva intacta la tabla de 4 columnas de tu plantilla (añadiendo la fila de F-06 Wiz Research y enlazando los registros `P2/registros/*.csv` y evidencias `EV-01` a `EV-07`) y añade un subapartado conciso de **Contraste de dependencias entre fuentes** (unas 100–130 palabras) que deje explícitas tres cadenas:
- **Metadatos primarios:** F-03 (NVD) agrega información de F-01 (PHP Group) y F-02 (CISA), por lo que no suma confirmación independiente sobre hechos de parcheo o explotación.
- **Base técnica secundaria:** Tanto F-04 (Snyk) como F-05 (Sygnia) parten de F-01 para versiones y mitigaciones.
- **Dependencia crítica en `PI-01`:** La afirmación sobre el papel de la IA tiene un **único origen trazable (`F-06`)**. F-05 se limita a citar a F-06, F-04 no menciona la IA y F-01 acredita a los investigadores sin auditar las herramientas usadas. Repetir el mismo origen en varias fuentes secundarias no aumenta la confianza.

---

### Apartado 6 · Resultados y evidencias (`H-01` a `H-06`)
Usa la tabla exacta de 5 columnas de la plantilla (`Hallazgo | Pregunta | Observación verificable | Fuente y fecha | Qué no demuestra`), dejando cada fila en 2–3 líneas sin mezclar interpretaciones:
- **H-01 (`PI-01`):** Wiz Research (F-06, 21/10/2026) declara el hallazgo inicial (19/08) con Wiz Atlas, Gemini 4 Argon y GPT-5.6 Sol y RCE en Drupal/WordPress (20–21/08); PHP (F-01, 21/10) acredita a `@sagitzadik-wiz`, `@amyb-oai`, `@lcfr-hax` y `@tomash-areion`. **Qué no demuestra:** el grado real de autonomía de la IA ni auditoría independiente de esas trazas.
- **H-02 (`PI-01`):** En fuentes secundarias, Sygnia (F-05, 22/10) solo cita a F-06 respecto a la IA, mientras Snyk (F-04, 26/10) no la menciona. **Qué no demuestra:** consenso independiente entre analistas externos sobre la autoría de la IA.
- **H-03 (`PI-02`):** CISA (F-02, 26/10) añade CVE-2026-109618 y CVE-2026-109619 al catálogo KEV (plazo 29/10) y Sygnia (F-05, 22/10) reporta tráfico de ataque observado y RCE en laboratorio. **Qué no demuestra:** atribución de actores, volumen real de compromisos ni IoCs de red verificables.
- **H-04 (`PI-01`, `PI-03`):** PHP Group (F-01, `GHSA-658j-r8rw-q6mx`, 19/11, CVSS 4.0 9.2, CWE-20/CWE-502) precisa que CVE-2026-115560 exige cambiar `session.serialize_handler` en ejecución con `ini_set()` antes de `session_start()` con *upload progress* activo, y acredita a 7 reportadores distintos de los de octubre. **Qué no demuestra:** uso de IA en este tercer fallo ni explotación activa (ausente en KEV).
- **H-05 (`PI-03`):** Snyk (F-04, 26/10) encuadra CVE-2026-115560 como evasión parcial de CVE-2026-109619 y recoge las mitigaciones temporales de PHP advirtiendo que solo actualizar es seguro. **Qué no demuestra:** que la condición de 115560 sea habitual en producción ni invalida el alcance acotado de F-01.
- **H-06 (`PI-03`):** Sygnia (F-05, 22/10) advierte que el WAF es un control adicional y que no debe dependerse solo de reglas sobre `PHP_SESSION_UPLOAD_PROGRESS`, porque CVE-2026-109618 no lo exige. **Qué no demuestra:** eficacia universal de una regla WAF concreta ni cobertura frente a acceso directo al origen.

---

### Apartado 7 · Análisis provisional
Divídelo en cuatro bloques breves y directos (unas 700–850 palabras en total para no disparar el recuento):
1. **Análisis provisional por pregunta (`PI-01` a `PI-03`):**
   - **`PI-01`:** Separa explícitamente los dos tramos del ciclo: en los CVEs de octubre (`109618`/`109619`) hay autoría confirmada de Wiz y OpenAI en F-01, pero el papel de la IA procede solo de una autodeclaración (F-06) sin trazas reproducibles; en CVE-2026-115560 ninguna fuente documenta IA y los 7 reportadores distintos apuntan a un hallazgo separado.
   - **`PI-02`:** Explotación activa confirmada para los dos CVEs iniciales (F-02, confianza alta), pero con alcance real de compromisos desconocido (F-05) y sin IoCs de red; evita equiparar la cuota global de PHP citada por F-06 con sistemas comprometidos.
   - **`PI-03`:** Actualizar PHP es la única remediación completa (H-05). Resume los tres límites operativos de las mitigaciones temporales: riesgo de agotamiento con `memory_limit=-1`, cobertura incompleta de reglas WAF basadas solo en `PHP_SESSION_UPLOAD_PROGRESS` (H-06), y bypass del WAF si existe acceso directo al origen.
2. **Organizaciones, publicaciones e infraestructura (apartados sin datos justificados):** Tres viñetas breves justificando que: (a) en *Organizaciones* no hay víctimas ni actores atribuidos por ausencia en F-02 y alcance; (b) en *Publicaciones* se excluyen foros cerrados, *dark web* y código PoC por OPSEC; y (c) en *Infraestructura* no hay datos propios por exclusión de escaneos activos.
3. **Explicaciones alternativas sobre `PI-01` (tabla de 5 columnas):**
   - **E-01 (Papel determinante de la IA en todo el ciclo):** *A favor:* fechas y modelos concretos en F-06, créditos de `@sagitzadik-wiz` y `@amyb-oai` en F-01, entrada rápida en KEV (F-02). *En contra:* ausencia de trazas reproducibles/auditoría externa, F-02 no vincula ataques con IA y F-01 acredita a 7 reportadores distintos en 115560 bajo configuración atípica. *Pendiente:* publicación de trazas o declaraciones de los 7 reportadores antes del 30/11. *Valoración:* plausible con reservas en el descubrimiento inicial; no sostenida para 115560 ni para la explotación.
   - **E-02 (Asistencia parcial de IA amplificada comercialmente + *patch diffing* humano):** *A favor:* interés comercial de F-06 (Wiz Atlas), silencio de F-04 sobre IA y perfil de los 7 reportadores de `GHSA-658j-r8rw-q6mx` compatible con revisión clásica de parches. *En contra:* la acreditación conjunta de `@amyb-oai` y Wiz en F-01 respalda colaboración técnica real en IA y no solo marketing. *Pendiente:* verificar comunicados de OpenAI/Google o de los 7 reportadores antes del 30/11. *Valoración:* plausible y prudente; explica mejor la separación de descubridores y CVE-2026-115560.
4. **Revisión de sesgos y contradicciones:**
   - **Corrección del sesgo inicial (`v0.1`):** Descartar la asunción previa de que la IA generó la evasión CVE-2026-115560, refutada al cruzar F-01 y F-04.
   - **Contradicción técnica sobre `PHP_SESSION_UPLOAD_PROGRESS`:** Documenta que F-04 vincula `session.upload_progress.enabled=0` a CVE-2026-109619, F-05 advierte que CVE-2026-109618 no requiere `PHP_SESSION_UPLOAD_PROGRESS`, y F-06 asocia *upload-progress* a 109618 y *fatal-error backtrace* / *OPcache* a 109619. Deja anotado que esta discrepancia entre fuentes secundarias se contrastará contra el texto técnico íntegro de los GHSA (F-01) en P3 y refuerza por qué el SOC no debe depender de un único filtro WAF.

---

### Apartado 8 · Amenazas, indicadores y comportamientos (primera lectura provisional)
Añade una nota inicial indicando que es una **lectura provisional para P2** (a revisar con el Tema 6 y cerrar en P3) y rellena la tabla exacta de 5 columnas (`Indicador o comportamiento | Fuente y fecha | Relación con el caso | Técnica, si procede | Limitación`) con tres filas limpias:
1. **Explotación remota pre-auth de servidores web PHP vulnerables (`CVE-2026-109618`, `CVE-2026-109619`):** Fuentes F-01 (21/10), F-02 (26/10), F-05 (22/10). Técnica provisional MITRE ATT&CK: *Exploit Public-Facing Application* (`T1190`, a confirmar en P3). **Limitación:** una versión desactualizada no prueba explotación; F-02 no publica IoCs de red ni atribución.
2. **Deserialización condicionada a cambio de `session.serialize_handler` en ejecución (`CVE-2026-115560`):** Fuentes F-01 (19/11), F-04 (26/10). Técnica: pendiente de valoración en P3. **Limitación:** requiere configuración atípica (`ini_set()` antes de `session_start()` con *upload progress* activo) y no figura en KEV.
3. **Peticiones HTTP anómalas con `PHP_SESSION_UPLOAD_PROGRESS` y referencias secundarias a PoC:** Fuentes F-04 (26/10), F-05 (22/10). Técnica: pendiente de contraste en P3. **Limitación:** parámetro útil solo como señal parcial (no cubre CVE-2026-109618 según F-05); no se inspecciona código PoC por OPSEC y todo indicador futuro deberá ir neutralizado (*defanged*).

---

### Comprobación rápida de presupuesto de palabras
Si tras pegar estos cambios ejecutas `node proyecto-final/contar-palabras.mjs entregas/castilloCayetano/PF/P2/informe.md` y te acercas a 4.500 palabras, el recorte más limpio sin perder rigor está en **sintetizar el texto narrativo del Apartado 5** (dejando los detalles de cada fuente en `P2/registros/fuentes.csv`) y **no repetir citas largas de `H-01` a `H-06` dentro del Apartado 7** (cita directamente el código `H-01`, `H-04`, etc.).