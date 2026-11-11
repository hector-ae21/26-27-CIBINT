# HSE de Irlanda: ¿qué prioridades de continuidad y controles defensivos se justifican en una red sanitaria interconectada?

## Portada y control del documento

| Campo | Contenido |
|---|---|
| Autor | Eirik Alberto Rosete León, estudiante |
| Destinatario | Responsable de continuidad de negocio y seguridad de la información (CISO) en entidades de salud interconectadas. Supuesto académico |
| Organización o caso estudiado | Health Service Executive (HSE) de Irlanda y su red de salud: National Healthcare Network (NHN). |
| Fecha y versión | 11 de noviembre de 2026, v0.1 (PF-P1) |
| Periodo de los hechos | Del 16 de marzo de 2021 (envío del phishing inicial) al 21 de septiembre de 2021 (servidores y aplicaciones estables). |
| Corte de información | 30 de noviembre de 2026 a las 23:59, Europe/Madrid. |
| Condiciones de difusión | Repositorio público mediante pull request |
| Referencia del encargo y alcance aprobado | [Propuesta PF-TEMA v0.2](../TEMA/propuesta.md), aprobada con condiciones el 4 de noviembre de 2026 |

### Historial de versiones

| Versión | Fecha | Cambio principal | Responsable |
|---|---|---|---|
| 0.1 | 11/11/2026 | Primer avance (PF-P1): encargo, alcance aprobado con sus condiciones, contexto y plan de fuentes tomados de la propuesta | Eirik Alberto Rosete León |

## Índice

1. [Resumen ejecutivo](#1-resumen-ejecutivo)
2. [Requerimiento de inteligencia](#2-requerimiento-de-inteligencia)
3. [Alcance, límites y condiciones de trabajo](#3-alcance-límites-y-condiciones-de-trabajo)
4. [Contexto y cronología](#4-contexto-y-cronología)
5. [Fuentes y método](#5-fuentes-y-método)
6. [Resultados y evidencias](#6-resultados-y-evidencias)
7. [Análisis](#7-análisis)
8. [Amenazas, indicadores y comportamientos](#8-amenazas-indicadores-y-comportamientos)
9. [Confianza y limitaciones](#9-confianza-y-limitaciones)
10. [Conclusiones y recomendaciones](#10-conclusiones-y-recomendaciones)
11. [Referencias](#11-referencias)
12. [Anexos](#12-anexos)

## 1. Resumen ejecutivo

Pendiente. Se redactará al terminar el análisis.

## 2. Requerimiento de inteligencia

| Elemento | Definición para este trabajo |
|---|---|
| Destinatario y necesidad | Responsable de continuidad de negocio y seguridad de la información (CISO) en entidades de salud interconectadas. Supuesto académico |
| Decisión que se debe apoyar | Determinar cuáles son las tres prioridades de recuperación clínica y qué controles de segmentación y monitorización deben incorporarse al plan de continuidad y defensa de la red sanitaria. |
| Objeto | Health Service Executive (HSE) de Irlanda y su red de salud: National Healthcare Network (NHN). |
| Plazo | Corte de información: 30 de noviembre de 2026 a las 23:59, Europe/Madrid. Informe definitivo: 14 de diciembre de 2026 |
| Resultado solicitado | Justificar, mediante evidencia auditada (F-01), las inversiones en segmentación y contingencia manual ante la pérdida total de TI. |

### Preguntas

| ID | Pregunta de inteligencia | Decisión a la que contribuye |
|---|---|---|
| PI-01 | ¿Qué información está documentada de forma independiente sobre la intrusión, la propagación lateral y el impacto operativo entre marzo y septiembre de 2021? | Distinguir hechos probados de estimaciones iniciales. |
| PI-02 | ¿Qué dependencias entre servicios clínicos críticos y sistemas centrales (Active Directory, NHN) retrasaron la recuperación? | Priorizar la restauración y diseñar procedimientos manuales viables. |
| PI-03 | ¿Qué deficiencias de monitorización, gestión de privilegios y arquitectura de red permitieron que las alertas previas no evitaran el cifrado? | Seleccionar controles de detección y segmentación adecuados. |
| PI-04 | ¿Qué limitaciones de evidencia (logs de antivirus, forense parcial, exfiltración) reducen la confianza del análisis? | Delimitar conclusiones y definir requisitos de registro resiliente. |

## 3. Alcance, límites y condiciones de trabajo

- Objeto: Health Service Executive (HSE) de Irlanda y su red de salud: National Healthcare Network (NHN).
- Periodo de los hechos: Del 16 de marzo de 2021 (envío del phishing inicial) al 21 de septiembre de 2021 (servidores y aplicaciones estables).
- Corte de información: 30 de noviembre de 2026 a las 23:59, Europe/Madrid.
- Territorio: República de Irlanda.
- Autorización: No aplica (caso público y documental). Esta propuesta no me autoriza a acceder a sistemas, contactar con la organización ni ampliar las acciones por mi cuenta.
- Aprobación del alcance: propuesta aprobada con condiciones el 4 de noviembre de 2026.

### Condiciones de aprobación

| Condición de la resolución (4 de noviembre de 2026) | Cómo se incorpora |
|---|---|
| 1. Sustituye F-03: el enlace pasa por removepaywall.com, un servicio para eludir el muro de pago del medio. Eludir controles de acceso está prohibido por las normas de la asignatura. Cita la URL original del Irish Independent solo si puedes leerla legítimamente, o usa otra fuente de prensa de acceso abierto. | F-03 es ahora un artículo de The Journal y se añade F-04, del HSE ([apartado 11](#11-referencias)). |
| 2. Mantén las cifras de cancelaciones y del volumen exfiltrado como afirmaciones atribuidas a quien las hace, no como hechos, hasta contrastarlas. | Las cifras se presentan atribuidas a quien las hace ([apartado 4](#4-contexto-y-cronología)). |
| 3. En P1, concreta en qué fecha y con qué fuentes revisarás cada pregunta. | Fecha y fuentes de revisión de cada pregunta en el [apartado 5](#5-fuentes-y-método). |

| Dentro del alcance | Fuera del alcance | Motivo |
|---|---|---|
| OSINT documental y pasivo: informe de PwC, alertas del NCSC y prensa. | Escaneo o acceso a sistemas, consultas DNS al HSE, contacto con personal, foros o dark web, descarga de filtraciones y atribución a personas. | Esta propuesta no me autoriza a acceder a sistemas, contactar con la organización ni ampliar las acciones por mi cuenta. |
| Cronología, métricas agregadas, fallos de control documentados, TTPs y lecciones aprendidas. | Datos personales, dark web, credenciales o binarios de malware. | Por minimización (art. 5.1.c RGPD). |

### Datos, seguridad y condiciones de parada

- Datos que se conservan: Cronología, métricas agregadas, fallos de control documentados, TTPs y lecciones aprendidas.
- Datos que no se recogerán: Por minimización (art. 5.1.c RGPD): datos personales, dark web, credenciales o binarios de malware.
- Acciones expresamente excluidas: Escaneo o acceso a sistemas, consultas DNS al HSE, contacto con personal, foros o dark web, descarga de filtraciones y atribución a personas.
- Condición de parada y procedimiento de consulta: Ante credenciales, datos clínicos sin redactar, espacios restringidos o dudas de licitud, se detendrá la obtención, se anotará en la bitácora y se consultará al profesorado.

## 4. Contexto y cronología

El 14 de mayo de 2021, el Health Service Executive (HSE) de Irlanda fue víctima de un ataque de ransomware Conti, lo que obligó a apagar los sistemas de TI y desconectar la National Healthcare Network (NHN). El ataque causó una parálisis en los sistemas clínicos (correo, gestión de pacientes, laboratorios) y se aplazaron o cancelaron las citas no urgentes (F-01, F-02, F-03, F-04). Según la auditoría de PwC (F-01), el acceso inicial se produjo el 18 de marzo de 2021 a través de un archivo Excel malicioso recibido por correo de phishing. Durante ocho semanas, el atacante comprometió cuentas privilegiadas, extrajo información y se desplazó lateralmente para luego realizar el cifrado masivo. Tras la publicación de la clave de descifrado el 20 de mayo, no fue hasta el 21 de septiembre cuando se descifraron el 100 % de los servidores y se restauraron el 99 % de las aplicaciones (F-01).

Es necesario contrastar la estimación inicial de la gerencia (80 % de sistemas cifrados, F-01), las cancelaciones en hospitales (prensa, F-03) y los volúmenes de información exfiltrados reportados por el atacante. Hasta hacerlo, estas cifras se presentarán como afirmaciones de quien las hace, no como hechos. Según The Journal (F-03), varios hospitales cancelaron miles de citas desde el 14 de mayo, sin dar una cifra exacta. El NCSC (F-02) informa de que se aplazaron algunos procedimientos no urgentes mientras los hospitales activaban sus planes de continuidad. Sobre la exfiltración, el director general del HSE, Paul Reid, declaró que aún no había indicios de cuántos datos de pacientes habían obtenido los atacantes (F-03). Asimismo, el cifrado del servidor central del antivirus provocó la pérdida de trazabilidad de alertas previas (F-01).

| Fecha y zona horaria del hecho | Publicación u observación | Hecho o afirmación atribuida | Fuente | Limitación |
|---|---|---|---|---|
| 16/03/2021 | 03/12/2021 | Envío del phishing inicial | F-01 | Pendiente de verificar |
| 18/03/2021 | 03/12/2021 | Según la auditoría de PwC, acceso inicial a través de un archivo Excel malicioso recibido por correo de phishing | F-01 | Solo consta en F-01 por ahora |
| 18/03/2021 – 14/05/2021 | 03/12/2021 | Según F-01, durante ocho semanas el atacante comprometió cuentas privilegiadas, extrajo información y se desplazó lateralmente | F-01 | Solo consta en F-01 por ahora |
| 14/05/2021 | 14/05/2021; 16/05/2021; 03/12/2021 | Ataque de ransomware Conti; apagado de los sistemas de TI y desconexión de la NHN; paralización de sistemas clínicos y aplazamiento o cancelación de citas no urgentes | F-01, F-02, F-03, F-04 | — |
| Desde el 14/05/2021 | 16/05/2021 | Según The Journal, varios hospitales cancelaron miles de citas | F-03 | Afirmación atribuida, sin cifra exacta |
| 14/05/2021 | 14/05/2021 | Según el NCSC, se aplazaron algunos procedimientos no urgentes mientras los hospitales activaban sus planes de continuidad | F-02 | Afirmación atribuida |
| Sin fecha registrada | 16/05/2021 | Según el director general del HSE, Paul Reid, aún no había indicios de cuántos datos de pacientes habían obtenido los atacantes | F-03 | Afirmación atribuida |
| Sin fecha registrada | 03/12/2021 | Estimación inicial de la gerencia: 80 % de sistemas cifrados | F-01 | Estimación pendiente de contrastar |
| Sin fecha registrada | — | Volumen de información exfiltrada reportado por el atacante | Sin fuente citada todavía | Afirmación del atacante pendiente de contrastar |
| Sin fecha registrada | 03/12/2021 | Cifrado del servidor central del antivirus y pérdida de trazabilidad de alertas previas | F-01 | Solo consta en F-01 por ahora |
| 20/05/2021 | 03/12/2021 | Publicación de la clave de descifrado | F-01 | Solo consta en F-01 por ahora |
| 21/09/2021 | 03/12/2021 | Descifrado el 100 % de los servidores y restauradas el 99 % de las aplicaciones | F-01 | Solo consta en F-01 por ahora |

La hora y la zona horaria de cada hecho se completarán al revisar las fuentes.

## 5. Fuentes y método

Fuentes y acciones: OSINT documental y pasivo: informe de PwC, alertas del NCSC y prensa.

El caso dispone de información pública suficiente, proporcionada principalmente por la auditoría de PwC (F-01), que describe la cronología técnica, la respuesta organizativa y la evaluación de controles. Sin embargo, el informe forense original no es público y en F-01 se han redactado ciertos datos por motivos de seguridad, como el CVE específico explotado en un hospital o los nombres de dominios internos. El análisis se limitará a evidencia publicada en fuentes oficiales, identificando estos elementos censurados como limitaciones de información y analizando las fuentes de prensa como objeto de estudio de especulaciones sobre la situación.

Tras P1, cada pregunta se revisará en una fecha y con unas fuentes concretas. El 13 de noviembre de 2026 se revisará PI-01 con la cronología de F-01, la alerta del NCSC (F-02) y las informaciones sobre cancelaciones (F-03 y F-04). El 17 de noviembre se revisará PI-02 con la parte de respuesta y recuperación de F-01 y los servicios afectados que comunicó el HSE (F-04). El 20 de noviembre se revisará PI-03 con la evaluación de controles y las alertas previas descritas en F-01 y con las técnicas que señala el NCSC (F-02). El 23 de noviembre se revisará PI-04 con los datos redactados y la pérdida de registros del antivirus que documenta F-01. Las preguntas formarán parte de la siguiente entrega (P2).

| Fuente o grupo | Pregunta que cubre | Criterio de selección y evaluación | Limitación |
|---|---|---|---|
| F-01 · HSE / PwC | PI-01, PI-02, PI-03, PI-04 | Primaria. Evaluación pendiente | El informe forense original no es público y en F-01 se han redactado ciertos datos por motivos de seguridad |
| F-02 · NCSC Ireland | PI-01, PI-03 | Primaria. Evaluación pendiente | Pendiente |
| F-03 · The Journal | PI-01, PI-02 | Secundaria. Evaluación pendiente | Pendiente |
| F-04 · HSE | PI-01, PI-02 | Secundaria. Evaluación pendiente | Copia archivada en Internet Archive |
| F-05 · RTÉ | PI-01 | Secundaria. Evaluación pendiente | Pendiente |

Los registros de trabajo están en [`registros/fuentes.csv`](registros/fuentes.csv) y [`registros/bitacora.csv`](registros/bitacora.csv). Las fuentes se identifican como F-01, F-02…; las preguntas, como PI-01, PI-02…

## 6. Resultados y evidencias

| Hallazgo | Pregunta | Observación verificable | Fuente y fecha | Qué no demuestra |
|---|---|---|---|---|
| H-01 | PI-01 | El ataque causó una parálisis en los sistemas clínicos (correo, gestión de pacientes, laboratorios) y se aplazaron o cancelaron las citas no urgentes. | F-01, F-02, F-03, F-04, 14/05/2021; 16/05/2021; 03/12/2021 | Qué sistemas fueron cifrados directamente por el malware y cuáles fueron apagados preventivamente por el equipo de TI para contener la propagación |
| H-02 | PI-01 | Según The Journal (F-03), varios hospitales cancelaron miles de citas desde el 14 de mayo, sin dar una cifra exacta. | F-03, 16/05/2021 | El volumen total real de citas perdidas ni el impacto asistencial a nivel nacional |
| H-03 | PI-01 | El NCSC (F-02) informa que se aplazaron algunos procedimientos no urgentes mientras los hospitales activaban sus planes de continuidad. | F-02, 14/05/2021 | La eficacia operativa de esos planes de continuidad y si los procedimientos urgentes tuvieron una degradación en su calidad |
| H-04 | PI-02 | Tras la publicación de la clave de descifrado el 20 de mayo, no fue hasta el 21 de septiembre cuando se descifraron el 100 % de los servidores y se restauraron el 99 % de las aplicaciones. | F-01, p. 3, 03/12/2021 | Cómo las dependencias técnicas y la reconstrucción de sistemas explican la demora de cuatro meses en la recuperación |
| H-05 | PI-03 | Según la auditoría de PwC (F-01), durante ocho semanas, el atacante comprometió cuentas privilegiadas, extrajo información y se desplazó lateralmente para luego realizar el cifrado masivo. | F-01, p. 2, 03/12/2021 | Las brechas y fallos específicos en los controles preventivos que permitieron que la intrusión prosperara sin ser detectada durante ocho semanas |
| H-06 | PI-04 | El cifrado del servidor central del antivirus provocó la pérdida de trazabilidad de alertas previas. | F-01, p. 53, 03/12/2021 | Si los atacantes eliminaron los registros para borrar sus huellas de la intrusión |
| H-07 | PI-04 | Sobre la exfiltración, el director general del HSE, Paul Reid, declaró que aún no había indicios de cuántos datos de pacientes habían obtenido los atacantes. | F-03, 16/05/2021 | Al ser una declaración inicial, no demuestra el volumen ni la sensibilidad de los datos extraídos |

## 7. Análisis

Pendiente. La formulación de hipótesis con evidencias a favor, en contra y pendientes está prevista en P2.

### Explicaciones alternativas

| Explicación | Evidencia a favor | Evidencia en contra | Información pendiente | Valoración |
|---|---|---|---|---|
| | | | | |

### Revisión de sesgos y contradicciones

Pendiente.

## 8. Amenazas, indicadores y comportamientos

Pendiente. Se realizará una primera revisión provisional de MITRE ATT&CK en P2.

| Indicador o comportamiento | Fuente y fecha | Relación con el caso | Técnica, si procede | Limitación |
|---|---|---|---|---|
| | | | | |

## 9. Confianza y limitaciones

Pendiente. La evaluación de confianza está prevista en P3.

| Valoración | Confianza alta, media o baja | Evidencia y razonamiento | Limitación que puede cambiarla |
|---|---|---|---|
| | | | |

## 10. Conclusiones y recomendaciones

### Respuesta al encargo

Pendiente. Previsto en P3.

### Prioridades

| ID | Recomendación | Hallazgo que la sostiene | Responsable propuesto | Prioridad y plazo orientativo | Comprobación de cumplimiento |
|---|---|---|---|---|---|
| | | | | | |

### Próxima revisión

Pendiente.

## 11. Referencias

| ID | Autor u organización | Título | Fecha de publicación | URL o referencia | Fecha de consulta |
|---|---|---|---|---|---|
| F-01 | Health Service Executive (HSE) / PwC | Conti cyber attack on the HSE: Independent Post Incident Review | 03/12/2021 | <https://about.hse.ie/api/v2/download-file/file_based_publications/conti_cyber_attack_on_the_hse_full_report.pdf/> | 28/10/2026 |
| F-02 | National Cyber Security Centre (NCSC Ireland) | Ransomware Attack on Health Sector - Update | 14/05/2021 | <https://www.ncsc.gov.ie/pdfs/HSE_Conti_140521_UPDATE.pdf> | 28/10/2026 |
| F-03 | The Journal | HSE won't comment on ransom figure, as other departments take precautions after cyber attack | 16/05/2021 | <https://www.thejournal.ie/hse-cyber-attack-cancelled-appointments-5438671-May2021/> | 09/11/2026 |
| F-04 | Health Service Executive (HSE) | Appointment and service updates – HSE IT system cyber attack | 16/05/2021 | <https://web.archive.org/web/20210516223458/https://www2.hse.ie/services/hospital-service-disruptions/hse-it-system-cyber-attack.html> | 09/11/2026 |
| F-05 | RTÉ (Brian O'Donovan) | HSE cyber attack: 32,000 notified of stolen data | 09/02/2023 | <https://www.rte.ie/news/business/2023/0209/1355572-pac-hse-cyberattack/> | 10/11/2026 |

## 12. Anexos

### Anexo A. Evaluación de fuentes y evidencias

Pendiente. No se han conservado archivos como evidencia hasta este avance.

### Anexo B. Bitácora y cambios del alcance

La bitácora está en [`registros/bitacora.csv`](registros/bitacora.csv). Cambio de fuentes exigido por la resolución del 4 de noviembre de 2026: sustitución de F-03 (ver [apartado 3](#condiciones-de-aprobación)).

### Anexo C. Aplicación de los temas

Ver la tabla de aplicación de los temas en [`seguimiento.md`](seguimiento.md).

### Anexo D. Seguimiento y herramientas

Ver [`seguimiento.md`](seguimiento.md).

### Anexo E. Autoría, colaboración y uso de IA

Ver [`registro-ia.md`](registro-ia.md).
