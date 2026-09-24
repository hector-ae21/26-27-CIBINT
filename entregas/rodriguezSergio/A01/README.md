# A01 · Del dato a la inteligencia

## Estudiante

* Nombre: Sergio Rodríguez López
* Carpeta personal: `entregas/rodriguezSergio/A01/`

---

## 1. Ordena lo que sabes

### 1.1 Clasificación de las frases

| Frase | Categoría | Justificación |
| --- | --- | --- |
| **A** | **Dato** | Hecho bruto, objetivo y públicamente observable emitido por la plataforma sin agregar procesamiento ni análisis (C01, F01). |
| **B** | **Ninguna de las tres** | Expresa incertidumbre y vacíos de información; la ausencia de conocimiento no constituye por sí sola un dato, información ni inteligencia. |
| **C** | **Información** | Agrupa, contextualiza y cruza datos brutos sobre el vector de entrada y el estado de la cadena de suministro de software (C01, C03, S01, S04). |
| **D** | **Ninguna de las tres** | Se trata de un supuesto no fundamentado que incurre en la falacia de asumir que la ausencia de evidencia equivale a evidencia de ausencia. |
| **E** | **Inteligencia** | Sintetiza la información disponible, evalúa el nivel de riesgo probable y formula recomendaciones priorizadas para orientar la decisión del comité (C02, S03). |

### 1.2 Dato, información e inteligencia propios

| Capa | Formulación | Filas usadas | Qué limitación tiene |
| --- | --- | --- | --- |
| **Dato** | Hugging Face declaró la revocación preventiva de tokens de acceso asociados a Spaces tras detectar accesos no autorizados (C02, F01). | `C02`, `F01` | No desglosa la lista concreta de identidades ni confirma si afectó a credenciales de nuestra organización. |
| **Información** | El incidente afectó a la infraestructura de ejecución de Spaces y la gestión de secretos (S02, S03), mientras que la plataforma afirma que los repositorios y la distribución de modelos en el Hub no sufrieron alteración (S01, C01, C03). | `C01`, `C03`, `S01`, `S02`, `S03` | Se basa en declaraciones unilaterales del proveedor (`una_parte`) sin verificación ni auditoría externa independiente. |
| **Inteligencia** | Dado que la vulneración constatada afecta a credenciales y tokens de Spaces (S02, S03, C02) y no a la integridad de los modelos en el Hub (S01, C03), el riesgo inmediato para el servicio reside en el compromiso de nuestras credenciales API activas y no en la contaminación de los modelos en producción; por ello, procede ejecutar la rotación de credenciales (O3), auditar artefactos locales (O4) y fijar seguimiento (O7), evitando paralizar la operativa con una congelación (O2). | `C01`, `C02`, `C03`, `S01`, `S03` | Depende estrictamente de la foto de los hechos conocida a las 09:00 del 20 de julio (C01-C14); el riesgo aumentaría si revisiones posteriores ampliaran el alcance a los artefactos. |

---

## 2. Completa el requerimiento

### 2.1 Revisión de los componentes de la petición

| Componente | ¿Está? | Qué dice, o qué falta |
| --- | --- | --- |
| **Destinatario** | Sí | Su responsable de equipo (y por extensión el Comité de las 13:00). |
| **Decisión** | Parcial | Se menciona «dime si nos afecta», pero falta precisar qué conjunto de medidas operativas (O1-O7) debe adoptar la empresa. |
| **Objeto** | Sí | El impacto del incidente de seguridad de Hugging Face en los servicios de la empresa que emplean pesos abiertos. |
| **Horizonte** | Parcial | No fija marco temporal de evaluación ni periodo de validez del análisis frente a la cita de las 13:00. |
| **Alcance** | No | Falta acotar si abarca credenciales, modelos en producción, entornos de desarrollo o infraestructura en la nube. |
| **Exclusiones** | No | No explicita qué queda fuera (p. ej., investigación de atribución del atacante o auditoría interna del proveedor). |
| **Producto** | No | No especifica el formato de entrega (p. ej., nota ejecutiva de inteligencia de una página para el comité). |

### 2.2 Componentes completados

* **Destinatario**: Responsable del equipo de ciberinteligencia y miembros del Comité de Dirección de las 13:00.
* **Decisión**: Determinar qué paquete de medidas preventivas y correctivas (O1-O7 o adicionales) deben activarse antes de las 13:30 para mitigar el riesgo de la brecha.
* **Objeto**: Evaluación de la afectación potencial en nuestras credenciales corporativas, canal de descarga y modelos de pesos abiertos en uso.
* **Horizonte**: Situación analizada al 20 de julio a las 09:00, con un horizonte de revisión preventiva acotado a 72 horas.
* **Alcance**: Entorno de producción y repositorios locales que consumen artefactos o API de Hugging Face, así como secretos y tokens vinculados a la organización.
* **Exclusiones**: Se excluye la atribución del incidente a actores de amenaza específicos, la investigación forense de la plataforma de Hugging Face y el análisis de servicios de terceros no integrados.
* **Producto**: Nota ejecutiva de inteligencia en formato sintético (máximo 1 página) con evaluación de confianza y tabla de medidas recomendadas.

### 2.3 Requerimiento en una frase

> Proporcionar al Comité de las 13:00 una nota ejecutiva de inteligencia que evalúe la afectación potencial de la brecha de Hugging Face en las credenciales y modelos en uso de la empresa a fecha 20 de julio a las 09:00, recomendando las medidas mitigadoras (O1-O7) a adoptar antes de las 13:30, excluyendo investigaciones de atribución o auditorías a terceros.

### 2.4 Preguntas de inteligencia

| Prioridad | Pregunta | Te ayuda a decidir |
| --- | --- | --- |
| **1** | ¿Existen indicios o evidencias de que tokens de API o credenciales corporativas de nuestra empresa almacenadas en Spaces o plataformas vinculadas hayan sido expuestos o utilizados indebidamente? (C02, S03) | **O3** (Rotar credenciales) y **O5** (Revisar credenciales publicadas fuera). |
| **2** | ¿Se ha detectado alguna anomalía o pérdida de integridad en la cadena de suministro de artefactos/pesos de modelos descargados desde el Hub de Hugging Face? (C03, S01) | **O1** (Seguir descargando), **O2** (Congelar descargas) y **O4** (Verificar integridad). |
| **3** | ¿Cuáles son los principales vacíos de información en la declaración inicial del proveedor que justifican mantener vigilancia activa? (C01, C04) | **O7** (Mantener observación y fijar punto de revisión) y **O6** (Avisar a clientes). |

---

## 3. Planifica el ciclo

### 3.1 Recorrido por las fases

| Fase | Entrada utilizada | Decisión o tarea | Salida | Siguiente fase |
| --- | --- | --- | --- | --- |
| **Dirección y planificación** | Encargo informal del responsable a las 09:00. | Formalizar el requerimiento de inteligencia, definir alcance, priorizar preguntas clave y fijar cronograma para llegar al comité de las 13:00. | Requerimiento de inteligencia validado y plan de obtención con entrega interna a las 11:30. | **Obtención** |
| **Obtención** | Plan de obtención y fuentes iniciales (`fuentes.csv` F01-F12, `cronologia-inicial.csv` C01-C14, `superficies-plataforma.csv` S01-S10). | Recopilar comunicados oficiales, coberturas en medios y mapear superficies involucradas en el incidente de Hugging Face. | Conjunto de datos brutos sobre el incidente organizados por fecha y superficie afectada. | **Procesamiento** |
| **Procesamiento** | Conjunto de datos brutos recopilados (C01-C14, S01-S10, F01-F12). | Clasificar fuentes por su naturaleza, corroborar hechos (`una_parte`, `prensa`, `dos_partes`) y filtrar datos irrelevantes o no verificado. | Matriz de datos procesada con niveles de corroboración y mapeo directo sobre activos de la empresa. | **Análisis y producción** |
| **Análisis y producción** | Matriz de datos procesada y evaluada. | Analizar el nivel de riesgo en la infraestructura propia, evaluar la proporcionalidad de las opciones (O1-O7), determinar la confianza y redactar la nota. | Nota ejecutiva de inteligencia para el comité con recomendaciones y limitaciones explicitadas. | **Difusión** |
| **Difusión** | Nota ejecutiva de inteligencia terminada a las 12:30. | Presentar la nota de inteligencia ante el Comité de Dirección durante la reunión de las 13:00 para respaldar la toma de decisiones. | Acuerdos y decisiones tomadas por el comité sobre las medidas a aplicar. | **Retroalimentación** |
| **Retroalimentación** | Decisiones adoptadas por el comité y nuevas informaciones surgidas sobre la brecha tras las 13:00. | Evaluar si la decisión del comité requiere ajustes debido a la aparición de nuevos hechos públicos o cambios en la amenaza. | Nuevos requerimientos de inteligencia o confirmación de la validez del plan actual. | **Dirección y planificación** |

---

## 4. Responde

### 4.1 Nota para el comité

**Qué puedes afirmar el 20 de julio**

El 16 de julio de 2026, Hugging Face publicó un comunicado indicando la detección de un acceso no autorizado a su infraestructura de producción enfocado en Spaces y gestión de tokens (C01, S02, S03). La plataforma afirma expresamente que los repositorios de modelos del Hub y la cadena de suministro de software no resultaron comprometidos (C03, S01). A fecha 20 de julio a las 09:00, no consta evidencia de filtración o uso indebido específico de credenciales o tokens pertenecientes a nuestra organización (C01, C02).

**Nivel de confianza y justificación**

**Media**. La valoración de que los modelos del Hub están intactos y que la brecha se acota a Spaces descansa de forma exclusiva en la declaración oficial emitida por la propia plataforma (C01, C03), clasificada como corroboración de `una_parte` (cronologia-inicial.csv). Aunque la prensa ha dado cobertura a la noticia (F03, F04), ningún medio ha presentado una comprobación técnica independiente de los hechos (`prensa`), lo que impide elevar el nivel de confianza a alto.

**Recomendación al comité**

| Opción | ¿La activas? | Por qué, y por qué es proporcionada |
| --- | --- | --- |
| **O1** | **No** | Continuar con descargas sin controles adicionales es imprudente mientras el incidente siga bajo investigación (C01). |
| **O2** | **No** | Paralizar las descargas es desproporcionado, ya que la plataforma declara no afectada la cadena de suministro de modelos (C03, S01) y causaría un impacto operativo innecesario. |
| **O3** | **Sí** | Es la medida preventiva primordial: anula cualquier riesgo en caso de que nuestros tokens de Spaces o API hayan sido expuestos sin nuestro conocimiento (C02, S03). Su impacto operativo es muy bajo. |
| **O4** | **Sí** | Comprobar los hashes de integridad (SHA256) de los pesos almacenados localmente permite verificar que no existan modelos manipulados previamente (C03, S01). |
| **O5** | **Sí** | Escanear repositorios externos y fuentes públicas descarta que credenciales propias hayan sido filtradas o expuestas fuera de la red corporativa (S03). |
| **O6** | **No** | Innecesario y alarmista en este momento. No hay indicios ni confirmación de afectación a datos o servicios de clientes (C01). |
| **O7** | **Sí** | Establecer una ventana de revisión a las 48 horas permite reevaluar la situación con nuevos comunicados u hallazgos independientes (C01, C04). |

**Limitación**

Existe un vacío de visibilidad sobre los registros detallados de acceso a los sistemas internos de Hugging Face. Dependemos por completo de la transparencia del proveedor (C01, C03); si investigaciones posteriores demostraran compromiso en el almacenamiento de modelos del Hub, las premisas sobre la integridad de los artefactos deberán ser modificadas de inmediato.

### 4.2 Hechos, inferencias y supuestos

| Afirmación de tu nota | ¿Hecho, inferencia o supuesto? | Por qué |
| --- | --- | --- |
| «Hugging Face publicó una comunicación de incidente declarando un acceso no autorizado a su infraestructura de producción y procedió a la revocación preventiva de tokens (C01, C02).» | **Hecho** | Está sustentado de forma directa y literal por las declaraciones públicas oficiales registradas en la cronología (C01, C02, F01). |
| «Los pesos de los modelos de IA almacenados localmente no sufrieron alteraciones durante la brecha de la plataforma (C03, S01).» | **Inferencia** | Es una conclusión deductora fundamentada en la declaración de integridad del Hub por parte del proveedor (C03) y la coincidencia de hashes, aunque no se ha realizado un peritaje completo a nivel de byte en la infraestructura origen. |
| «Ningún token o secreto de API perteneciente a nuestra empresa fue extraído ni utilizado por terceros atacantes (C02, S03).» | **Supuesto** | Es una hipótesis operativa basada en la ausencia momentánea de alertas de tráfico anómalo, cuya veracidad absoluta solo se garantizará tras completar la rotación (O3) y el análisis de logs (O5). |

---

## 5. Revisa

### 5.1 Revisión de conclusiones

| Conclusión previa | ¿Cambia o se confirma? | Hecho que lo provoca | Nueva formulación |
| --- | --- | --- | --- |
| **Los artefactos de modelos alojados en el Hub mantienen su integridad y no sufrieron manipulación.** | **Se confirma** | **C18** | Las investigaciones forenses definitivas confirman que el acceso del atacante estuvo delimitado al entorno de desarrollo de Spaces sin alterar los repositorios ni la cadena de distribución del Hub de modelos (C18). |
| **La exposición de secretos se limitó exclusivamente a tokens de la plataforma Spaces.** | **Cambia** | **C16** | El análisis posterior reveló que la exfiltración de credenciales alcanzó a un ámbito más amplio de claves de API corporativas de la plataforma que el declarado inicialmente (C16). |
| **Las operaciones automatizadas de consumo mediante API no sufrieron intentos de abuso.** | **Cambia** | **C21** | Se detectaron registros de peticiones anómalas mediante tokens expuestos hacia endpoints de producción en las horas posteriores al incidente (C21). |

### 5.2 Efecto sobre la recomendación

**Sí**, cambiaría la recomendación. Aunque se sostienen las medidas preventivas internas (O3, O4, O5, O7), la revelación de una afectación más amplia en tokens de API (C16, C21) exige incorporar con carácter urgente una opción adicional: **O8 (Auditar los registros de actividad y accesos API históricos)**. Esto es necesario para comprobar si los tokens de la empresa registraron uso anómalo desde direcciones IP no autorizadas antes de que se ejecutara su rotación.

### 5.3 Conclusión sobre la retroalimentación

> La retroalimentación continua dentro del ciclo de inteligencia es indispensable para ajustar el análisis y corregir premisas iniciales basándose en la evolución real de los hechos.

---

## Fuentes

| Identificador | Fuente | URL | Fecha de consulta |
| --- | --- | --- | --- |
| F01 | Hugging Face — Security incident disclosure (July 2026) | https://huggingface.co/blog/security-incident-july-2026 | 2026-07-20 |
| F02 | Hugging Face — Anatomy of a Frontier Lab Agent Intrusion (technical timeline) | https://huggingface.co/blog/agent-intrusion-technical-timeline | 2026-07-20 |
| F03 | SecurityWeek — Hugging Face Hacked in Autonomous AI Attack | https://www.securityweek.com/hugging-face-hacked-in-autonomous-ai-attack/ | 2026-07-20 |
| F04 | BleepingComputer — Hugging Face warns an autonomous AI agent hacked its network | https://www.bleepingcomputer.com/news/security/hugging-face-breach-autonomous-ai-agent-system-internal-datasets-credentials/ | 2026-07-20 |

---

## Decisiones y limitaciones

* **Acotación temporal**: Los Pasos 1 a 4 fueron elaborados utilizando de manera exclusiva la información disponible hasta las 09:00 del 20 de julio de 2026 (`cronologia-inicial.csv`), garantizando la preservación metodológica del ejercicio.
* **Principio de proporcionalidad**: Las recomendaciones priorizan la continuidad del negocio sin descuidar la seguridad de las credenciales corporativas.

---

## Colaboración

Trabajo realizado de forma individual en todas sus fases de análisis, procesamiento e informe.

---

## Uso de inteligencia artificial

|  |  |
| --- | --- |
| **Herramienta utilizada** | Gemini y Claude |
| **Para qué la usaste** | Gemini: estructuración del documento conforme a la plantilla, validación de la lógica de trazabilidad y corrección de redacción técnica. <br> Claude: corrección de errores en la escritura del lenguaje Markdown (.md) y mejora estética del formato para la presentación final. |
| **En qué fase intervino** | Pasos 1 a 5 y revisión del informe final. |

---

## Comprobación

* [x] He trabajado sobre una copia de la plantilla, dentro de `entregas/apellidoNombre/A01/`.
* [x] He resuelto los pasos 1 a 4 solo con la cronología inicial.
* [x] Cada afirmación lleva su identificador y he comprobado que dice lo que le atribuyo.
* [x] No he interactuado con ninguna infraestructura ni servicio del caso.
* [x] No incluyo exploits, credenciales, indicadores operativos ni datos personales.
* [x] He incluido el apartado de uso de inteligencia artificial con los tres puntos.
* [x] Solo he modificado `entregas/apellidoNombre/A01/`.
