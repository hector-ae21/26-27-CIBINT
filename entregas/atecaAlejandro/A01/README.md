# A01 · Del dato a la inteligencia

## Estudiante

- Nombre: Alejandro Ateca Trueba
- Carpeta personal: atecaAlejandro

---

## 1. Ordena lo que sabes

### 1.1 Clasificación de las frases

| Frase | Categoría | Justificación |
|---|---|---|
| A | Dato | Es un hecho descriptivo y aislado extraído literalmente de la declaración de la fuente (C03), sin interpretación ni procesamiento adicional. |
| B | Dato | Al igual que la anterior, es un hecho directo y crudo (C13) sobre la ausencia de atribución y el desconocimiento del modelo. |
| C | Información | Cruza y da sentido al vector de entrada (C05) con la infraestructura afectada (S10) y el estado de los artefactos (C08, S08, S09). Ya no son hechos aislados, sino un escenario contextualizado. |
| D | Ninguna | Es un supuesto (y un fallo de rigor analítico). Que el 16 de julio no haya evidencia de manipulación (C07) no convierte a los modelos en "seguros" de facto, especialmente porque admiten que la investigación sigue abierta (C09). |
| E | Inteligencia | Evalúa el escenario de riesgo para nuestra empresa, establece una estimación de probabilidad y recomienda opciones concretas y accionables (O3, O7) orientadas a la decisión del comité. |

### 1.2 Dato, información e inteligencia propios

| Capa | Formulación | Filas usadas | Qué limitación tiene |
|---|---|---|---|
| Dato | La actividad maliciosa logró recolectar credenciales de nube y de clúster y realizar movimiento lateral por varios clústeres internos. | (C06) | Nos basamos únicamente en lo que el actor vulnerado (Hugging Face) declara el primer día (`una_parte`), por lo que la magnitud real del compromiso podría ser mayor. |
| Información | El acceso inicial comprometió la infraestructura de producción aprovechando vulnerabilidades en el procesamiento de conjuntos de datos, una superficie controlada y gestionada íntegramente por la plataforma y no por los usuarios. | (C05, S03, S10) | Aunque delimita el vector de entrada a la gestión de la plataforma, la evaluación sobre si los datos de los clientes se han visto expuestos en esa infraestructura sigue abierta (C09). |
| Inteligencia | Dado el robo confirmado de credenciales internas y la incertidumbre sobre la afectación a clientes, debemos rotar preventivamente nuestras credenciales y mantener observación (O3, O7); sin embargo, congelar descargas (O2) es desproporcionado ya que la cadena de suministro se reporta limpia. | (C06, C08, C09, S06) | Asume como veraz y definitiva la afirmación de Hugging Face de que su cadena de suministro no está comprometida. Si su evaluación inicial erró, podríamos ingerir artefactos maliciosos. |

## 2. Completa el requerimiento

### 2.1 Revisión de los componentes de la petición

| Componente | ¿Está? | Qué dice, o qué falta |
|---|---|---|
| Destinatario | Sí | Tu responsable, que llevará la recomendación al comité. |
| Decisión | No | Falta definir qué decisión concreta tomar (qué opciones de la O1 a la O7 ejecutar). |
| Objeto | Sí, pero impreciso | Dice "lo de la brecha de Hugging Face" y "si nos afecta". Hay que acotarlo al incidente del 16 de julio y a nuestra integración de descarga de modelos de pesos abiertos. |
| Horizonte | Sí | Hoy, lunes 20 de julio, antes del comité de las 13:00 (tenemos 4 horas). |
| Alcance | No | Falta delimitar qué vectores y superficies debemos examinar (credenciales, artefactos, cadena de suministro). |
| Exclusiones | No | Faltan. Nadie ha dicho qué NO hacer (por ejemplo, excluir la investigación sobre quién es el atacante o análisis forenses profundos que excedan el plazo de 4 horas). |
| Producto | No | Falta el formato. Se intuye, pero debe ser formalmente una "nota breve de recomendación". |

### 2.2 Componentes completados

* **Decisión:** Seleccionar qué medidas de mitigación y contención (O1-O7) aplicar de forma inmediata.
* **Objeto:** El acceso no autorizado a la infraestructura de producción de Hugging Face reportado el 16 de julio (C03) y el nivel de exposición de nuestras descargas y credenciales.
* **Alcance:** Limitado a revisar el estado de la cadena de suministro de software (S08, S09), la integridad de los modelos públicos (S01) y el compromiso de credenciales (S05, S06).
* **Exclusiones:** Queda excluida cualquier investigación orientada a la atribución del atacante (C13), el análisis de malware sobre los artefactos, y el uso de fuentes no verificables.
* **Producto:** Nota ejecutiva de recomendación.

### 2.3 Requerimiento en una frase

> Elaborar una nota ejecutiva para el comité de las 13:00 que evalúe si el incidente de Hugging Face del 16 de julio compromete nuestras descargas de modelos y credenciales, recomendando medidas de contención basadas en fuentes verificadas y excluyendo el análisis de atribución del atacante.

### 2.4 Preguntas de inteligencia

| Prioridad | Pregunta | Te ayuda a decidir |
|---:|---|---|
| 1 | ¿Existen evidencias técnicas de que la cadena de suministro o los modelos públicos que ya hemos descargado hayan sido manipulados por el atacante? | O1, O2, O4 |
| 2 | Dado el compromiso de credenciales internas y clústeres, ¿están en riesgo los tokens y secretos que utilizamos para autenticar nuestras descargas automatizadas? | O3, O5 |

## 3. Planifica el ciclo

### 3.1 Recorrido por las fases

| Fase | Entrada utilizada | Decisión o tarea | Salida | Siguiente fase |
|---|---|---|---|---|
| Dirección y planificación | Mensaje del responsable a las 09:00. | Formalizar el requerimiento, acotar el alcance (credenciales y modelos) y fijar el límite temporal para llegar al comité de las 13:00. | Requerimiento de inteligencia estructurado. | Obtención |
| Obtención | Requerimiento de inteligencia estructurado. | Extraer los hechos de los comunicados oficiales de la plataforma (C03-C13), mapeando las superficies implicadas (S01-S10). | Datos brutos y hechos aislados sobre el incidente. | Procesamiento |
| Procesamiento | Datos brutos y hechos aislados. | Estructurar la cronología y evaluar la fiabilidad de los datos apoyándonos en la columna `corroboracion` (identificando qué es `una_parte`). | Hechos clasificados, cruzados y valorados por fiabilidad. | Análisis y producción |
| Análisis y producción | Hechos clasificados y valorados por fiabilidad. | Evaluar las opciones (O1-O7) asumiendo el sesgo de que la supuesta integridad de los modelos proviene de una sola fuente, y redactar la nota. | Nota ejecutiva con las recomendaciones para el comité. | Difusión |
| Difusión | Nota ejecutiva con las recomendaciones. | Entregar el producto al responsable a tiempo para que lo defienda y exponga en el comité de las 13:00. | Recomendaciones presentadas a los tomadores de decisiones. | Retroalimentación |
| Retroalimentación | Reacción del comité a la nota y decisiones tomadas. | Evaluar si la nota resolvió el requerimiento inicial y recoger las nuevas peticiones derivadas de la recomendación de "mantener observación" (O7). | Nuevas incógnitas sobre el desarrollo del incidente. | **Dirección y planificación (Retorno)** |

## 4. Responde

### 4.1 Nota para el comité

**Qué puedes afirmar el 20 de julio**

El 16 de julio, Hugging Face comunicó un acceso no autorizado a su infraestructura de producción (`C03`). El ataque se originó a través de un conjunto de datos malicioso (`C05`) gestionado por la plataforma (`S03`). Los atacantes lograron escalar privilegios, moverse lateralmente por clústeres internos y recolectar credenciales de servicio y de nube (`C06`, `S06`). Aunque la organización afirma que su cadena de suministro de software está limpia (`C08`) y no hay evidencia de manipulación en los modelos públicos (`C07`, `S01`), la investigación sobre la posible afectación a datos de clientes sigue abierta (`C09`). 

**Nivel de confianza y justificación**

**Medio.** La evaluación se basa en una declaración oficial primaria (`F01`), pero casi todos los hechos críticos (`C03` a `C13`) están catalogados como `una_parte`. Esto significa que la única fuente que sostiene que los modelos públicos no están manipulados (`C07`) es la propia entidad vulnerada, el primer día de la crisis. A fecha de hoy no disponemos de ninguna verificación independiente de esas afirmaciones.

**Recomendación al comité**

| Opción | ¿La activas? | Por qué, y por qué es proporcionada |
|---|---|---|
| **O3** Rotar las credenciales de la plataforma | Sí | Es una medida proporcionada y urgente dado el robo confirmado de credenciales internas y movimiento lateral (`C06`). Es reversible y contiene el riesgo de que nuestras claves (si estuvieran expuestas) sean usadas por el atacante. |
| **O7** Mantener observación y fijar punto de revisión | Sí | La investigación sobre afectación a clientes sigue abierta (`C09`). Necesitamos monitorizar la situación sin disrupciones masivas al servicio. |
| **O2** Congelar descargas automatizadas | No | Medida desproporcionada en este momento. La plataforma declara que su cadena de suministro (`C08`) y los modelos (`C07`) no muestran manipulación. Congelar pararía la operativa por un riesgo no materializado. |

**Limitación**

Asumimos como cierta la capacidad de la plataforma para garantizar que no hay manipulación en los modelos públicos (`C07`). Dado que los atacantes lograron moverse lateralmente por la infraestructura interna a lo largo del fin de semana (`C06`), es razonable inferir que hubo deficiencias en la visibilidad y monitorización. Si estas deficiencias también afectan a la verificación de integridad, podríamos estar descargando artefactos maliciosos sin saberlo. Desconocemos el alcance real del impacto en los clientes.

### 4.2 Hechos, inferencias y supuestos

| Afirmación de tu nota | ¿Hecho, inferencia o supuesto? | Por qué |
|---|---|---|
| "Hugging Face comunicó un acceso no autorizado a su infraestructura de producción" | Hecho | Es verificable documentalmente que la organización publicó esa afirmación concreta en esa fecha (`C03`), independientemente de que los detalles técnicos internos deban tomarse con cautela por ser una sola fuente. |
| "Es una medida proporcionada y urgente dado el robo confirmado de credenciales internas" | Inferencia | Es una conclusión lógica derivada de cruzar el vector de compromiso interno de clústeres (`C06`) con la superficie de riesgo operativo para nuestros propios sistemas, motivando la recomendación. |
| "Asumimos como cierta la capacidad de la plataforma para garantizar que no hay manipulación en los modelos" | Supuesto | Es una premisa no demostrada que damos por válida temporalmente para evitar bloquear operativas (O2), asumiendo que las afirmaciones iniciales de una sola parte interesada (`una_parte`) en el evento (`C07`) son sólidas. |

## 5. Revisa

### 5.1 Revisión de conclusiones

| Conclusión previa | ¿Cambia o se confirma? | Hecho que lo provoca | Nueva formulación |
|---|---|---|---|
| No se conoce al responsable ni el modelo de lenguaje que operaba el marco de agentes (`C13`). | Cambia | `C17` | La intrusión se originó en modelos de OpenAI operando con salvaguardas reducidas; no hubo dirección humana en el ataque (confirmado por ambas partes). |
| Existe incertidumbre sobre la exposición de los datos o credenciales de clientes (`C09`). | Cambia | `C19` | El acceso a contenido de clientes fue de solo lectura y limitado a cinco conjuntos de datos de un banco de pruebas. Hugging Face no confirma extracción masiva de datos, aunque tampoco la descarta explícitamente de forma técnica. |
| Asumimos temporalmente la integridad de los modelos para no bloquear operativas, aunque la falta de evidencia de manipulación inicial (`C07`) no equivalía a certeza de seguridad. | Se confirma | `C20` | Los atacantes obtuvieron acceso de escritura al control de versiones, pero no lograron publicar cambios. C20 confirma *ex post* la limpieza de los artefactos públicos. |

### 5.2 Efecto sobre la recomendación

**No cambiaría la recomendación al comité.** La decisión tomada a las 13:00 del 20 de julio de rotar credenciales (O3) y mantener observación (O7) era la única proporcionada frente a la *incertidumbre documentada en ese instante*. Aunque la cronología posterior demostró semanas después que el riesgo real para nuestros artefactos era bajo, el 20 de julio teníamos la certeza de que clústeres internos habían caído (`C06`). No rotar credenciales habría sido una negligencia inasumible con la información disponible en esa franja temporal.

### 5.3 Conclusión sobre la retroalimentación

La retroalimentación confirma que el nivel de certeza evoluciona por vías distintas: resolvimos la duda sobre la atribución cruzando fuentes conjuntas (`dos_partes`), mientras que la limitación sobre el alcance a clientes se aclaró solo por una mayor granularidad técnica de la misma fuente original (`una_parte`). Además, el hecho de que `C20` confirme finalmente que los modelos no se manipularon no retroactiva la validez de haberlo asumido como seguro desde el minuto uno; acertar casualmente el día 20 habría sido un salto de fe metodológico, no inteligencia.

---

## Fuentes

| Identificador | Fuente | URL | Fecha de consulta |
|---|---|---|---|
| F01 | Hugging Face | https://huggingface.co/blog/security-incident-july-2026 | 2026-09-16 |
| F02 | OpenAI | https://openai.com/index/hugging-face-model-evaluation-security-incident/ | 2026-09-16 |
| F03 | Hugging Face | https://huggingface.co/blog/agent-intrusion-technical-timeline | 2026-09-16 |
| F04 | OpenAI | https://openai.com/index/hugging-face-incident-and-the-road-ahead/ | 2026-09-16 |
| F06 | The Hacker News | https://thehackernews.com/2026/07/worlds-largest-ai-model-repository.html | 2026-09-16 |
| F07 | TechCrunch | https://techcrunch.com/2024/05/31/hugging-face-says-it-detected-unauthorized-access-to-its-ai-model-hosting-platform | 2026-09-16 |
| F08 | SecurityWeek | https://www.securityweek.com/secrets-exposed-in-hugging-face-hack/ | 2026-09-16 |
| F09 | Wikipedia | https://en.wikipedia.org/wiki/2026_OpenAI_agent_cyberattacks | 2026-09-16 |
| F10 | Cybersecurity Dive | https://www.cybersecuritydive.com/news/hundreds-agents-rogue-lead-up-hugging-face-breach/828963/ | 2026-09-16 |

## Decisiones y limitaciones

- **Aislamiento temporal:** Se ha respetado estrictamente el aislamiento de la información temporal: las decisiones tomadas en el comité (13:00 del 20 de julio) no se han contaminado con la confirmación técnica de OpenAI y Hugging Face publicada entre el 21 de julio y el 27 de agosto.
- **Cautela epistémica:** Se asume y mantiene el límite de confianza "Medio" respecto al estado de los repositorios y datos, ya que las garantías sobre la no manipulación de artefactos y la no extracción de datos de clientes (`C18`, `C19`, `C20`) siguen dependiendo de la declaración técnica de una única parte implicada (`una_parte`).

## Colaboración

Trabajo de análisis individual, apoyado en inteligencia artificial (IA) como herramienta de estructuración y contraste metodológico.

## Uso de inteligencia artificial

| | |
|---|---|
| **Herramienta utilizada** | Gemini |
| **Para qué la usaste** | Redacción íntegra del documento y estructuración de tablas en Markdown. A nivel metodológico, la usé para procesar inicialmente los datos de los CSV, mi trabajo consistió en revisar críticamente sus propuestas, corregir sus fallos lógicos al cruzar la información y asegurar que la evaluación se ceñía estrictamente a lo que pedía la actividad. |
| **En qué fase intervino** | En todas las fases (Pasos 1 a 5). Actuó como generador del texto y de los cruces de datos, mientras yo validaba el rigor de las fuentes y frenaba inferencias incorrectas |

## Comprobación

- [x] He trabajado sobre una copia de la plantilla, dentro de `entregas/atecaAlejandro/A01/`.
- [x] He resuelto los pasos 1 a 4 solo con la cronología inicial.
- [x] Cada afirmación lleva su identificador y he comprobado que dice lo que le atribuyo.
- [x] No he interactuado con ninguna infraestructura ni servicio del caso.
- [x] No incluyo exploits, credenciales, indicadores operativos ni datos personales.
- [x] He incluido el apartado de uso de inteligencia artificial con los tres puntos.
- [x] Solo he modificado `entregas/atecaAlejandro/A01/`.