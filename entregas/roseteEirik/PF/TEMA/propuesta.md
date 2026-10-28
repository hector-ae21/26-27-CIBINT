# PF-TEMA · Propuesta individual

**Estudiante:** Eirik Alberto Rosete León
**Fecha y versión:** 28 de octubre de 2026, v0.1
**Título provisional:** HSE de Irlanda: ¿qué prioridades de continuidad y controles defensivos se justifican en una red sanitaria interconectada?

**Modalidad:** Incidente
**Canal de entrega:** Repositorio público mediante pull request
**Número de palabras y método de recuento:** 899 palabras; se utilizó el script contar-palabras.mjs --propuesta (node proyecto-final/contar-palabras.mjs entregas/roseteEirik/PF/TEMA/propuesta.md --propuesta)

## 1. Caso real y situación de partida

El 14 de mayo de 2021, el Health Service Executive (HSE) de Irlanda fue víctima de un ataque de ransomware Conti, lo que obligó a apagar los sistemas de TI y desconectar la National Health Network (NHN). Esta acción paralizó los sistemas clínicos (correo, gestión de pacientes, laboratorios) y provocó la cancelación de citas (F-01, F-02, F-03). De acuerdo con la auditoría de PwC (F-01), el acceso inicial se produjo el 18 de marzo de 2021 a través de un archivo Excel malicioso recibido por correo de phishing. Durante ocho semanas, el atacante comprometió cuentas privilegiadas, extrajo información y se desplazó lateralmente para luego realizar el cifrado masivo. Tras la publicación de la clave de descifrado el 20 de mayo, fue hasta el 21 de septiembre se descifraron el 100 % de los servidores y se restauraron el 99 % de las aplicaciones (F-01).

Es necesario contrastar la estimación inicial de la gerencia (80 % de sistemas cifrados, F-01), las cancelaciones hospitales (prensa, F-03) y los volúmenes de información exfiltrados reportados por el atacante. Asimismo, el cifrado del servidor central del antivirus provocó la pérdida de trazabilidad de alertas previas (F-01).

## 2. Destinatario y decisión

| Campo | Propuesta |
|---|---|
| Destinatario | Responsable de continuidad de negocio y seguridad de la información (CISO) en entidades de salud interconectadas |
| Condición del destinatario | Supuesto académico |
| Decisión que necesita tomar | Determinar cuáles son las tres prioridades de recuperación clínica y qué controles de segmentación y monitorización deben incorporarse al plan de continuidad y defensa de la red sanitaria. |
| Utilidad del informe | Justificar, mediante evidencia auditada (F-01, F-02), las inversiones en segmentación y contingencia manual ante la pérdida total de TI. |

## 3. Preguntas de inteligencia

| ID | Pregunta principal | Decisión a la que contribuye |
|---|---|---|
| PI-01 | ¿Qué información está documentada de forma independiente sobre la intrusión, la propagación lateral y el impacto operativo entre marzo y septiembre de 2021? | Distinguir hechos probados de estimaciones iniciales. |
| PI-02 | ¿Qué dependencias entre servicios clínicos críticos y sistemas centrales (Active Directory, NHN) retrasaron la recuperación? | Priorizar la restauración y diseñar procedimientos manuales viables. |
| PI-03 | ¿Qué deficiencias de monitorización, gestión de privilegios y arquitectura de red permitieron que las alertas previas no evitaran el cifrado? | Seleccionar controles de detección y segmentación adecuados. |
| PI-04 | ¿Qué limitaciones e evidencia (logs de antivirus, forense parcial, exfiltración) reducen la confianza del análisis? | Delimitar conclusiones y definir requisitos de registro resiliente. |

## 4. Alcance y exclusiones

| Límite | Propuesta |
|---|---|
| Organización, servicio, campaña o identidad propia | Health Service Executive (HSE) de Irlanda y su Red Nacional de Salud (NHN). |
| Periodo de los hechos | Del 16 de marzo de 2021 (envío del *phishing* inicial) al 21 de septiembre de 2021 (servidores y aplicaciones estables). |
| Corte previsto de información, con zona horaria | 30 de noviembre de 2026 a las 23:59, Europe/Madrid. |
| Territorio, cuando sea relevante | República de Irlanda. |
| Fuentes y acciones propuestas | OSINT documental y pasivo: informe de PwC, alertas del NCSC y prensa. |
| Datos que necesitas conservar | Cronología, métricas agregadas, fallos de control documentados, TTPs y lecciones aprendidas. |
| Datos que no se recogerán | Por minimización (art. 5.1.c RGPD): datos personales, *dark web*, credenciales o binarios de *malware*. |
| Autorización disponible y condiciones; si procede, referencia privada al documento | No aplica (caso público y documental). |
| Motivo de entrega privada, si es un caso personal; canal acordado y acceso habilitado para la revisión | No aplica (pull request público). |
| Acciones expresamente excluidas | Escaneo o acceso a sistemas, consultas DNS al HSE, contacto con personal, foros o *dark web*, descarga de filtraciones y atribución a personas. |
| Condición de parada y procedimiento de consulta | Ante credenciales, datos clínicos sin redactar, espacios restringidos o dudas de licitud, se detendrá la obtención, se anotará en la bitácora y se consultará al profesorado. |

## 5. Viabilidad y referencias iniciales

| Referencia | Autor u organización | Título y URL | Fecha de publicación y consulta | Primaria o secundaria | Qué pregunta ayuda a responder |
|---|---|---|---|---|---|
| F-01 | Health Service Executive (HSE) / PwC | [Conti cyber attack on the HSE: Independent Post Incident Review](https://about.hse.ie/api/v2/download-file/file_based_publications/conti_cyber_attack_on_the_hse_full_report.pdf/) | Publicación: 03/12/2021. Consulta: 28/10/2026. | Primaria | PI-01, PI-02, PI-03, PI-04 |
| F-02 | National Cyber Security Centre (NCSC Ireland) | [Ransomware Attack on Health Sector - Update](https://www.ncsc.gov.ie/pdfs/HSE_Conti_140521_UPDATE.pdf) | Publicación: 14/05/2021. Consulta: 28/10/2026. | Primaria | PI-01, PI-03 |
| F-03 | Irish Independent | [HSE cyber attack – which hospitals are affected? Here is everything you need to know](https://www.removepaywall.com/search?url=https://www.independent.ie/irish-news/hse-cyber-attack-which-hospitals-are-affected-here-is-everything-you-need-to-know-40432288.html) | Publicación: 16/05/2021. Consulta: 28/10/2026. | Secundaria | PI-01, PI-02 |

El caso dispone de información pública suficiente, proporcionada principalmente por la auditoría de PwC (F-01), que describe la cronología técnica, la respuesta organizativa y la evaluación de controles. Sin embargo, el informe forense original no es público y en F-01 se han redactado ciertos datos por motivos de seguridad, como el CVE específico explotado en un hospital o los nombres de dominios internos. El análisis se limitará estrictamente a la evidencia publicada en fuentes oficiales, identificando estos elementos censurados como limitaciones de información, sin especular sobre ellos.

## 6. Plan de trabajo

El desarrollo del proyecto se organizará en tres fases, combinando trabajo autónomo y sesiones prácticas:

- P1 (Planificación y Obtención): Diseño del plan de fuentes vinculado a las preguntas y primeras observaciones. Se revisarán el método, las fuentes y los controles legales y de OPSEC.
- P2 (Análisis y Estructuración): Obtención de evidencias, elaboración de una cronología estructurada, contraste de cifras con la prensa y formulación de hipótesis con evidencias a favor, en contra y pendientes. Se realizará una primera revisión provisional de MITRE ATT&CK.
- P3 (Comunicación y Conclusiones): Redacción del borrador completo integrando los ocho temas, con evaluación de confianza, tabla de cambios respecto a P2 y recomendaciones dirigidas al CISO.

**Dificultades y consultas previas:**
Se consultará al profesorado si el nivel de detalle técnico de F-01 es suficiente para extraer comportamientos y realizar el mapeo necesario para P3.

## 7. Declaración

He leído las condiciones del proyecto. Esta propuesta no me autoriza a acceder a sistemas, contactar con la organización ni ampliar las acciones por mi cuenta. La recogida sistemática comenzará cuando se apruebe el alcance. Entrego mi declaración de uso o ausencia de IA en `registro-ia.md`.

## 8. Resolución de la propuesta

[No completar como si fuera una aprobación. Después de recibirla, anota su fecha, las condiciones indicadas y la versión del alcance aprobada.]

[Volver a tema y alcance](../01-tema-y-alcance.md) · [Calendario](../02-proceso-y-entregas.md)