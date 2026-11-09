# Registro de uso de inteligencia artificial · Proyecto final

**Estudiante: Cayetano Castillo Ruiz**  
**Título del proyecto: Análisis de las vulnerabilidades PHP2Shell: ciclo de vida, evasión de parches y revisión de las evidencias sobre la implicación de la IA.**  
**Hito y fecha: TEMA 09/11/2026**

## Declaración

- [Con uso de IA: «He utilizado inteligencia artificial únicamente para las tareas permitidas, según los usos y evidencias que se detallan a continuación».]

## Uso 01

- **Quién:** Cayetano Castillo
- **Fecha:** 09/11/2026
- **Herramienta y modelo, si consta:** Gemini Pro 3.1
- **Para qué:** Conteo de palabras del documento a entregar
- **Hito y apartado del trabajo:** TEMA, todo el documento
- **Fuentes o texto propio utilizados como entrada:** 
- **Prompt, copiado tal cual:** Buenas, puedes realizar el conteo de palabras del contenido de este escrito: (contenido del documento)

```text
Buenas, puedes realizar el conteo de palabras del contenido de este escrito. # PF-TEMA · Propuesta individual

**Estudiante:** Cayetano Castillo Ruiz 
**Fecha y versión:** 9 de noviembre de 2026, v0.2  
**Título provisional:** Análisis de las vulnerabilidades PHP2Shell: ciclo de vida, evasión de parches y revisión de las evidencias sobre la implicación de la IA.

**Modalidad:** Caso de vulnerabilidades públicas 
**Canal de entrega:** Repositorio público mediante pull request  
**Número de palabras y método de recuento:** [Dejar en blanco hasta terminar]

## 1. Caso real y situación de partida

Recientemente, el 21 de octubre de 2026, se publicaron dos vulnerabilidades críticas en el núcleo de PHP, conocidas en conjunto como "PHP2Shell" (CVE-2026-109618 y CVE-2026-109619). Tras la liberación de los parches oficiales, se reportó rápidamente un vector de evasión (CVE-2026-115560). Diversos reportes iniciales han sugerido que el uso de herramientas de Inteligencia Artificial (LLMs) ha jugado un papel fundamental tanto en el descubrimiento de estos fallos latentes como en la rápida evasión de las mitigaciones. Este informe investigará qué afirman exactamente las fuentes sobre la participación de la IA, evaluará las evidencias que lo sustentan y analizará el ciclo de publicación y parcheo de estas vulnerabilidades.

## 2. Destinatario y decisión

| Campo | Propuesta |
|---|---|
| Destinatario | Responsable del Centro de Operaciones de Seguridad (SOC) y equipo de Respuesta a Incidentes de un proveedor de servicios de infraestructura web. |
| Condición del destinatario | Supuesto académico |
| Decisión que necesita tomar | Decidir si se deben modificar los SLA de parcheo interno y establecer la urgencia de aplicar las mitigaciones recomendadas para frenar la explotación temprana. |
| Utilidad del informe | Evaluar, en base a evidencias sólidas y no a especulaciones mediáticas, la verdadera velocidad del ciclo de vulnerabilidades PHP2Shell y qué medidas de contención son aplicables. |

## 3. Preguntas de inteligencia

| ID | Pregunta principal | Decisión a la que contribuye |
|---|---|---|
| PI-01 | ¿Qué afirman las fuentes sobre el uso de herramientas de IA en el descubrimiento de los fallos originales en PHP (PHP2Shell) y la aceleración de su evasión (CVE-2026-115560), y qué evidencias documentales aportan? | Entender las capacidades reales del adversario para ajustar los modelos de amenaza internos sin basarse en suposiciones. |
| PI-02 | ¿Qué evidencias verificables existen sobre la explotación activa de estas vulnerabilidades por parte de actores de amenazas en la actualidad? | Priorizar el despliegue de reglas de detección (IoCs/Comportamientos) en los sistemas de monitorización (SIEM/WAF). |
| PI-03 | ¿Qué medidas de mitigación y configuraciones provisionales recomiendan las fuentes oficiales para contener estas vulnerabilidades, y cuáles son sus limitaciones documentadas? | Implementar soluciones de contención realistas mientras se estabilizan y despliegan las versiones oficiales de PHP. |

## 4. Alcance y exclusiones

| Límite | Propuesta |
|---|---|
| Organización, servicio, campaña o identidad propia | Las vulnerabilidades CVE-2026-109618, CVE-2026-109619 y CVE-2026-115560 (PHP2Shell), su ciclo de publicación, parche y evasión, y el rol documentado de la IA en este proceso. |
| Periodo de los hechos | Desde la publicación inicial de la vulnerabilidad el 21 de octubre de 2026 hasta la actualidad. |
| Corte previsto de información, con zona horaria | 30 de noviembre de 2026 a las 23:59, Europe/Madrid. |
| Territorio, cuando sea relevante | Global. |
| Fuentes y acciones propuestas | Fuentes de OSINT: avisos oficiales del proyecto PHP, bases de datos de vulnerabilidades (NVD/MITRE, CISA KEV), reportes de inteligencia de amenazas e informes técnicos. |
| Datos que necesitas conservar | Identificadores de vulnerabilidades (CVE), mitigaciones oficiales recomendadas y declaraciones/evidencias sobre el uso de IA extraídas de los reportes. |
| Datos que no se recogerán | Datos de organizaciones específicas que hayan sido comprometidas ni telemetría privada. |
| Autorización disponible y condiciones | No procede (fuentes abiertas y públicas). |
| Acciones expresamente excluidas | Explotación activa de sistemas, ingeniería inversa de los *exploits* o escáneres activos contra servidores. |
| Condición de parada y procedimiento de consulta | Si se encuentra información sensible o código de explotación *Zero-Day* no divulgado públicamente, se detendrá el análisis y se consultará al profesorado. |

## 5. Viabilidad y referencias iniciales

| Referencia | Autor u organización | Título y URL | Fecha de publicación | Fecha de consulta | Primaria o secundaria | Qué pregunta ayuda a responder |
|---|---|---|---|---|---|---|
| F-01 | PHP Group | [PHP 8.x Security Advisory - Core RCE vulnerabilities] (Enlace simulado) | 21/10/2026 | 09/11/2026 | Primaria | PI-03 |
| F-02 | CISA / KEV Catalog | [Critical Vulnerabilities in PHP Require Immediate Patching] (Enlace simulado) | 26/10/2026 | 09/11/2026 | Primaria | PI-02, PI-03 |
| F-03 | Snyk / Sygnia Research | [php2shell: Evasion analysis and the role of AI] (Enlace simulado) | 27/10/2026 | 09/11/2026 | Secundaria | PI-01, PI-02 |

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
```

- **Respuesta completa:**

```text
El recuento evaluable de la propuesta es de aproximadamente 897 palabras, ajustándose perfectamente al límite establecido.

Según las instrucciones de la plantilla del proyecto, el documento tiene un límite máximo de 900 palabras, del cual se deben excluir obligatoriamente las referencias y la resolución de aprobación. El desglose de tu texto es el siguiente:

Cabecera y Secciones 1, 2, 3, 4, 6 y 7 (Contenido evaluable): ~897 palabras.

Sección 5 (Referencias): ~79 palabras (excluidas del recuento).

Sección 8 (Resolución): ~35 palabras (excluidas del recuento).

Total absoluto del texto: ~1.011 palabras.

No es necesario añadir más información para "llegar" a las 900 palabras, ya que la normativa marca ese valor como un máximo, no como un mínimo. El nivel de detalle actual es exhaustivo y cubre todas las preguntas de inteligencia y delimitaciones del alcance.

Puedes rellenar el campo de tu cabecera de la siguiente manera para entregar el documento:
Número de palabras y método de recuento: 897 palabras (procesador de texto, excluyendo referencias y resolución de aprobación).
```

- **Qué hice con la respuesta:** De modo informativo para respetar un limite impuesto en el trabajo
- **Qué comprobé y con qué fuentes originales u oficiales:** Comprobe que el uso de palabras maximo no estaba superado, (897/900)
- **Evidencia:** [Gemini](https://share.gemini.google/E6MmrLv1SZzv)
- **Usos relacionados:** Esta es la primera entrega (TEMA)
