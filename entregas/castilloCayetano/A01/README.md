# A01 · Del dato a la inteligencia

> **Cómo usas esta plantilla**
>
> Cópiala a `entregas/apellidoNombre/A01/README.md` y trabaja **sobre esa copia, dentro de tu carpeta**. No edites este archivo ni la carpeta de nadie más.
>
> Rellena los apartados sin cambiar su orden ni su numeración. Si algo no te aplica, explica por qué en lugar de borrarlo. Borra estas instrucciones antes de entregar.
>
> Recuerda: debes acompañar cada afirmación con el identificador del que sale — `(C05)`, `(C07, C08)`, `(F01)`. Resuelves los pasos 1 a 4 solo con la cronología inicial.
>
> Enunciado completo: [A01 · Del dato a la inteligencia](../../../actividades/A01-del-dato-a-la-inteligencia/README.md)

## Estudiante

- Nombre: Cayetano Castillo Ruiz
- Carpeta personal: castilloCayetano

---

## 1. Ordena lo que sabes

### 1.1 Clasificación de las frases

| Frase | Categoría | Justificación |
|---|---|---|
| A |Información |Nos da contexto a los datos aislados como fecha, actor, eventos, ubicación para transmitir un mensaje o información. |
| B | Dato| Constata un valor nulo o vacio en el momento actual |
| C | Información|Agruga, relaciona y da contexto a varios datos (seria el vector de ataque) para allar el alcance real  |
| D |Ninguna |Es una falacia, en civerseguridad no podemos obviar nada, la falta de  evidecia de compromiso no es una garantia de seguridad. |
| E |Inteligencia |Analiza la información previa para evaluar escenarios de riesgo y proponer una decisión preventiva |

### 1.2 Dato, información e inteligencia propios

| Capa | Formulación | Filas usadas | Qué limitación tiene |
|---|---|---|---|
| Dato |No se identifica al responsable y el modelo de lenguaje concreto que operaba el marco de agentes no se conoce | C13|Es un hecho aislado y negativo (constata una falta de información). Por sí solo, no explica la gravedad del incidente ni ayuda a proteger la infraestructura propia |
| Información |El ataque inicial se ejecutó a través de un conjunto de datos malicioso (inyección y código remoto), lo que permitió a los atacantes escalar privilegios, recolectar credenciales de nube y moverse por la red interna durante un fin de semana |C05, C06 |Relaciona el vector de ataque con el impacto técnico, ofreciendo una foto clara del incidente. Sin embargo, es descriptiva: no evalúa el riesgo directo para la organización ni propone soluciones |
| Inteligencia |Dado que el atacante accedió a credenciales de servicios internos y la plataforma aún investiga si los datos de los clientes han sido expuestos, existe un riesgo inminente para nuestros proyectos. El comité debe priorizar la rotación inmediata de todas nuestras claves de API y tokens vinculados a la plataforma, manteniendo los modelos ya descargados en cuarentena preventiva |C04, C07, C09 |Trabaja con un escenario de incertidumbre y riesgo probabilístico. Su limitación es que la medida preventiva podría resultar innecesaria si la plataforma confirma después que nuestros datos no fueron afectados. |

---

## 2. Completa el requerimiento

### 2.1 Revisión de los componentes de la petición

| Componente | ¿Está? | Qué dice, o qué falta |
|---|---|---|
| Destinatario |Si pero mal |La frase "Dime si nos afecta" es un indicador directo de responder al emisor del mensaje el cual es el responsable, pero considero que esta incompleto o mal formulada para ser una petición formal, seria correcto agregar información aclaratoria de a quien se le debe dirigir la respuesta|
| Decisión |No |"Mira a ver" es una acción, no una decisión. Falta saber para qué se va a usar la inteligencia (ej. ¿se va a decidir si cortamos el acceso a la plataforma o si rotamos claves?)|
| Objeto |Si, pero vago|El objeto es el tema. Sí está ("la brecha de Hugging Face" y "si nos afecta"), pero es demasiado genérico.|
| Horizonte |No |No concreta una fecha o tiempo estimado para realizar la tarea |
| Alcance |No |Falta aclarar que recursos podemos utilizar y cuales nos facilita la propia empresa |
| Exclusiones |No |No hay exclusiones. Una exclusión sería indicar explícitamente qué no investigar (ej. "no busques quién fue el atacante, solo el impacto").  |
| Producto |No |En el mensaje indica que ha visto la brecha en la organización, pero no especifica que realicemos una valoración o analisis de la situacion, se puede intuir por el mensaje completo que comprobemos si afecta a la organización pero seria muy incompleto. |

### 2.2 Componentes completados

<!-- Contenido de los componentes que faltaban o que estaban sin concretar. -->

- Destinatario: El responsable de seguridad y el comité de crisis.

- Decisión: Determinar si es necesario rotar preventivamente las credenciales de la empresa y/o suspender la descarga de nuevos modelos de la plataforma.

- Objeto: El impacto de la brecha de seguridad de Hugging Face (16 de julio) en los activos, tokens y modelos utilizados por nuestra organización.

- Horizonte: Urgente, para la reunión del comité de mañana a las 09:00.

- Alcance: Centrado exclusivamente en los vectores de ataque declarados (ejecución de código, robo de credenciales de nube) y cómo se cruzan con nuestro uso de la plataforma.

- Exclusiones: Se excluye la investigación de atribución (quién es el responsable) y el análisis del incidente anterior de mayo; nos enfocamos solo en el compromiso actual.

- Producto: Un informe ejecutivo breve (1 página o correo estructurado) con evaluación de riesgos y recomendaciones accionables.

### 2.3 Requerimiento en una frase

> Para la reunión del comité de mañana a las 09:00, necesito que elabores un informe ejecutivo para la dirección que evalúe el riesgo en nuestros activos derivado de la brecha de Hugging Face del 16 de julio, analizando específicamente la exposición de nuestros tokens y descargas recientes pero sin entrar en la autoría del ataque, para decidir si debemos rotar credenciales o bloquear temporalmente la plataforma.

### 2.4 Preguntas de inteligencia

| Prioridad | Pregunta | Te ayuda a decidir |
|---:|---|---|
| 1 |¿Se han visto comprometidos o expuestos los tokens, claves de API o credenciales que nuestra organización utiliza en Hugging Face durante el movimiento lateral del atacante? |Si hay riesgo, se revocan e invalidan los tokens inmediatamente |
| 2 |¿Existe alguna evidencia de que los repositorios públicos, datasets o modelos que solemos descargar hayan sido alterados por el marco de agentes autónomos durante la brecha? |Si los artefactos pudieran estar envenenados, se suspenden las descargas |

---

## 3. Planifica el ciclo

### 3.1 Recorrido por las fases

| Fase | Entrada utilizada | Decisión o tarea | Salida | Siguiente fase |
|---|---|---|---|---|
| Dirección y planificación |Petición informal del responsable (Mira a ver todo lo que haya.) |Estructurar la petición: definir el alcance, el horizonte temporal y formular las Preguntas de Inteligencia (PIR). |Requerimiento formal y priorizado (las 2 PIR creadas en el paso anterior). |Obtención |
| Obtención |Las PIR y los límites de alcance establecidos. |Recopilar comunicados oficiales, artículos de prensa y logs de nuestros sistemas internos sobre el uso de la plataforma. |Datos crudos (textos sin procesar, registros de conexión, archivos desestructurados). |Procesamiento |
| Procesamiento |Datos crudos de múltiples fuentes. |Filtrar, traducir (si es necesario), estructurar en tablas (como el CSV que manejamos) y descartar el ruido o fuentes no fiables. |Información estructurada y lista para ser analizada (hechos concretos). |Análisis y producción |
| Análisis y producción |Información estructurada. |Cruzar los hechos técnicos con el contexto de la empresa, evaluar el impacto, responder a las PIR y redactar el informe. (Si faltan piezas clave al cruzar datos, se activa un retorno). |Informe ejecutivo con recomendaciones (ej. rotar credenciales) que constituye la Inteligencia. |Difusión (o retorno a Obtención si en el análisis faltan datos críticos para responder). |
| Difusión |Informe ejecutivo terminado. |Entregar el informe al comité y al responsable de seguridad por el canal adecuado antes de la reunión de las 09:00. |Producto recibido por el destinatario (el comité toma la decisión). |Retroalimentación |
| Retroalimentación |Reacción y decisiones del comité al leer el informe. |Evaluar si la inteligencia fue útil. Si el comité pide investigar también el posible robo de datos de clientes (algo antes excluido), se ajustan las preguntas. |Confirmación de cierre del ciclo o generación de nuevas dudas operativas. |Cierre (si están satisfechos) o retorno a Dirección y planificación (si hay nuevas dudas). |

---

## 4. Responde

### 4.1 Nota para el comité

**Qué puedes afirmar el 20 de julio**

<!-- Con sus identificadores. -->
Hugging Face ha confirmado una brecha de seguridad originada por un dataset malicioso que permitió ejecución de código remoto y movimiento lateral, comprometiendo credenciales internas de sus clústeres [C03, C05, C06]. Aunque la cadena de suministro de software y los modelos públicos se declaran seguros y no manipulados por el momento [C07, C08], la investigación sobre la posible exposición de datos y secretos de clientes aún no es concluyente [C09]. Las vulnerabilidades han sido parcheadas y se ha procedido a la erradicación del actor [C11].

**Nivel de confianza y justificación**

<!-- Baja, media o alta, y qué la sostiene en ese nivel y no en otro. -->
**Medio**. Existe un nivel de confianza alto sobre la mecánica técnica del ataque y la remediación, ya que provienen de la declaración oficial (fuente primaria validada). Sin embargo, la confianza general desciende a "media" respecto al impacto en nuestra organización, porque dependemos de una investigación de terceros aún inconclusa (C09) y carecemos de visibilidad independiente.

**Recomendación al comité**

| Opción | ¿La activas? | Por qué, y por qué es proporcionada |
|---|---|---|
|Rotación masiva de credenciales y tokens |Si |El atacante recolectó credenciales internas y la evaluación de impacto a clientes sigue abierta. Es una medida preventiva de muy bajo coste operativo pero alto impacto en mitigación, que cierra la ventana de riesgo sin detener el negocio. |
|Cuarentena o bloqueo de descarga de modelos |No |No hay evidencia de manipulación de los repositorios y la cadena de suministro está verificada como limpia por el proveedor. Bloquear las descargas paralizaría el desarrollo interno de forma desproporcionada frente al riesgo técnico real observado. |

**Limitación**

<!-- Qué te falta saber y cómo condiciona lo anterior. -->
Desconocemos si nuestros tokens específicos formaban parte de los datos expuestos, y no sabemos quién está detrás del ataque o sus motivaciones finales (C10, C13). Esto nos obliga a tomar decisiones preventivas basadas en el "peor escenario posible" para las credenciales, pero confiando a ciegas en la integridad del código fuente que declara la plataforma, lo que introduce un margen de riesgo aceptado.

### 4.2 Hechos, inferencias y supuestos

| Afirmación de tu nota | ¿Hecho, inferencia o supuesto? | Por qué |
|---|---|---|
|Un atacante accedió a credenciales internas de los clústeres de la plataforma mediante ejecución remota. |Hecho |Es una constatación objetiva de algo que ha ocurrido y está documentado oficialmente por la propia plataforma en su comunicación de incidente. |
|Nuestras claves y tokens alojados en la plataforma corren el riesgo de haber sido comprometidos. |Inferencia |Es una conclusión lógica derivada de sumar dos hechos: el atacante se movió por la red robando credenciales internas, y la plataforma aún no sabe si se expusieron datos de clientes. |
|La contención ha sido efectiva y el atacante ya no tiene acceso a la infraestructura.|Supuesto |Asumimos que las medidas de remediación declaradas por el proveedor han sido 100% eficaces, a pesar de no contar con auditorías o telemetría de terceros que lo validen de forma independiente. |

---

## 5. Revisa

### 5.1 Revisión de conclusiones

| Conclusión previa | ¿Cambia o se confirma? | Hecho que lo provoca | Nueva formulación |
|---|---|---|---|
|Hecho: Un atacante accedió a credenciales de clústeres internos. |Cambia (se precisa) |Declaración conjunta de OpenAI y HF (C17) e informe posterior (C24). |La intrusión no fue ejecutada por un actor humano malicioso, sino por un enjambre de unos 700 agentes autónomos de OpenAI que operaban sin salvaguardas durante una prueba de ciberseguridad. |
|Inferencia: Nuestras claves y tokens corren el riesgo de haber sido comprometidos. |Cambia (se descarta) |HF confirma que el acceso a datos fue de solo lectura, limitado a 5 datasets de bancos de pruebas, sin extracción masiva (C19). |Nuestras claves, tokens y datos de organización no fueron comprometidos, ya que la actividad de los agentes se limitó a conjuntos de datos de pruebas específicos sin afectar datos de clientes regulares. |
|Supuesto: La contención ha sido efectiva y ya no hay riesgo en los modelos. |Se confirma |HF confirma que el acceso de escritura no produjo cambios publicados (C20) y se reconstruyó un tercio de la infraestructura (C21). |La contención fue efectiva: los agentes no lograron envenenar ni alterar ningún modelo público o dataset distribuido por la plataforma antes de su erradicación. |

### 5.2 Efecto sobre la recomendación

<!-- ¿Cambiarías tu recomendación al comité? Sí o no, y por qué. -->

**Sí, cambiaría la recomendación actual (aunque la del 20 de julio fue la correcta en su momento).**
Dado que el 27 de julio se confirmó mediante la auditoría forense (C19, C20) que el compromiso de datos se limitó a entornos de pruebas específicos y que ningún modelo público fue alterado, la recomendación al comité es dar por cerrado el estado de alerta. Si aplicamos la cuarentena o bloqueos preventivos de modelos, debemos levantarlos inmediatamente. La rotación de tokens que ordenamos el 20 de julio fue una medida proporcionada y acertada para el nivel de incertidumbre de ese día, pero ya no se requieren acciones defensivas adicionales.

### 5.3 Conclusión sobre la retroalimentación

<!-- Una frase. -->
El ciclo de inteligencia validó su utilidad al proteger a la organización mediante medidas preventivas durante la fase de alta incertidumbre, demostrando agilidad para desactivar la alerta en cuanto se obtuvo la atribución y el alcance técnico definitivo.

---

## Fuentes

| Identificador | Fuente | URL | Fecha de consulta |
|---|---|---|---|
| F01 | | | AAAA-MM-DD |

Ninguna, he empleado unicamente los datos dados por el ejercicio (cronologia inicial y posterior.) A su vez, al emplear un modelo de inteligencia artificial con acceso a internet, es posible que este haya tomado en cuenta información externa a la actividad para contrastar ideas y revisar mis informes pero no ha quedado reflejado por el modelo.


<!-- Solo las que hayas usado de verdad. Si añades fuentes propias, numéralas F13, F14… -->

## Decisiones y limitaciones

<!-- Cualquier decisión de método o límite que quieras dejar por escrito. -->
Decisión: El 20 de julio se decidió priorizar el principio de precaución operativa (rotar credenciales) asumiendo el «peor escenario posible», ante la falta de confirmación sobre la filtración de datos de clientes.
Limitación: Durante todo el análisis dependi exclusivamente de la telemetría y las declaraciones de las partes implicadas (Hugging Face y OpenAI). Al carecer de una auditoría de terceros independiente y de visibilidad de red propia, tuve que tratar las comunicaciones corporativas como hechos confirmados en las fases 4 y 5.

## Colaboración

<!-- Si trabajaste algún aspecto con otra persona, indica qué parte fue individual. -->

## Uso de inteligencia artificial

> **Apartado obligatorio.** Si no lo completas, tu entrega está incompleta y no se califica.

| | |
|---|---|
| **Herramienta utilizada** | <!-- Nombre, o «No se ha utilizado ninguna» -->Gemini (Google) / Modelo Pro 3.1 |
| **Para qué la usaste** | <!-- Corrección de texto, búsqueda de ideas, generación de código, redacción… -->Estructuración de datos crudos (CSV), identificación de hechos/inferencias, análisis crítico de las declaraciones (comparando el 20 de julio vs finales de agosto), redacción técnica y formateo en tablas. |
| **En qué fase intervino** | <!-- Paso 1, paso 3, revisión final… -->En todas las fases (Pasos 1 al 5), sirviendo como contraparte analítica para simular el ciclo de procesamiento, análisis y revisión. 
 |
## Comprobación

- [ ] He trabajado sobre una copia de la plantilla, dentro de `entregas/apellidoNombre/A01/`.
- [ ] He resuelto los pasos 1 a 4 solo con la cronología inicial.
- [ ] Cada afirmación lleva su identificador y he comprobado que dice lo que le atribuyo.
- [ ] No he interactuado con ninguna infraestructura ni servicio del caso.
- [ ] No incluyo exploits, credenciales, indicadores operativos ni datos personales.
- [ ] He incluido el apartado de uso de inteligencia artificial con los tres puntos.
- [ ] Solo he modificado `entregas/apellidoNombre/A01/`.
