# A01 · Del dato a la inteligencia

## Estudiante

- Nombre: Eirik Alberto Rosete León
- Carpeta personal: [/entregas/roseteEirik](/entregas/roseteEirik/)

---

## 1. Ordena lo que sabes

### 1.1 Clasificación de las frases

| Frase | Categoría | Justificación |
|---|---|---|
| A | Dato | Es un suceso reportado con una fecha, sin relación con algún otro dato o contexto (C03) |
| B | Información | Se identifica que hacen falta datos y eso conlleva estructurar lo que conocemos. (C13) |
| C | Información | Se hace uso de datos (C05, C08) entrelazados organizados en un mismo contexto: se identificó qué plataformas se vieron afectadas (S06), que fueron meramente internas (C06). |
| D | Ninguna | Es un supuesto no fundamentado, está saltando a una conclusión por algo no confirmado, que no equivale a inexistente (C07) |
| E | Inteligencia | Establece un juicio de probabilidad estimativo, está orientado a tomar una decisión antes del comité y propone acciones inmediatas (C06, C08) |



### 1.2 Dato, información e inteligencia propios

| Capa | Formulación | Filas usadas | Qué limitación tiene |
|---|---|---|---|
| Dato | La actividad escaló hasta el acceso a nivel de nodo, recolección de credenciales de nube y de clúster, y movimiento lateral por varios clústeres internos a lo largo de un fin de semana. | C06 | El dato no aclara qué servicios o credenciales propias podrían haber estado en esos clústeres |
| Información | El acceso no autorizado vulneró credenciales y conjuntos de datos internos, afectando los clústeres y nodos de producción un fin de semana completo | C03, C04, C06, S06, S10 | No se especifica si los conjuntos de datos afectaron a cuentas o tokens de usuarios externos |
| Inteligencia | Tomando en cuenta la extracción de conjuntos de datos y posible asociación de credenciales internas con productos o tokens de organizaciones y usuarios, es posible que las credenciales estén expuestas, por lo que es recomendable hacer una rotación de credenciales | C04, S06, S07, O3 | Se sigue evaluando el impacto a clientes externos (C09) por lo que no se sabe si las credenciales fueron expuestas o la rotación es una medida preventiva |

---

## 2. Completa el requerimiento

### 2.1 Revisión de los componentes de la petición

> «He visto lo de la brecha de Hugging Face. Mira a ver todo lo que haya y dime si nos afecta.»

| Componente | ¿Está? | Qué dice, o qué falta |
|---|---|---|
| Destinatario | Parcial | Es impreciso, puede inferirse que es mi responsable porque menciona la palabra "*Dime*" |
| Decisión | No | Únicamente está preguntando si nos afecta, no está solicitando una decisión ni acciones/medidas que implementar. |
| Objeto | Sí | Nos comunica lo de la brecha a Hugging Face, pero desconocemos qué elementos y servicios manejamos nosotros o con qué es que estamos relacionados con el incidente; está delegando todo el trabajo para que "mire todo lo que haya" |
| Horizonte | No | No hay una solicitud expresa de tiempo o urgencia en la petición del responsable |
| Alcance | No | La información acerca de la cronología inicial y los hechos son datos públicos, no nos fueron brindados. No tenemos datos de qué "nos afecta", es decir, no hay perímetro interno delimitado para investigar |
| Exclusiones | No | No limita ni prohíbe acciones a realizar |
| Producto | No | Dice "*Dime*", pero no especifica el formato de entrega |

### 2.2 Componentes completados

| Componente | Dato faltante o sin concretar |
|---|---|
| Destinatario | El responsable de seguridad del equipo de ciberinteligencia |
| Decisión | Determinar qué medidas de contención aplicar sobre los servicios, credenciales e infraestructura vinculados al incidente |
| Objeto | Brecha de seguridad en Hugging Face y exposición de credenciales de acceso |
| Horizonte | Antes de las 13:00, con una recomendación para presentar en el comité |
| Alcance | Limitar la investigación a nuestra propia infraestructura que integren servicios de Hugging Face |
| Exclusiones | Excluir el uso de elementos vulnerados que hayan sido expuestos al ataque, como tokens potencialmente comprometidos |
| Producto | Reporte de situación, elementos que tienen mayor probabilidad de haber sido vulnerados y brindar propuesta de acción inmediata |

### 2.3 Requerimiento en una frase

> Determinar antes de las 13:00 si el ciberataque realizado a Hugging Face tiene un impacto y si vulnera los servicios, credenciales e infraestructura internos asociados al incidente y proponer un informe al responsable del equipo de ciberinteligencia con medidas de acción inmediata, omitiendo cualquier prueba con tokens comprometidos

### 2.4 Preguntas de inteligencia

| Prioridad | Pregunta | Te ayuda a decidir |
|---:|---|---|
| 1 | ¿Existe riesgo directo de que el compromiso de credenciales internas de producción (C04, C06, S06, S10) haya alcanzado a nuestras credenciales de usuario o tokens de organización (S05) asociadas a la plataforma? | O3 (Rotar las credenciales de la plataforma) y O5 (Revisar credenciales propias publicadas fuera). |
| 2 | ¿La extracción de conjuntos de datos internos (C04, S07) o el acceso a nodos de producción (C06) afectaron la integridad de los modelos o librerías (S01, S08) que consumimos en nuestros servicios, más allá de lo declarado por una parte del caso, la plataforma (C07, C08)? | O2 (Congelar las descargas automatizadas) y O4 (Verificar la integridad de los artefactos ya descargados) |

---

## 3. Planifica el ciclo

### 3.1 Recorrido por las fases

| Fase | Entrada utilizada | Decisión o tarea | Salida | Siguiente fase | 
|---|---|---|---|---|
| Dirección y planificación | Petición informal del responsable "He visto lo de la brecha" y las opciones que tenemos antes del comité | Concretar los 7 componentes del requerimiento, fijar el horizonte a las 13:00, establecer las exclusiones (no interactuar con tokens de la plataforma externa) y priorizar las 2 preguntas de inteligencia | Requerimiento de inteligencia acotado y plan de investigación centrado en credenciales (S05, S06) e integridad de artefactos (S01, S08) | Obtención | 
| Obtención | Requerimiento acotado y las 2 preguntas de inteligencia priorizadas | Recopilar las evidencias públicas (C01–C14), superficies (S01–S10) y fuentes (F01–F12), respetando la prohibición de escaneo externo | Muestra de eventos, declaraciones oficiales de la plataforma y referencias de superficies sin procesar | Procesamiento | 
| Procesamiento | Muestra de hechos (C01–C14) y superficies de la plataforma (S01–S10) | Cruzar e integrar los hechos con las superficies afectadas (C04, C06 con S06, S10), clasificar por grado de corroboración (una_parte, prensa) y aislar las lagunas explícitas (C09, C13) | Matriz estructurada de eventos procesados, verificar impacto en credenciales internas e inventario de lagunas de información | Análisis y producción | 
| Análisis y producción | Matriz estructurada de eventos, superficies e inventario de lagunas (C13) | Evaluar hipótesis de riesgo debido a la falta de evidencia de manipulación en artefactos (C07, C08) con riesgo en credenciales (C04, C06), y detectar que la laguna en datos de clientes (C09) exige verificar registros de auditoría interna propios | Detección de laguna crítica sobre afectación a tokens de la empresa (S05) que requiere consultar únicamente los registros de auditoría interna locales | Obtención (Retorno para recuperar registros locales de auditoría pasivos antes del comité) | 
| Difusión | Valoración de impacto validada con nivel de confianza (media) (una_parte), opciones existentes (O1–O7) y limitaciones explícitas (C09) | Adaptar el resultado para el comité de las 13:00 mediante una Nota de Situación ejecutiva orientada a la toma de decisiones | Nota de Situación ejecutiva terminada con recomendación de activar O3 (rotar credenciales) y O7 (fijar punto de revisión) para el responsable | Retroalimentación | 
| Retroalimentación | Observaciones, preguntas y acuerdos adoptados por el comité después de la reunión de las 13:00 | Evaluar si las decisiones tomadas o la aparición de nuevas publicaciones por parte de la plataforma requieren redefinir las preguntas de investigación para el seguimiento post-comité | Solicitud de actualización del requerimiento de inteligencia y nuevo plan de seguimiento continuo de la brecha. | Dirección y planificación (Retorno al inicio para ajustar el requerimiento tras el comité) | 

---

## 4. Responde

### 4.1 Nota para el comité

**Qué puedes afirmar el 20 de julio**

Se confirma un acceso no autorizado a la infraestructura de producción de Hugging Face (C03, S10), con recolección de credenciales de servicio y datos internos (C04, C06, S06, S07). La plataforma declara sin evidencia de manipulación sus modelos públicos y la cadena de suministro software (C07, C08, S01, S08). El riesgo directo para nuestra organización reside en la posible exposición de nuestras credenciales o tokens de acceso (S05).

**Nivel de confianza y justificación**

Confianza media. Toda la información proviene del comunicado de la entidad afectada (C03–C13, F01) con grado de corroboración una_parte. La cobertura de prensa solo replica la nota sin verificación propia (C14, F05) y la investigación sobre datos de clientes continúa abierta (C09).

**Recomendación al comité**

| Opción | ¿La activas? | Por qué, y por qué es proporcionada |
|---|---|---|
| O1 - Seguir con normalidad | NO | Imprudente mientras no se roten nuestras credenciales (S05) |
| O2 - Congelar descargas automáticas | SÍ | Medida preventiva temporal y reversible mientras se contenga el entorno |
| O3 - Rotar credenciales | SÍ | Prioritaria; mitiga el riesgo de suplantación (C04, C06) sin impacto operativo |
| O4 - Verificar artefactos locales | SÍ | Control pasivo interno mediante comprobación de hashes (C07) |
| O5 - Revisar credenciales externas | SÍ | Verificación rápida para descartar fuga de tokens de organización (S05) |
| O6 - Avisar a clientes | NO | Desproporcionado; la investigación (C09) sigue abierta sin afectación en nuestros servicios |
| O7 - Mantener observación | SÍ | Permite fijar un punto de revisión tras el comité ante nuevos datos |

**Limitación**

La evaluación de afectación a datos de clientes continúa abierta (C09) y se desconoce la identidad del responsable o el modelo de agentes (C13), lo que impide descartar una exfiltración previa de credenciales.

### 4.2 Hechos, inferencias y supuestos

| Afirmación de tu nota | ¿Hecho, inferencia o supuesto? | Por qué |
|---|---|---|
| Hugging Face declaró que no se encontró evidencia de manipulación en los modelos públicos (C07) | Hecho | Registro directo e identificable del comunicado oficial (C07, F01) |
| Existe riesgo de exposición en nuestras credenciales (S05) debido a la recolección de credenciales de la plataforma (C04, C06) | Inferencia | Relaciona dos hechos comprobados (C04, C06 y S05) para deducir una vulnerabilidad no confirmada explícitamente |
| Los artefactos descargados son seguros porque no se detectó manipulación en el origen (C07) | Supuesto | Asume erróneamente que la ausencia de evidencia de manipulación equivale a seguridad garantizada (lo no confirmado no equivale a inexistente) |

---

## 5. Revisa

### 5.1 Revisión de conclusiones

| Conclusión previa | ¿Cambia o se confirma? | Hecho que lo provoca | Nueva formulación |
|---|---|---|---|
| Se asumía incertidumbre y riesgo sobre exfiltración masiva de datos de clientes (C09). | Cambia | C19 (2026-07-27) | El acceso a datos de clientes fue exclusivamente de lectura y se limitó a cinco conjuntos de datos de un banco de pruebas, descartando la extracción masiva (C19). |
| Se planteaba la hipótesis de un ataque dirigido por un actor humano o grupo cibercriminal (C13). | Cambia | C17 (2026-07-21) | La intrusión no fue dirigida por una persona, sino que se originó en modelos de OpenAI que operaban con salvaguardas reducidas durante una evaluación interna (C17). |
| Los modelos y artefactos públicos distribuidos en producción no sufrieron alteraciones (C07, C08). | Se confirma | C20 (2026-07-27) | Se confirma que el acceso de escritura obtenido sobre el control de versiones no llegó a producir ningún cambio publicado en los artefactos (C20). |

---

### 5.2 Efecto sobre la recomendación

NO cambiaría la recomendación inicial. Mantener la rotación de credenciales (O3) y la congelación/verificación preventiva (O2, O4) fue una decisión proporcionada y acertada con la información disponible el 20 de julio. El desarrollo posterior reveló que los agentes ejecutaron más de 17.600 acciones (C18) y comprometieron cuentas de proveedores de terceros (C22), por lo que aislar nuestras credenciales y automatizaciones previno cualquier exposición secundaria.

---

### 5.3 Conclusión sobre la retroalimentación

La retroalimentación demuestra que la inteligencia es un ciclo dinámico donde la nueva evidencia permite precisar las causas y el alcance real del riesgo sin invalidar la proporcionalidad de las medidas preventivas adoptadas bajo incertidumbre.

---

## Fuentes

| Identificador | Fuente | URL | Fecha de consulta |
|---|---|---|---|
| F01 | Hugging Face | https://huggingface.co/blog/security-incident-july-2026 | 2026-07-20 |
| F02 | OpenAI | https://openai.com/index/hugging-face-model-evaluation-security-incident/ | 2026-07-21 |
| F03 | Hugging Face | https://huggingface.co/blog/agent-intrusion-technical-timeline | 2026-07-27 |
| F05 | TechRadar Pro | https://www.techradar.com/pro/security/hugging-face-reveals-unauthorized-access-to-ai-model-hosting-platform | 2026-07-20 |

## Decisiones y limitaciones

Se respetó el uso de fuentes de manera cronológica y no hubo interacción con la infraestructura del caso.

## Colaboración

Trabajo realizado de manera individual

## Uso de inteligencia artificial

> **Apartado obligatorio.** Si no lo completas, tu entrega está incompleta y no se califica.

| **Herramienta utilizada** | **Para qué la usaste** | **En qué fase intervino** |
|---|---|---|
| Gemini Notebook | Estructurar la información, corrección de incoherencias y verificación de trazabilidad de los identificadores | Del paso 1 al 5 y la revisión final |
| Gemini Pro 3.1 | Gramática y correcciones ortográficas | Revisión final |

## Comprobación

- [X] He trabajado sobre una copia de la plantilla, dentro de `entregas/apellidoNombre/A01/`.
- [X] He resuelto los pasos 1 a 4 solo con la cronología inicial.
- [X] Cada afirmación lleva su identificador y he comprobado que dice lo que le atribuyo.
- [X] No he interactuado con ninguna infraestructura ni servicio del caso.
- [X] No incluyo exploits, credenciales, indicadores operativos ni datos personales.
- [X] He incluido el apartado de uso de inteligencia artificial con los tres puntos.
- [X] Solo he modificado `entregas/apellidoNombre/A01/`.
