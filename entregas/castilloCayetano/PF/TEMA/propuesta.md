# PF-TEMA · Propuesta individual

**Estudiante:** Cayetano Castillo Ruiz   
**Fecha y versión:** 27 de octubre de 2026, v0.1  
**Título provisional:** El uso de IA en el descubrimiento acelerado de vulnerabilidades: Análisis de amenaza sobre los fallos críticos de PHP2Shell y sus evasiones.

**Modalidad:** Incidente / Exposición  
**Canal de entrega:** Repositorio público mediante pull request  
**Número de palabras y método de recuento:** 781 palabras (herramienta de conteo del procesador de texto, excluyendo portadas e índices). (Gemini Pro)

## 1. Caso real y situación de partida

Recientemente, el 21 de octubre de 2026, se publicaron dos vulnerabilidades críticas en el núcleo de PHP, conocidas en conjunto como "PHP2Shell" (CVE-2026-109618 y CVE-2026-109619), que permiten la ejecución remota de código (RCE) sin autenticación. Dado que PHP impulsa aproximadamente el 70 % de los sitios web a nivel mundial, el impacto de este fallo es masivo. Lo más destacable de este incidente es que las vulnerabilidades, latentes en el código fuente de PHP durante más de una década, fueron descubiertas gracias al uso de modelos avanzados de inteligencia artificial (como GPT-5.6 Sol) durante auditorías de seguridad. 

Tras la liberación de los parches oficiales de PHP (versiones 8.5.12, 8.4.27, 8.3.36 y 8.2.35), se reportó rápidamente un vector de evasión parcial (asignado como CVE-2026-115560) que afectaba a una de las mitigaciones. Este escenario evidencia una tendencia emergente: la IA no solo facilita la identificación de fallos *Zero-Day* ocultos, sino que reduce drásticamente el tiempo necesario para encontrar *bypasses* a los parches recién emitidos. Este informe analizará cómo la IA acelera este ciclo de vulnerabilidades y el impacto operativo que tiene sobre la defensa de las infraestructuras web expuestas.

## 2. Destinatario y decisión

| Campo | Propuesta |
|---|---|
| Destinatario | Responsable del Centro de Operaciones de Seguridad (SOC) y equipo de Respuesta a Incidentes de un proveedor de servicios de hosting o infraestructura web. |
| Condición del destinatario | Supuesto académico |
| Decisión que necesita tomar | Decidir si se deben modificar los tiempos del ciclo de gestión de vulnerabilidades (SLA de parcheo), establecer bloqueos perimetrales estrictos y determinar la urgencia de aplicar medidas provisionales (como inhabilitar configuraciones específicas en `php.ini` o desplegar reglas SIGMA/WAF) ante la capacidad de la IA para generar *exploits* antes de poder parchear. |
| Utilidad del informe | Evaluar si el uso de IA por parte de investigadores y atacantes requiere un cambio de paradigma táctico en la defensa perimetral de la organización, justificando inversiones en mitigación dinámica frente a los ciclos de parcheo tradicionales. |

## 3. Preguntas de inteligencia

| ID | Pregunta principal | Decisión a la que contribuye |
|---|---|---|
| PI-01 | ¿De qué manera están facilitando las herramientas de IA el descubrimiento de los fallos originales en PHP (PHP2Shell) y sus posteriores evasiones de parches (CVE-2026-115560)? | Entender las capacidades del adversario para ajustar los modelos de amenaza internos. |
| PI-02 | ¿Existen evidencias de que actores de amenazas estén explotando activamente estas vulnerabilidades (CVE-2026-109618 y CVE-2026-109619), y qué TTPs emplean tras el descubrimiento impulsado por IA? | Priorizar el despliegue de reglas de detección (IoCs/Comportamientos) en los sistemas de monitorización (SIEM/WAF) y las búsquedas retrospectivas. |
| PI-03 | ¿Qué medidas de mitigación provisionales y configuraciones de `php.ini` (ej. `session.upload_progress.enabled=0`, `pm.max_requests = 1`) son efectivas cuando el ciclo oficial de parches es superado por la velocidad de descubrimiento impulsada por IA? | Implementar soluciones de contención de emergencia mientras se estabilizan las versiones oficiales de PHP. |

## 4. Alcance y exclusiones

| Límite | Propuesta |
|---|---|
| Organización, servicio, campaña o identidad propia | Ecosistema de servidores expuestos que ejecutan versiones vulnerables de PHP (desde 5.4 hasta las recientes sin parchear) afectadas por la campaña PHP2Shell. |
| Periodo de los hechos | Desde la publicación inicial de la vulnerabilidad el 21 de octubre de 2026 hasta la actualidad. |
| Corte previsto de información, con zona horaria | 27 de octubre de 2026, Europe/Madrid. |
| Territorio, cuando sea relevante | Global. |
| Fuentes y acciones propuestas | Fuentes de OSINT: bases de datos de vulnerabilidades (NVD/MITRE, CISA KEV), avisos oficiales del proyecto PHP, reportes de inteligencia de amenazas (Sygnia, Snyk, Wiz) y repositorios de pruebas de concepto (PoC) en GitHub. |
| Datos que necesitas conservar | Identificadores de vulnerabilidades (CVE-2026-109618, CVE-2026-109619, CVE-2026-115560), reglas de detección (SIGMA), TTPs asociados a la explotación de memoria en PHP y fragmentos de código neutralizado. |
| Datos que no se recogerán | Datos personales de operadores de infraestructura afectada ni de investigadores de seguridad. |
| Autorización disponible y condiciones; si procede, referencia privada al documento | No procede (fuentes abiertas y públicas). |
| Acciones expresamente excluidas | Explotación activa de sistemas, ingeniería inversa de los *exploits* originales o interacción directa con atacantes en foros clandestinos. |
| Condición de parada y procedimiento de consulta | Si se encuentra información sensible de víctimas reales o código de explotación *Zero-Day* no divulgado públicamente, se detendrá el análisis y se consultará al profesorado. |

## 5. Viabilidad y referencias iniciales

| Referencia | Autor u organización | Título y URL | Fecha de publicación y consulta | Primaria o secundaria | Qué pregunta ayuda a responder |
|---|---|---|---|---|---|
| F-01 | CISA / KEV Catalog | [Critical Vulnerabilities in PHP Require Immediate Patching](https://www.cisa.gov/news-events/alerts/2026/10/21/critical-vulnerabilities-php-require-immediate-patching) | 26 de octubre de 2026 | Primaria | PI-02, PI-03 |
| F-02 | Snyk Security Research | [PHP fixes two critical unauthenticated RCE flaws](https://snyk.io/blog/php-patches-critical-unauthenticated-rces/) | 27 de octubre de 2026 | Secundaria | PI-01, PI-03 |
| F-03 | Sygnia Threat Reports | [php2shell: Two Critical PHP Vulnerabilities Expose Web Servers to Remote Code Execution](https://www.sygnia.co/threat-reports-and-advisories/php2shell-two-critical-php-vulnerabilities-expose-web-servers-to-remote-code-execution/) | 22 de octubre de 2026 | Secundaria | PI-02 |

## 6. Plan de trabajo

El desarrollo del proyecto se estructurará en los tres avances previstos, combinando el trabajo autónomo con el análisis en las sesiones prácticas:

- **P1 (Planificación y Obtención):** Configuración del entorno de trabajo y recolección sistemática de información en fuentes abiertas (OSINT). Se identificarán los detalles técnicos de los CVEs asociados a PHP2Shell, los repositorios de GitHub con pruebas de concepto (PoC) y los boletines de seguridad de CISA. En clase, se ajustarán las consultas de búsqueda y se validará la calidad de las fuentes primarias frente a las secundarias.
- **P2 (Análisis y Estructuración):** Procesamiento de las evidencias obtenidas, extracción de Indicadores de Compromiso (IoCs) y mapeo de los comportamientos de los atacantes usando la matriz MITRE ATT&CK. En clase, se trabajará la justificación analítica para asegurar que cada hallazgo soporta adecuadamente una conclusión y se debatirán posibles sesgos de confirmación al evaluar si un ataque fue realmente generado con IA.
- **P3 (Comunicación y Conclusiones):** Redacción final del informe, consolidación de las recomendaciones para el destinatario (equipo SOC/Respuesta a Incidentes) y elaboración del resumen ejecutivo. En clase, se someterán a revisión las limitaciones del análisis y la viabilidad técnica de las mitigaciones propuestas frente a la evasión de parches.

**Dificultades y consultas previas:** 
La principal dificultad anticipada es la evolución rápida del incidente, dado que la IA está generando nuevas variantes o *bypasses* (como el reciente CVE-2026-115560) casi a diario. Si el volumen de información crece de forma desproporcionada, se consultará al profesorado para acotar temporalmente el corte de información o centrarse exclusivamente en el vector de RCE principal.

## 7. Declaración

He leído las condiciones del proyecto. Esta propuesta no me autoriza a acceder a sistemas, contactar con la organización ni ampliar las acciones por mi cuenta. La recogida sistemática comenzará cuando se apruebe el alcance. Entrego mi declaración de uso o ausencia de IA en `registro-ia.md`.

## 8. Resolución de la propuesta

*(Espacio reservado. No rellenar hasta recibir la evaluación del profesor. Una vez devuelta la corrección, se anotará aquí la fecha, las condiciones impuestas y la versión del alcance definitivamente aprobada).*
