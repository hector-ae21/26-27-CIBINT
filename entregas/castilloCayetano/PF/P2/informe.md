# Informe de Inteligencia: Análisis de las vulnerabilidades PHP2Shell y el rol documentado de la IA

## Portada y control del documento

| Campo | Contenido |
|---|---|
| Autor | Cayetano Castillo Ruiz |
| Destinatario | Responsable del Centro de Operaciones de Seguridad (SOC) [Supuesto académico] |
| Organización o caso estudiado | Vulnerabilidades públicas PHP2Shell (CVE-2026-109618, CVE-2026-109619, CVE-2026-115560) |
| Fecha y versión | 27 de noviembre de 2026, v0.3 (Avance 2 - P2) |
| Periodo de los hechos | 19 de agosto de 2026 (descubrimiento documentado) / 21 de octubre de 2026 (publicación) – Actualidad |
| Corte de información | 30 de noviembre de 2026 a las 23:59, Europe/Madrid |
| Condiciones de difusión | TLP:CLEAR. Uso académico, informe público en repositorio. |
| Referencia del encargo y alcance aprobado | PF-TEMA (`v0.2`) aprobado el 23/11/2026 condicionado a incorporar URLs reales; correcciones de P1 aplicadas en `v0.2` (27/11/2026). |

### Historial de versiones

| Versión | Fecha | Cambio principal | Responsable |
|---|---|---|---|
| 0.1 | 09/11/2026 | Creación del documento. Avance 1 (P1): Requerimientos, OPSEC, contexto inicial, plan de fuentes y primeros hallazgos. | Cayetano Castillo Ruiz |
| 0.2 | 27/11/2026 | Corrección de las 7 observaciones de P1 (23/11/2026): URLs reales verificadas, registros `fuentes.csv` y `bitacora.csv`, `README.md`, exportaciones locales en `P1/ia/`, corrección de condición de parada (sin captura ni descarga), exclusión de PoCs, separación de Snyk y Sygnia y recuento con `contar-palabras.mjs`. | Cayetano Castillo Ruiz |
| 0.3 | 27/11/2026 | Avance 2 (P2): Incorporación de Wiz Research (`F-06`), preservación local con huellas SHA-256/MD5 (`EV-01` a `EV-07`), cronología de cuatro fechas, contraste de dependencias, hallazgos `H-01` a `H-06`, análisis provisional con explicaciones alternativas (`PI-01`) y primera lectura provisional de amenazas. | Cayetano Castillo Ruiz |

## Índice

1. [Resumen ejecutivo](#1-resumen-ejecutivo)
2. [Requerimiento de inteligencia](#2-requerimiento-de-inteligencia)
3. [Alcance, límites y condiciones de trabajo](#3-alcance-límites-y-condiciones-de-trabajo)
4. [Contexto y cronología](#4-contexto-y-cronología)
5. [Fuentes y método](#5-fuentes-y-método)
6. [Resultados y evidencias](#6-resultados-y-evidencias)
7. [Análisis](#7-análisis) *(Provisional)*
8. [Amenazas, indicadores y comportamientos](#8-amenazas-indicadores-y-comportamientos) *(Provisional)*
9. [Confianza y limitaciones](#9-confianza-y-limitaciones) *(Pendiente)*
10. [Conclusiones y recomendaciones](#10-conclusiones-y-recomendaciones) *(Pendiente)*
11. [Referencias](#11-referencias)

## 1. Resumen ejecutivo

*[Nota del analista: Conforme a las instrucciones metodológicas, esta sección se redactará íntegramente al finalizar el análisis en P3/FINAL, una vez cerradas la lectura definitiva de amenazas y las recomendaciones, para no introducir conclusiones prematuras.]*

## 2. Requerimiento de inteligencia

| Elemento | Definición para este trabajo |
|---|---|
| Destinatario y necesidad | SOC y equipo de Respuesta a Incidentes de un proveedor de infraestructura web. Necesita evaluar la amenaza real de las nuevas vulnerabilidades de PHP y el ciclo acelerado de explotación. |
| Decisión que se debe apoyar | Ajuste de los SLA de parcheo interno y priorización en el despliegue de las mitigaciones oficiales recomendadas. |
| Objeto | Las vulnerabilidades PHP2Shell (publicación, parche y evasión) y el rol documentado de la IA en este proceso. |
| Plazo | Entrega del informe final el 14 de diciembre de 2026. |
| Resultado solicitado | Informe estratégico-táctico en formato Markdown con evidencias trazables. |

### Preguntas

| ID | Pregunta de inteligencia | Decisión a la que contribuye |
|---|---|---|
| PI-01 | ¿Qué afirman las fuentes sobre el uso de herramientas de IA en el descubrimiento de los fallos originales en PHP (PHP2Shell) y la aceleración de su evasión (CVE-2026-115560), y qué evidencias documentales aportan? | Entender las capacidades reales del adversario para ajustar los modelos de amenaza internos sin basarse en sesgos mediáticos. |
| PI-02 | ¿Qué evidencias verificables existen sobre la explotación activa de estas vulnerabilidades por parte de actores de amenazas en la actualidad? | Priorizar el despliegue de reglas de detección (IoCs/Comportamientos) en los sistemas de monitorización (SIEM/WAF). |
| PI-03 | ¿Qué medidas de mitigación provisionales recomiendan las fuentes oficiales para contener estas vulnerabilidades, y cuáles son sus limitaciones documentadas? | Implementar soluciones de contención realistas mientras se estabilizan y despliegan las versiones oficiales de PHP. |

## 3. Alcance, límites y condiciones de trabajo

| Dentro del alcance | Fuera del alcance | Motivo |
|---|---|---|
| Ciclo de publicación y parcheo de CVE-2026-109618, CVE-2026-109619 y CVE-2026-115560. | Análisis de telemetría de organizaciones víctimas o servidores de terceros. | Restricción legal y metodológica (solo fuentes abiertas). |
| Análisis de reportes técnicos públicos que documenten el uso de IA en estos CVEs. | Pruebas activas de concepto (PoC) contra infraestructura real. | Prohibición de explotación activa en el marco del proyecto. |
| Recomendaciones oficiales de mitigación del Proyecto PHP y agencias estatales. | Ingeniería inversa del código fuente de los *exploits* desarrollados. | Excede el tiempo del encargo y el enfoque del análisis OSINT. |

### Datos, seguridad y condiciones de parada (Evaluación Legal y OPSEC)

**Evaluación legal y manejo de datos:** La investigación se limita exclusivamente a la recolección pasiva de Inteligencia de Fuentes Abiertas (OSINT) sobre vulnerabilidades públicas. No se interactúa con infraestructura de terceros, no se realizan escaneos activos, no se recopila información personal identificable (PII) y queda expresamente excluida la descarga, apertura, ejecución o ingeniería inversa de código de explotación (PoC). Cualquier mención a la existencia de pruebas de concepto públicas se tomará únicamente de lo documentado por fuentes secundarias de análisis de amenazas, sin acceder al código fuente del *exploit*. Las copias estáticas en PDF de las fuentes consultadas en P2 se conservan en `P2/recursos/` con verificación de integridad SHA-256 y MD5 en `P2/registros/integridad.csv`.

**Medidas de OPSEC aplicadas al alcance:**
- **Separación de identidades y sesiones:** Las consultas se realizan desde un perfil dedicado o ventana privada (Opera GX en P2) sin iniciar sesión en cuentas personales ni universitarias.
- **Privacidad en la consulta:** Uso de conexión cifrada (VPN integrada con el *bypass* de motores de búsqueda desactivado y DNS sobre HTTPS) para evitar la correlación de búsquedas en blogs técnicos y bases de datos públicas. Las incidencias técnicas de conectividad (errores `504 Gateway Time-out` iniciales del proxy VPN al consultar avisos `GHSA`) quedaron documentadas en `P2/registros/bitacora.csv`.
- **Neutralización de artefactos:** Cualquier indicador técnico potencialmente malicioso o URL sensible se neutralizará (*defanging*, p. ej., `hxxps://`) antes de incorporarse al informe o a los registros locales.

**Condiciones de parada y procedimiento de consulta:** La recolección se detendrá de forma inmediata si aparece: (a) código de explotación funcional no divulgado (*Zero-Day*), (b) infraestructura activa de Comando y Control (C2), (c) datos confidenciales o personales de víctimas reales, o (d) un requisito de interacción directa con presuntos actores de amenazas. **Procedimiento:** al activarse una condición de parada **no se captura, copia ni descarga ningún contenido ni pantalla**; se cierra la consulta, se registra únicamente la categoría del incidente, la fecha/hora y la búsqueda que llevó a él en `registros/bitacora.csv`, y se consulta al profesorado por el canal privado antes de continuar. Durante la obtención de P2 no se activó ninguna condición de parada.

## 4. Contexto y cronología

El caso de estudio se centra en el descubrimiento de fallos críticos en el motor principal de PHP, afectando potencialmente a una parte significativa de la superficie web mundial. En este segundo avance se amplía la cronología inicial para distinguir explícitamente la fecha del hecho, la fecha de publicación, la fecha de observación técnica (cuando corresponde) y la fecha de consulta, manteniendo una separación estricta entre hechos técnicos confirmados y afirmaciones atribuidas a terceros.

| Fecha y zona horaria del hecho | Fecha de publicación | Observación técnica | Fecha de consulta (`Europe/Madrid`) | Hecho o afirmación atribuida | Fuente | Limitación |
|---|---|---|---|---|---|---|
| 19/08/2026 (Global) | 21/10/2026 | 19/08/2026 *(entorno del descubridor)* | 27/11/2026 21:30 | **Afirmación atribuida:** Wiz Research afirma haber descubierto la primera vulnerabilidad PHP empleando Wiz Atlas, Gemini 4 Argon y GPT-5.6 Sol. | F-06 | Declaración de parte interesada sin auditoría independiente ni publicación de *prompts* o trazas reproducibles; `F-01` acredita a los investigadores pero no certifica el uso de IA. |
| 20/08/2026 y 21/08/2026 (Global) | 21/10/2026 | 20/08/2026 (Drupal) y 21/08/2026 (WordPress) | 27/11/2026 21:30 | **Afirmación atribuida:** Wiz Research indica haber confirmado RCE preautenticación contra Drupal (20/08) y WordPress (21/08) en laboratorio. | F-06 | Demostración en entorno controlado; no acredita explotación en producción ni reproducibilidad directa en entornos endurecidos. |
| 24/08/2026 y 21/09/2026 (Global) | 21/10/2026 | N/A | 27/11/2026 21:30 | **Afirmación atribuida:** Wiz Research reporta las vulnerabilidades al equipo de seguridad de PHP (24/08) y PHP acusa recibo iniciando una corrección coordinada (21/09). | F-06 | Cronología privada de divulgación documentada por el reportador; los avisos `GHSA` de `F-01` no publican las fechas internas de triaje. |
| 21/10/2026 (UTC) | 21/10/2026 | N/A | 27/11/2026 15:05 y 21:05 | **Hecho:** PHP Group publica actualizaciones críticas y los avisos `GHSA-w8hw-w9fx-j79w` (`CVE-2026-109618`) y `GHSA-6wmf-4rv5-p3rp` (`CVE-2026-109619`), ambos con severidad Crítica (CVSS 4.0 `9.2`); CISA emite alerta urgente y NVD publica ambas fichas. | F-01, F-02, F-03 | Solo confirma la existencia de los fallos y su parcheo; no documenta explotación activa en esa fecha ni uso de IA. |
| 22/10/2026 (Global) | 22/10/2026 | Anterior o igual al 22/10/2026 *(investigadores / Sygnia)* | 27/11/2026 21:20 | **Afirmación atribuida:** Sygnia (Omer Kidron y Roey Bartov) publica su análisis sobre `php2shell`, reporta tráfico de ataque observado y RCE demostrada en laboratorio (alcance real de compromisos desconocido) y enlaza a Wiz (`F-06`). | F-05 | Su mención al papel de la IA depende de `F-06`; la telemetría sobre tráfico de ataque no es auditable de forma independiente. |
| 23/10/2026 (UTC) | 23/10/2026 *(citado el 26/10/2026)* | N/A | 27/11/2026 21:15 | **Hecho:** El proyecto PHP publica un aviso informativo preliminar para `CVE-2026-115560` (entonces reservado) y CISA actualiza su alerta del 21/10/2026. | F-01, F-02, F-04 | En esa fecha todavía no existía el parche definitivo ni el aviso completo `GHSA` de `CVE-2026-115560`. |
| 26/10/2026 (UTC) | 26/10/2026 | Anterior o igual al 26/10/2026 *(telemetría CISA)* | 27/11/2026 15:10 | **Hecho:** CISA incluye `CVE-2026-109618` y `CVE-2026-109619` en el catálogo KEV con plazo límite de remediación del 29/10/2026. | F-02, F-03 | Confirma explotación activa global, pero no atribuye los ataques, no publica IoCs ni confirma uso de IA. |
| 26/10/2026 (Global) | 26/10/2026 | N/A *(análisis documental)* | 27/11/2026 21:15 | **Afirmación atribuida:** Snyk actualiza su análisis describiendo `CVE-2026-115560` como vía de evasión parcial de `CVE-2026-109619` y recoge las mitigaciones temporales de PHP; no menciona intervención de IA. | F-04 | Su calificación inicial de «evasión parcial» precede a la publicación técnica definitiva de PHP del 19/11/2026. |
| 18/11/2026 (UTC) | 18/11/2026 | N/A | 27/11/2026 21:05 | **Hecho:** El equipo de seguridad de PHP anuncia en `php.net` lanzamientos críticos programados para el 19/11/2026 (14:00–14:30 UTC), indicando que los fallos críticos requieren configuraciones no predeterminadas o poco comunes. | F-01 | El preaviso no concretaba todavía las versiones corregidas ni los detalles técnicos completos. |
| 19/11/2026 15:08 (`GMT+1`) | 19/11/2026 | N/A | 27/11/2026 21:05 | **Hecho:** PHP Group (`@bukka`) publica el aviso completo `GHSA-658j-r8rw-q6mx` (`CVE-2026-115560`, CVSS 4.0 `9.2`, `CWE-20` y `CWE-502`), precisando la combinación atípica de configuración y acreditando a siete reportadores distintos de los de octubre. | F-01, F-03 | No incluye telemetría de explotación activa ni detalla las herramientas utilizadas por los siete reportadores. |

## 5. Fuentes y método

La recolección se limita a OSINT pasivo, priorizando fuentes primarias (PHP Group, CISA y NVD) frente a secundarias separadas por organización (Snyk y Sygnia). En P2 se añade **Wiz Research (`F-06`)**, localizada al rastrear las citas de `F-05` como origen de la afirmación sobre IA y corroborada en los créditos de `F-01`. Queda excluido el acceso a repositorios con código PoC; la fiabilidad de cada fuente y la credibilidad de sus afirmaciones se valoran por separado.

| Fuente o grupo | Pregunta | Criterio de selección y evaluación | Limitación |
|---|---|---|---|
| F-01: PHP Group (Aviso oficial y *Security Advisories*) | PI-01, PI-03 | **Primaria.** Autoridad técnica directa sobre código, CVSS/CWE, créditos y parches. Fiabilidad: Alta; credibilidad: Alta. | No documenta explotación activa ni TTPs; acredita descubridores pero no verifica uso de IA. |
| F-02: CISA (Alerta y Catálogo KEV) | PI-02, PI-03 | **Primaria.** Agencia gubernamental con telemetría validada de explotación activa. Fiabilidad: Alta; credibilidad: Alta. | No atribuye actores, no publica IoCs de red ni menciona IA. |
| F-03: NIST / NVD | PI-01, PI-02, PI-03 | **Primaria.** Repositorio estandarizado de CVEs, fechas y referencias cruzadas. Fiabilidad: Alta; credibilidad: Alta. | Depende de referencias de `F-01` y `F-02`; posible retraso de enriquecimiento. |
| F-04: Snyk Security Research | PI-01, PI-03 | **Secundaria.** Análisis técnico de parches y mitigaciones. Fiabilidad: Media-Alta; credibilidad: Media-Alta. | Enfoque comercial; su calificación de `CVE-2026-115560` como evasión parcial diverge del aviso final de `F-01`. |
| F-05: Sygnia Threat Reports | PI-01, PI-02, PI-03 | **Secundaria.** Reporte de amenazas con guía WAF y tráfico de ataque observado. Fiabilidad: Media-Alta; credibilidad: Media-Alta. | Su referencia a IA depende de `F-06`; telemetría propia no verificable externamente. |
| F-06: Wiz Research | PI-01, PI-02 | **Primaria (descubridor) / Secundaria (análisis propio).** Origen de la afirmación sobre IA y vectores de `109618`/`109619`. Fiabilidad: Media-Alta; credibilidad: Media-Alta (técnica) y Media (autodeclarada en IA). | Incentivo promocional (Wiz Atlas); «70 % de Internet» refleja cuota global de PHP y no exposición real; no cubre `CVE-2026-115560`. |

### Plan de consultas

| Fuente | Consulta concreta | Qué se busca | Pregunta |
|---|---|---|---|
| F-01 | Revisión de `php.net` (21/10 y 18/11) y los tres `GHSA` en `php/php-src` (`Ctrl+F`: *Workarounds*, *Credits*, *CVSS*). | Fechas, CVSS/CWE, créditos oficiales, mitigaciones y condición técnica de `CVE-2026-115560`. | PI-01, PI-03 |
| F-02 | Alerta de CISA y filtrado KEV por `CVE-2026-109618`, `CVE-2026-109619` y comprobación de `CVE-2026-115560`. | Explotación activa, fechas KEV, plazo límite y mención o ausencia de IA. | PI-02, PI-03 |
| F-03 | Consulta directa de las tres fichas CVE en `nvd.nist.gov`. | Fechas oficiales NVD y coherencia con `F-01` y `F-02`. | PI-01, PI-02, PI-03 |
| F-04 | Revisión del blog de Snyk (`Ctrl+F`: *AI*, *bypass*, *115560*, *mitigation*, *workaround*). | Uso de IA, encuadre de `CVE-2026-115560` y mitigaciones oficiales recogidas. | PI-01, PI-03 |
| F-05 | Revisión del reporte de Sygnia (`Ctrl+F`: *AI*, *exploit*, *WAF*, *PHP_SESSION_UPLOAD_PROGRESS*). | Explotación observada, guías WAF/SAPI y origen citado sobre IA. | PI-01, PI-02, PI-03 |
| F-06 | Revisión directa del informe de Wiz Research hallado vía `F-05`. | Modelos de IA declarados, pruebas, cronología de divulgación y alcance técnico. | PI-01, PI-02 |

### Contraste de dependencias entre fuentes

El trazado de citas impide tratar varias menciones como corroboración independiente:
- **Avisos técnicos:** `F-03` agrega datos de `F-01` y `F-02`; `F-04` se apoya en `F-01` (incluido el aviso del 23/10) y no menciona IA.
- **Origen único sobre IA:** `F-05` no aporta evidencia propia, sino que cita a **Wiz Research (`F-06`)**. `F-01` solo corrobora la autoría de los reportadores de `109618` y `109619` (`@sagitzadik-wiz`, `@amyb-oai`, `@lcfr-hax`, `@tomash-areion`), sin auditar el papel real de los modelos.
- **Fuente reservada para P3:** `F-05` enlaza un artículo de Cloudflare sobre WAF (`blog.cloudflare.com/php-vulnerabilities-waf-protection`) para contrastar detección en P3.

Los registros completos constan en `P2/registros/` (`fuentes.csv`, `bitacora.csv`, `hallazgos.csv` e `integridad.csv`) con los códigos `F-01` a `F-06`, `H-01` a `H-06` y `EV-01` a `EV-07`.

## 6. Resultados y evidencias

A continuación se consolidan los hallazgos contrastados en P2, vinculados a cada pregunta de inteligencia, fuente y evidencia local preservada (`P2/recursos/`), indicando expresamente su nivel de confianza y qué no demuestran.

| Hallazgo | Pregunta | Observación verificable | Fuente, fecha y evidencia | Confianza | Qué no demuestra |
|---|---|---|---|---|---|
| H-01 | PI-03 | PHP Group publicó parches críticos el 21/10/2026 para `CVE-2026-109618` y `CVE-2026-109619` (CVSS 4.0: `9.2`) y anunció el 18/11/2026 el lanzamiento del 19/11/2026 (14:00–14:30 UTC; `GHSA-658j-r8rw-q6mx` a las 15:08 `GMT+1`) para `CVE-2026-115560` (CVSS 4.0: `9.2`), recomendando actualizar las ramas soportadas. | F-01, F-03 (21/10 y 19/11/2026; `EV-01`, `EV-04`) | Alta | El preaviso del 18/11 no listaba las versiones exactas corregidas hasta el lanzamiento; no demuestra que las mitigaciones en `php.ini` sean suficientes por sí solas ni cubre ramas fuera de soporte. |
| H-02 | PI-02 | CISA incluyó `CVE-2026-109618` y `CVE-2026-109619` en el catálogo KEV el 26/10/2026 (plazo límite 29/10/2026), acreditando explotación activa; Sygnia (22/10/2026) reportó tráfico de ataque observado y RCE demostrada en laboratorio, precisando que el alcance real de compromisos sigue siendo desconocido. | F-02, F-05 (22/10 y 26/10/2026; `EV-02`, `EV-03`, `EV-06`) | Alta (explotación activa) / Media (alcance real) | No demuestra quién está explotando las vulnerabilidades, no aporta IoCs de red verificables, no confirma uso de IA en los *exploits* ni acredita explotación activa de `CVE-2026-115560`. |
| H-03 | PI-01 | Wiz Research (`F-06`) afirma haber descubierto el primer fallo el 19/08/2026 usando Wiz Atlas, Gemini 4 Argon y GPT-5.6 Sol y validado RCE pre-auth en Drupal (20/08) y WordPress (21/08). PHP (`F-01`) acredita como *reporters* de `109618` y `109619` a `@sagitzadik-wiz`, `@amyb-oai`, `@lcfr-hax` y `@tomash-areion`; Sygnia (`F-05`) cita a `F-06` y Snyk (`F-04`) no menciona IA. | F-06, F-01, F-05, F-04 (19/08 a 26/10/2026; `EV-01`, `EV-05`, `EV-06`, `EV-07`) | Media-Alta (autoría) / Media (grado de autonomía de IA) | No demuestra con auditoría independiente qué fracción del descubrimiento fue automática frente a análisis humano, ni demuestra uso de IA por atacantes reales. |
| H-04 | PI-01 | Snyk (`F-04`, 26/10) describe `CVE-2026-115560` como vía de evasión parcial de `CVE-2026-109619` sin mencionar IA. PHP (`F-01`, 19/11) aclara que solo ocurre bajo una configuración inusual (`session.serialize_handler` en `php_binary`/`php_serialize` cambiado a `php` en ejecución con `ini_set()` antes de `session_start()` y *upload progress* activo) y acredita a siete *reporters* distintos (`@Dviros`, `@oOSH4rpZOo`, `@Haruka-Kaya`, `@nvr0x5`, `@h1-mrz`, `@JacksonTai2007`, `@Crain99`). | F-01, F-04 (26/10 y 19/11/2026; `EV-01`, `EV-05`) | Alta | Aunque no existe prueba pública de IA en `CVE-2026-115560`, no puede descartarse al 100 % que alguno de los siete reportadores empleara asistencia de IA sin declararlo. |
| H-05 | PI-02 | Wiz (`F-06`) describe `CVE-2026-109618` como *use-after-free* en el deserializador de *upload-progress* (fuga remota de memoria de *workers* y RCE pre-auth en WordPress/Drupal/Joomla) y `CVE-2026-109619` como *use-after-free* en *fatal-error backtrace* y *OPcache type confusion* (RCE pre-auth en Drupal/WordPress). Sygnia (`F-05`) señala mayor riesgo demostrado en `Apache mod_php`, aunque `PHP-FPM` también requiere actualización. | F-06, F-05, F-01 (21/10 y 22/10/2026; `EV-01`, `EV-06`, `EV-07`) | Media-Alta | La complejidad alta (`AC:H/AT:P` en CVSS 4.0) implica que la RCE exige condiciones concretas; el titular «70 % de Internet» de `F-06` refleja cuota global de PHP y no servidores realmente explotables. |
| H-06 | PI-03 | `F-04` recoge las mitigaciones temporales de PHP (`memory_limit=-1` no sobrescribible, `post_max_size` bajo, `session.upload_progress.enabled=0` con reinicio de *workers* y `fatal_error_backtraces=0` en PHP 8.5), advirtiendo que «no hay mitigaciones completas; actualizar es la única opción segura». `F-05` añade que el WAF no sustituye al parche, debe impedirse el acceso directo al origen y no basta con filtrar `PHP_SESSION_UPLOAD_PROGRESS`, pues `CVE-2026-109618` no lo requiere. | F-04, F-05, F-01 (22/10 y 26/10/2026; `EV-01`, `EV-05`, `EV-06`) | Alta | No cuantifica el impacto operativo de estas directivas en cada aplicación (p. ej., riesgo de agotamiento de memoria al fijar `memory_limit=-1`). |

## 7. Análisis

### Análisis provisional por pregunta de inteligencia

#### PI-01 · Origen, evidencias y dependencias de la afirmación sobre IA

El contraste documental desmonta la narrativa de un ciclo completo impulsado por IA y obliga a separar dos hechos distintos:

1. **Descubrimiento inicial (`CVE-2026-109618` y `CVE-2026-109619`):** La afirmación tiene un único origen trazable: **Wiz Research (`F-06`)**, que declara haber hallado el primer fallo el 19/08/2026 con **Wiz Atlas, Gemini 4 Argon y GPT-5.6 Sol**. `F-05` solo cita a `F-06` y `F-04` no menciona la IA. Aunque `F-01` corrobora la autoría conjunta de investigadores de Wiz y OpenAI (`@sagitzadik-wiz`, `@amyb-oai`, `@lcfr-hax`, `@tomash-areion`), el grado real de contribución de los modelos es autodeclarado y carece de trazas reproducibles o auditoría externa.
2. **Tercer CVE (`CVE-2026-115560`):** Ninguna fuente acredita uso de IA. `F-04` lo califica como evasión parcial sin citar IA, `F-06` no lo incluye y `F-01` (`H-04`) aclara que exige una configuración atípica (`ini_set()` sobre `session.serialize_handler`) y acredita a siete reportadores distintos de los de octubre.

#### PI-02 · Explotación activa y exposición práctica

La entrada de `CVE-2026-109618` y `CVE-2026-109619` en **CISA KEV (`F-02`)** el 26/10/2026 confirma explotación activa con confianza alta. `F-05` reporta intentos de ataque y RCE en laboratorio, pero advierte que el alcance real de compromisos sigue siendo desconocido. Con complejidad CVSS 4.0 alta (`AC:H/AT:P`) y mayor riesgo demostrado en `Apache mod_php` frente a `PHP-FPM`, el SOC debe priorizar el parcheo sin equiparar la cuota global de PHP («70 % de Internet» en `F-06`) con compromisos masivos confirmados.

#### PI-03 · Mitigaciones oficiales y sus límites

Todas las fuentes coinciden en que **actualizar PHP es la única remediación completa** (`H-01`, `H-06`). Las directivas temporales en `php.ini` y el WAF presentan tres límites claros: fijar `memory_limit=-1` eleva el riesgo de agotamiento de memoria; filtrar solo `PHP_SESSION_UPLOAD_PROGRESS` no cubre `CVE-2026-109618` según `F-05`; y el WAF falla si existe acceso directo al origen. Para `CVE-2026-115560`, las aplicaciones que no cambian `session.serialize_handler` en ejecución no cumplen la condición vulnerable (`F-01`).

### Organizaciones, publicaciones e infraestructura (apartados sin datos justificados)

- **Organizaciones:** Se analizan solo los emisores públicos del caso (`F-01` a `F-06`). **Sin datos (justificado):** no se identifican víctimas ni actores adversarios por ausencia de atribución en fuentes primarias y exclusión en el alcance.
- **Publicaciones:** Se cubren avisos oficiales (`php.net`, `GHSA`, CISA, NVD) y tres informes públicos (`F-04`, `F-05`, `F-06`). **Sin datos (justificado):** quedan fuera foros cerrados, *dark web* y código PoC por límites legales y OPSEC.
- **Infraestructura:** **Sin datos propios (justificado):** el alcance pasivo excluye escaneos activos y análisis de servidores C2; el «70 % de Internet» de `F-06` se trata solo como contexto citado de cuota de PHP.

### Explicaciones alternativas sobre una cuestión relevante (`PI-01`)

**Cuestión analizada:** *¿Demuestran las fuentes disponibles que la IA fue determinante tanto en el descubrimiento de PHP2Shell como en `CVE-2026-115560`?*

| Explicación | Evidencia a favor | Evidencia en contra | Información pendiente | Valoración provisional |
|---|---|---|---|---|
| **E-01 · Papel determinante de la IA en todo el ciclo:** Los modelos citados por Wiz permitieron descubrir fallos complejos latentes y aceleraron nuevas variantes tras el parche. | `F-06` detalla fechas (19–21/08) y herramientas concretas; `F-01` acredita a `@sagitzadik-wiz` y `@amyb-oai`; entrada en KEV (`F-02`) en 5 días. | Sin auditoría externa ni trazas reproducibles; `F-02` no vincula ataques con IA; `F-01` atribuye `CVE-2026-115560` a 7 reportadores distintos en una configuración atípica. | Verificar antes del 30/11/2026 si Wiz publica trazas reproducibles o si algún reportador de `115560` declara uso de IA. | **Plausible con reservas en el descubrimiento inicial; no sostenida para `115560` ni para la explotación.** |
| **E-02 · Asistencia parcial de IA amplificada comercialmente + *patch diffing* humano:** Investigación humana asistida por IA en octubre (enfatizada para promocionar Wiz Atlas) y revisión humana clásica del parche en `CVE-2026-115560`. | `F-06` es parte interesada comercialmente; `F-04` no cita IA; los 7 reportadores independientes de `GHSA-658j-r8rw-q6mx` encajan con revisión tradicional de parches (*patch diffing*). | La presencia oficial de `@amyb-oai` junto a Wiz en `F-01` indica colaboración técnica real en IA y no un simple reclamo publicitario. | Comprobar publicaciones de los 7 reportadores de `115560` o comunicados adicionales de OpenAI/Google antes del 30/11/2026. | **Plausible y prudente**; explica mejor la separación de descubridores y `CVE-2026-115560`. |

### Revisión de sesgos y contradicciones

1. **Corrección del sesgo inicial:** La hipótesis de `v0.1` asociaba `CVE-2026-115560` con una evasión generada con IA; el cruce de `F-01` y `F-04` lo refuta al mostrar ausencia de citas sobre IA y siete reportadores distintos bajo una condición atípica.
2. **Contradicción técnica sobre `PHP_SESSION_UPLOAD_PROGRESS`:** `F-06` asocia `CVE-2026-109618` con *upload-progress* y `CVE-2026-109619` con *fatal-error backtrace* / *OPcache*, mientras `F-04` vincula `session.upload_progress.enabled=0` a `109619` y `F-05` indica que `109618` no exige `PHP_SESSION_UPLOAD_PROGRESS`. Esta discrepancia evidencia el riesgo de depender de un único filtro WAF y se contrastará en el texto íntegro de los `GHSA` (`F-01`) en P3.

## 8. Amenazas, indicadores y comportamientos

*(Primera lectura provisional para P2; sujeta a revisión en clase con el Tema 6 y desarrollo definitivo en P3.)*

| Indicador o comportamiento | Fuente y fecha | Relación con el caso | Técnica ATT&CK (provisional) | Limitación |
|---|---|---|---|---|
| Explotación remota sin autenticación contra el intérprete PHP (`Apache mod_php`, `PHP-FPM`) mediante *use-after-free* en deserializador de *upload-progress* o *fatal-error backtrace* / confusión de tipos en OPcache (`CVE-2026-109618`, `CVE-2026-109619`) | F-01 (21/10/2026), F-02 (26/10/2026), F-05 (22/10/2026), F-06 (21/10/2026) | Vector de acceso inicial y RCE que motiva la inclusión en CISA KEV y los intentos de ataque observados. | *Exploit Public-Facing Application* (`T1190`) — provisional | Ejecutar una versión desactualizada de PHP no demuestra compromiso; complejidad alta (`AC:H/AT:P`); `F-02` no publica IoCs ni atribución. |
| Divulgación remota no autenticada de memoria de procesos *worker* de PHP (independiente de la aplicación) | F-06 (21/10/2026) | Primitiva documentada para `CVE-2026-109618` como paso previo a corrupción de memoria y RCE. | Pendiente de mapeo refinado en P3 | Documentada por el descubridor en laboratorio; sin telemetría independiente en producción. |
| Peticiones HTTP que abusan del parámetro `PHP_SESSION_UPLOAD_PROGRESS` o buscan eludir el WAF/proxy inverso accediendo directamente al servidor de origen | F-05 (22/10/2026) | Comportamiento monitorizable en WAF y registros web como señal temprana de sondeo o intento de explotación. | *Exploit Public-Facing Application* (`T1190`) — provisional | Indicador parcial sujeto a falsos positivos; las discrepancias secundarias sobre qué CVE exige `upload_progress` se contrastarán en P3. |
| Deserialización insegura condicionada a cambio dinámico de `session.serialize_handler` vía `ini_set()` antes de `session_start()` (`CVE-2026-115560`) | F-01 (19/11/2026), F-04 (26/10/2026) | Tercer CVE asociado al ciclo PHP2Shell (`CWE-20`, `CWE-502`). | Pendiente de valoración en P3 | Exige configuración atípica; no aparece en CISA KEV ni consta evidencia pública de explotación activa. |

**Límites de esta primera lectura:** No se incluyen IoCs de red (IPs, dominios ni *hashes* de *payloads*) porque ninguna fuente consultada en P2 publica indicadores verificados de campañas activas y el alcance excluye abrir código PoC. En P3 se incorporará la referencia de Cloudflare citada por `F-05` para afinar los patrones de detección y el mapeo ATT&CK.

## 9. Confianza y limitaciones

*[Pendiente para avance P3]*

## 10. Conclusiones y recomendaciones

*[Pendiente para avance P3]*

## 11. Referencias

| ID | Autor u organización | Título | Fecha de publicación | URL o referencia | Fecha de consulta |
|---|---|---|---|---|---|
| F-01 | PHP Group | PHP News Archive (21/10 y preaviso 18/11/2026) y Security Advisories (`GHSA-w8hw-w9fx-j79w`, `GHSA-6wmf-4rv5-p3rp`, `GHSA-658j-r8rw-q6mx`) | 21/10/2026, 18/11/2026 y 19/11/2026 | `https://www.php.net/archive/2026.php#2026-10-21-5` · `https://github.com/php/php-src/security/advisories/GHSA-w8hw-w9fx-j79w` · `https://github.com/php/php-src/security/advisories/GHSA-6wmf-4rv5-p3rp` · `https://github.com/php/php-src/security/advisories/GHSA-658j-r8rw-q6mx` (`EV-01`) | 27/11/2026 (`Europe/Madrid`) |
| F-02 | CISA | Critical Vulnerabilities in PHP Require Immediate Patching y Known Exploited Vulnerabilities (KEV) Catalog | 21/10/2026 (rev. y KEV: 26/10/2026) | `https://www.cisa.gov/news-events/alerts/2026/10/21/critical-vulnerabilities-php-require-immediate-patching` · `https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-109618` · `https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-109619` (`EV-02`, `EV-03`) | 27/11/2026 (`Europe/Madrid`) |
| F-03 | NIST / NVD | NVD Vulnerability Details (`CVE-2026-109618`, `CVE-2026-109619`, `CVE-2026-115560`) | 21/10/2026 y 19/11/2026 | `https://nvd.nist.gov/vuln/detail/cve-2026-109618` · `https://nvd.nist.gov/vuln/detail/cve-2026-109619` · `https://nvd.nist.gov/vuln/detail/cve-2026-115560` (`EV-04`) | 27/11/2026 (`Europe/Madrid`) |
| F-04 | Snyk Security Research | PHP Patches Two Critical Unauthenticated RCEs (CVE-2026-109618, CVE-2026-109619): [Updated for CVE-2026-115560] | 26/10/2026 | `https://snyk.io/blog/php-patches-critical-unauthenticated-rces/` (`EV-05`) | 27/11/2026 (`Europe/Madrid`) |
| F-05 | Sygnia Threat Reports (Omer Kidron y Roey Bartov) | php2shell: Two Critical PHP Vulnerabilities Expose Web Servers to Remote Code Execution | 22/10/2026 | `https://www.sygnia.co/threat-reports-and-advisories/php2shell-two-critical-php-vulnerabilities-expose-web-servers-to-remote-code-execution/` (`EV-06`) | 27/11/2026 (`Europe/Madrid`) |
| F-06 | Wiz Research | PHP2Shell: AI Uncovers Critical RCE Vulnerabilities Affecting 70% of the Internet | 21/10/2026 | `https://www.wiz.io/blog/php2shell-php-rce` (`EV-07`) | 27/11/2026 (`Europe/Madrid`) |