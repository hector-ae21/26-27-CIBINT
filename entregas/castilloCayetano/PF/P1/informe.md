# Informe de Inteligencia: Análisis de las vulnerabilidades PHP2Shell y el rol documentado de la IA

## Portada y control del documento

| Campo | Contenido |
|---|---|
| Autor | Cayetano Castillo Ruiz |
| Destinatario | Responsable del Centro de Operaciones de Seguridad (SOC) [Supuesto académico] |
| Organización o caso estudiado | Vulnerabilidades públicas PHP2Shell (CVE-2026-109618, CVE-2026-109619, CVE-2026-115560) |
| Fecha y versión | 9 de noviembre de 2026, v0.1 (Avance 1 - P1) |
| Periodo de los hechos | 21 de octubre de 2026 - Actualidad |
| Corte de información | 30 de noviembre de 2026 a las 23:59, Europe/Madrid |
| Condiciones de difusión | TLP:CLEAR. Uso académico, informe público en repositorio. |
| Referencia del encargo y alcance aprobado | PF-TEMA aprobado con correcciones el 09/11/2026. |

### Historial de versiones

| Versión | Fecha | Cambio principal | Responsable |
|---|---|---|---|
| 0.1 | 09/11/2026 | Creación del documento. Avance 1 (P1): Requerimientos, OPSEC, contexto inicial, plan de fuentes y primeros hallazgos. | Cayetano Castillo Ruiz |

## Índice

1. [Resumen ejecutivo](#1-resumen-ejecutivo)
2. [Requerimiento de inteligencia](#2-requerimiento-de-inteligencia)
3. [Alcance, límites y condiciones de trabajo](#3-alcance-límites-y-condiciones-de-trabajo)
4. [Contexto y cronología](#4-contexto-y-cronología)
5. [Fuentes y método](#5-fuentes-y-método)
6. [Resultados y evidencias](#6-resultados-y-evidencias)
7. [Análisis](#7-análisis) *(Pendiente)*
8. [Amenazas, indicadores y comportamientos](#8-amenazas-indicadores-y-comportamientos) *(Pendiente)*
9. [Confianza y limitaciones](#9-confianza-y-limitaciones) *(Pendiente)*
10. [Conclusiones y recomendaciones](#10-conclusiones-y-recomendaciones) *(Pendiente)*
11. [Referencias](#11-referencias)

## 1. Resumen ejecutivo

*[Nota del analista: Conforme a las instrucciones metodológicas, esta sección se redactará íntegramente al finalizar el análisis, una vez procesadas todas las evidencias, para no introducir conclusiones prematuras.]*

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

**Evaluación legal y manejo de datos:** La investigación se limita exclusivamente a la recolección pasiva de Inteligencia de Fuentes Abiertas (OSINT) sobre vulnerabilidades públicas. No se interactúa con infraestructura de terceros, no se realizan escaneos activos, no se recopila información personal identificable (PII) y queda expresamente excluida la descarga, apertura, ejecución o ingeniería inversa de código de explotación (PoC). Cualquier mención a la existencia de pruebas de concepto públicas se tomará únicamente de lo documentado por fuentes secundarias de análisis de amenazas, sin acceder al código fuente del *exploit*.

**Medidas de OPSEC aplicadas al alcance:**
*   **Separación de identidades y sesiones:** Las consultas se realizan desde un perfil de navegador dedicado exclusivamente a la práctica, sin iniciar sesión en cuentas personales ni universitarias.
*   **Privacidad en la consulta:** Uso de conexión cifrada (VPN sin registros y DNS sobre HTTPS) para evitar la correlación de búsquedas en blogs técnicos y bases de datos públicas.
*   **Neutralización de artefactos:** Cualquier indicador técnico potencialmente malicioso o URL sensible se neutralizará (*defanging*, p. ej., `hxxps://`) antes de incorporarse al informe o a los registros locales.

**Condiciones de parada y procedimiento de consulta:** La recolección se detendrá de forma inmediata si aparece: (a) código de explotación funcional no divulgado (*Zero-Day*), (b) infraestructura activa de Comando y Control (C2), (c) datos confidenciales o personales de víctimas reales, o (d) un requisito de interacción directa con presuntos actores de amenazas. **Procedimiento:** al activarse una condición de parada **no se captura, copia ni descarga ningún contenido ni pantalla**; se cierra la consulta, se registra únicamente la categoría del incidente, la fecha/hora y la búsqueda que llevó a él en `registros/bitacora.csv`, y se consulta al profesorado por el canal privado antes de continuar.

## 4. Contexto y cronología

El caso de estudio se centra en el descubrimiento de fallos críticos en el motor principal de PHP, afectando potencialmente a gran parte de la superficie web mundial. Se debe distinguir entre los hechos técnicos confirmados (publicación de parches) y las afirmaciones pendientes de verificar respecto a la atribución de la velocidad de estos descubrimientos a la Inteligencia Artificial.

| Fecha y zona horaria | Publicación u observación | Hecho o afirmación atribuida | Fuente | Limitación |
|---|---|---|---|---|
| 21/10/2026 (Global) | Publicación de parches (Hecho) | El equipo de PHP publica actualizaciones de seguridad corrigiendo las vulnerabilidades iniciales PHP2Shell. | PHP Group (Aviso Oficial) | Solo confirma la existencia del fallo y su parcheo, no detalla la explotación activa. |
| 26/10/2026 (Global) | Catálogo KEV (Hecho) | CISA incluye los CVEs en su catálogo de vulnerabilidades conocidas explotadas. | CISA | Confirma explotación activa, pero no atribuye los ataques ni detalla los TTPs completos. |
| Finales Oct. 2026 | Reportes de Ciberseguridad (Afirmación pendiente) | Diversos blogs afirman que se ha descubierto una evasión del parche en tiempo récord y atribuyen esta velocidad a herramientas de IA. | Snyk / Sygnia | Afirmación de terceros pendiente de verificación mediante el análisis de evidencias (PI-01). |

## 5. Fuentes y método

El plan de recolección se basa en consultas a repositorios oficiales y técnicos. Cada fuente está seleccionada para responder directamente a una o varias Preguntas de Inteligencia (PI).

La selección de fuentes se limita a OSINT pasivo, priorizando fuentes primarias (Proyecto PHP, CISA y NVD) frente a secundarias de análisis de amenazas (Snyk y Sygnia, evaluadas por separado al tratarse de organizaciones independientes). Se excluye el acceso directo a repositorios con código de explotación (PoC); cualquier mención a su existencia se recogerá únicamente a través de lo documentado por las fuentes secundarias. La fiabilidad de cada fuente y la credibilidad de sus afirmaciones se valoran por separado.

| Fuente o grupo | Pregunta que cubre | Criterio de selección y evaluación | Limitación |
|---|---|---|---|
| F-01: PHP Group (Aviso oficial y *Security Advisories*) | PI-01, PI-03 | **Fuente primaria.** Autoridad técnica directa sobre el código base y los parches. Fiabilidad de la fuente: Alta. | No documenta explotación activa ni TTPs de terceros; suele ofrecer poco detalle sobre las herramientas usadas por los descubridores. |
| F-02: CISA (Alerta y Catálogo KEV) | PI-02, PI-03 | **Fuente primaria.** Agencia gubernamental con telemetría validada sobre explotación activa. Fiabilidad de la fuente: Alta. | Confirma explotación activa y plazos de mitigación, pero no atribuye actores ni detalla si los *exploits* se generaron con IA. |
| F-03: NIST / NVD | PI-01, PI-02, PI-03 | **Fuente primaria.** Repositorio estandarizado de CVEs, métricas CVSS y referencias cruzadas. Fiabilidad de la fuente: Alta. | Puede sufrir retrasos en el enriquecimiento técnico y depende de referencias remitidas por terceros. |
| F-04: Snyk Security Research | PI-01, PI-03 | **Fuente secundaria.** Proveedor especializado en seguridad de aplicaciones con análisis técnico del incidente. Fiabilidad de la fuente: Media-Alta; afirmaciones sobre IA pendientes de contraste. | Posible sesgo comercial o dependencia de terceros; debe comprobarse si sus afirmaciones sobre IA y `CVE-2026-115560` son propias o citadas. |
| F-05: Sygnia Threat Reports | PI-01, PI-02, PI-03 | **Fuente secundaria.** Equipo de respuesta a incidentes e inteligencia de amenazas con reporte específico sobre `php2shell`. Fiabilidad de la fuente: Media-Alta; afirmaciones pendientes de contraste. | Telemetría propia no verificable de forma independiente y posible énfasis comercial. |

### Plan de consultas

| Fuente | Consulta concreta | Qué se busca | Pregunta que cubre |
|---|---|---|---|
| F-01: PHP Group | Revisión de `php.net/archive/2026.php#2026-10-21-5` y de los avisos `GHSA-w8hw-w9fx-j79w`, `GHSA-6wmf-4rv5-p3rp` y `GHSA-658j-r8rw-q6mx` en `github.com/php/php-src`. | Fechas exactas de publicación y parcheo, versiones afectadas/corregidas, mitigaciones oficiales, créditos de descubrimiento y relación técnica real entre `CVE-2026-109619` y `CVE-2026-115560`. | PI-01, PI-03 |
| F-02: CISA | Consulta de la alerta del 21/10/2026 y filtrado en el catálogo KEV mediante `field_cve=CVE-2026-109618`, `field_cve=CVE-2026-109619` y comprobación de `CVE-2026-115560`. | Fecha exacta de inclusión en KEV, confirmación oficial de explotación activa, plazos de remediación y mitigaciones exigidas. | PI-02, PI-03 |
| F-03: NIST / NVD | Consulta directa de las fichas `cve-2026-109618`, `cve-2026-109619` y `cve-2026-115560` en `nvd.nist.gov/vuln/detail/`. | Fechas de publicación y modificación, vectores CVSS, clasificación CWE y listado de referencias primarias asociadas. | PI-01, PI-02, PI-03 |
| F-04: Snyk Security Research | Revisión del artículo `snyk.io/blog/php-patches-critical-unauthenticated-rces/` y trazado de las fuentes originales que cita. | Qué afirma exactamente sobre el papel de la IA, qué evidencias aporta (propias o heredadas), análisis de `CVE-2026-115560` y mitigaciones documentadas. | PI-01, PI-03 |
| F-05: Sygnia Threat Reports | Revisión del reporte `sygnia.co/threat-reports-and-advisories/php2shell-...` buscando secciones de explotación, detección y atribución de descubrimiento. | Evidencias de explotación observada, menciones documentadas a PoC públicas (sin abrir código), recomendaciones de detección/mitigación y afirmaciones sobre el uso de IA. | PI-01, PI-02, PI-03 |

Los registros detallados de valoración de fuentes y cada consulta ejecutada se conservan en `registros/fuentes.csv` y `registros/bitacora.csv`, respectivamente, usando identificadores correlativos (`F-01` a `F-05` para fuentes y `H-01` en adelante para hallazgos).

## 6. Resultados y evidencias

A continuación se exponen las primeras observaciones recopiladas, sin extraer conclusiones definitivas sobre la implicación de la IA hasta que se complete el análisis cruzado en el próximo avance (P2).

| Hallazgo | Pregunta | Observación verificable | Fuente y fecha | Qué no demuestra |
|---|---|---|---|---|
| H-01 | PI-03 | El aviso oficial de PHP (v8.5.12) incluye parches para el motor de *parsing*, recomendando actualizar inmediatamente. | F-01 (21/10/2026) | No demuestra que las mitigaciones en `php.ini` sean suficientes por sí solas. |
| H-02 | PI-02 | CISA añadió CVE-2026-109618 al catálogo KEV, indicando evidencia de explotación activa (*Known Exploited Vulnerability*). | F-02 (26/10/2026) | No demuestra quién está explotando la vulnerabilidad ni si usaron IA para crear el *exploit*. |

## 7. Análisis
*[Pendiente para avance P2]*

## 8. Amenazas, indicadores y comportamientos
*[Pendiente para avance P2]*

## 9. Confianza y limitaciones
*[Pendiente para avance P3]*

## 10. Conclusiones y recomendaciones
*[Pendiente para avance P3]*

## 11. Referencias

| ID | Autor u organización | Título | Fecha de publicación | URL o referencia | Fecha de consulta |
|---|---|---|---|---|---|
| F-01 | PHP Group | PHP 8.x Security Advisory - Core RCE vulnerabilities | 21/10/2026 | *(URL pendiente de registro local)* | 09/11/2026 |
| F-02 | CISA | Known Exploited Vulnerabilities Catalog | 26/10/2026 | *(URL pendiente de registro local)* | 09/11/2026 |
| F-03 | NIST | NVD - CVE-2026-109618 Detail | 23/10/2026 | *(URL pendiente de registro local)* | 09/11/2026 |
| F-04 | Snyk Research | php2shell: Evasion analysis and the role of AI | 27/10/2026 | *(URL pendiente de registro local)* | 09/11/2026 |
| F-05 | GitHub (Varios autores) | Repositorios taggeados con CVE-2026-109618 PoC | Oct/Nov 2026 | *(URL pendiente de registro local)* | 09/11/2026 |