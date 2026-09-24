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

- Nombre: Saúl de Cos Sánchez
- Carpeta personal: deCosSaul

---

## 1. Ordena lo que sabes

### 1.1 Clasificación de las frases

| Frase | Categoría        | Justificación                                                                                                   |
| ----- | ---------------- | --------------------------------------------------------------------------------------------------------------- |
| A     | Dato             | Es una información aisalda, sin contexto                                                                        |
| B     | Dato             | Dato sin contexto                                                                                               |
| C     | Información      | Varios datos contextualizados y relacionados entre sí, todavía no se ha valorado, por lo que no es inteligencia |
| D     | Ninguna de las 3 | Llega a una conclusión sin los datos necesarios para respaldarla                                                |
| E     | Inteligencia     | Informa de las acciones que se recomienda realizar                                                              |

### 1.2 Dato, información e inteligencia propios

| Capa         | Formulación                                                                                                                                             | Filas usadas  | Qué limitación tiene                                                                                                   |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------- | ---------------------------------------------------------------------------------------------------------------------- |
| Dato         | El 16 de julio, la plataforma comunica que la cadena de suministro de software no se ha visto comprometida                                              | C08           | No se tiene ninguna otra información ni contexto                                                                       |
| Información  | El acceso inicial se produjo mediante datos maliciosos y escaló hasta nivel de nodo, no se ha encontrado evidencia de manipulacion de espacios públicos | C05, C06, C07 | Esta información proviene únicamente de Hugging Face, que no descarta la falta de detección de algún acceso no deseado |
| Inteligencia | Por ahora, no hay evidencia de acceso a datos delicados, por lo que no es prioritario notificar a los clientes                                          | C07, C08, C09 | La investigación sigue abierta, puede que esta información cambie                                                      |

---

## 2. Completa el requerimiento

### 2.1 Revisión de los componentes de la petición

| Componente   | ¿Está? | Qué dice, o qué falta                                                                                |
| ------------ | ------ | ---------------------------------------------------------------------------------------------------- |
| Destinatario | Sí     | Persona que recibe el correo                                                                         |
| Decisión     | No     | El correo no comenta las acciones necesarias                                                         |
| Objeto       | Sí     | Dice que mires todo lo relacionado con la brecha de Hugging Face, faltaría especificarlo un poco más |
| Horizonte    | No     | Falta la hora/fecha límite para realizar la tarea                                                    |
| Alcance      | No     | No indica que analizar y que no                                                                      |
| Producto     | No     | No especifica el resultado esperado                                                                  |

### 2.2 Componentes completados

| Componente | Qué dice, o qué falta                                                            |
| ---------- | -------------------------------------------------------------------------------- |
| Decisión   | Analiza si la incidencia en Hugging Face nos afecta y debemos tomar medidas o no |
| Horizonte  | Realiza un informe antes de las 13:00                                            |
| Alcance    | Analiza los documentos proporcionados por Hugging Face                           |
| Producto   | Realizar un informe para el comité                                               |

<!-- Contenido de los componentes que faltaban o que estaban sin concretar. -->

### 2.3 Requerimiento en una frase

> Analiza los documentos publicados por Hugging Face sobre la incidencia ocurrida, y determina si nos afecta, ten un informe realizado para el comité de las 13:00

### 2.4 Preguntas de inteligencia

| Prioridad | Pregunta                                                                                                   | Te ayuda a decidir                                         |
| --------: | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
|         1 | ¿Es posible que las contraseñas de la empresa en Hugging Face se hayan visto afectadas por esta inciencia? | Si es necesario hacer cambios de credenciales              |
|         2 | ¿Es posible que los datos de nuestros clientes se hayan visto afectados?                                   | Si es necesario informar a los clientes de esta incidencia |

---

## 3. Planifica el ciclo

### 3.1 Recorrido por las fases

| Fase                      | Entrada utilizada                                                     | Decisión o tarea                                                                                  | Salida                              | Siguiente fase            |
| ------------------------- | --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ----------------------------------- | ------------------------- |
| Dirección y planificación | Petición inicial                                                      | Decidir si la empresa ha sido afectada por el problema en Hugging Face o no                       | Requisitos y plan a seguir          | Obtención                 |
| Obtención                 | Documentos iniciales                                                  | Analizar los datos iniciales para obtener información                                             | Datos recopilados                   | Procesamiento             |
| Procesamiento             | Datos recopilados de la fase de obtención                             | Analizar la información obtenida en el paso anterior para obtener inteligencia                    | Información relacionada             | Análisls y producción     |
| Análisis y producción     | Información obtenida a base de esos datos en la fase de procesamiento | Analizar si la incidencia afecta a la empresa o no, y si es el caso, que medidas habría que tomar | Recomendaciones de acciones a tomar | Difusión                  |
| Difusión                  | Inteligencia obtenida tras el análisis de la información              | Informe generado explicando lo que ha sucedido y en que nos afecta                                | Documento de análisis               | Retroalimentación         |
| Retroalimentación         | Nuevos datos recopilados tras la toma de decisiones/medidas           | Ver las consecuencias de las acciones realizadas y si es necesario hacer o modificar algo más     | Nuevos requisitos                   | Dirección y planificación |

---

## 4. Responde

### 4.1 Nota para el comité

**Qué puedes afirmar el 20 de julio**

Pese a que no hay aún evidencia de que los datos se hayan visto afectados, tampoco está descartado, por lo que, sería conveniente seguirlos de cerca para poder tomar medidas lo antes posible en caso de que se vean afectados, además recomendaría cambiar las contraseñas que se hayan podido ver afectadas(C06, C08, C09)

<!-- Con sus identificadores. -->

**Nivel de confianza y justificación**

Medio, pese a que es bastante posible que los modelos no se hayan visto afectados, la unica fuente es el propio Hugging Face, ninguna externa que lo confirme

<!-- Baja, media o alta, y qué la sostiene en ese nivel y no en otro. -->

**Recomendación al comité**

| Opción                                                    | ¿La activas? | Por qué, y por qué es proporcionada                                                                      |
| --------------------------------------------------------- | ------------ | -------------------------------------------------------------------------------------------------------- |
| Pausar las descargas de modelos de Hugging Face           | No           | Todavía no la activo por falta de evidencia de que los modelos se hayan visto afectados                  |
| Cambiar las contraseñas que se hayan podido ver afectadas | Si           | En caso de que las contraseñas se hayan visto afectadas, aún sin evidencia, conviene cambiarlas          |
| Avisar a los clientes                                     | No           | Todavía no hay evidencia de que sus datos se hayan visto afectados, por lo que por ahora no es necesario |
| Seguir de cerca la evolución del caso                     | Si           | Por si surge alguna novedad es recomendable seguir monitorizandolo                                       |

**Limitación**

Falta todavía la confirmación oficial de Hugging Face de que los datos realmente no se hayan visto afectados, por ahora es unicamente una suposición

<!-- Qué te falta saber y cómo condiciona lo anterior. -->

### 4.2 Hechos, inferencias y supuestos

| Afirmación de tu nota                                                  | ¿Hecho, inferencia o supuesto? | Por qué                                                                                                     |
| ---------------------------------------------------------------------- | ------------------------------ | ----------------------------------------------------------------------------------------------------------- |
| Por ahora no hay evidencia de que los modelos se hayan visto afectados | Hecho                          | Dato publicado por el propio proveedor                                                                      |
| Sería buena idea cambiar las contraseñas                               | Inferencia                     | Pese a la falta de evidencia, todavía no es seguro, por lo que convendría hacerlo por si acaso              |
| Los datos de los clientes puede que se hayan visto afectados           | Supuesto                       | Pese a que Hugging Face diga que no hay evidencia, tampoco lo ha descartado, por lo que podría haber pasado |

---

## 5. Revisa

### 5.1 Revisión de conclusiones

| Conclusión previa                                                                       | ¿Cambia o se confirma? | Hecho que lo provoca | Nueva formulación                                                          |
| --------------------------------------------------------------------------------------- | ---------------------- | -------------------- | -------------------------------------------------------------------------- |
| No es necesario pausar los modelos ni descargas                                         | Se confirma            | C20                  |                                                                            |
| No se ha confirmado que los datos de los clientes se hayan visto afectados              | Cambia                 | C19                  | Los datos de los clientes se han podido ver comprometidos                  |
| La confianza en la veracidad de los datos es media porque solo proviene de Hugging Face | Cambia                 | C16 C17              | La nueva confianza es alta, ya que es conjunta de Open AI con Hugging Face |

### 5.2 Efecto sobre la recomendación

No cambiaría las recomendaciones iniciales, la cornología posterior únicamente ha confirmado las decisiones tomadas anteriormente

<!-- ¿Cambiarías tu recomendación al comité? Sí o no, y por qué. -->

### 5.3 Conclusión sobre la retroalimentación

Pese a tener una valoración inicial con suficiente información como para que la mayoría de las recomendaciones se mantengan, los nuevos datos publicados confirman que conviene revisarlo periodicamente a medida que sale nueva información por si se requiere modificar algo

<!-- Una frase. -->

---

## Fuentes

| Identificador | Fuente | URL | Fecha de consulta |
| ------------- | ------ | --- | ----------------- |
| F01           |        |     | AAAA-MM-DD        |

Archivo de cronología inicial y posterior (para apartado 5 únicamente)

<!-- Solo las que hayas usado de verdad. Si añades fuentes propias, numéralas F13, F14… -->

## Decisiones y limitaciones

La principal limitación es que los datos provienen únicamente de Hugging Face, por lo que no están contrastados ni verificados por entidades externas a ellos, además para los apartados del 1 al 4, únicamente se tenía acceso a la cronología inicial, que también limita los datos disponibles

<!-- Cualquier decisión de método o límite que quieras dejar por escrito. -->

## Colaboración

<!-- Si trabajaste algún aspecto con otra persona, indica qué parte fue individual. -->

## Uso de inteligencia artificial

> **Apartado obligatorio.** Si no lo completas, tu entrega está incompleta y no se califica.

|                           |                                                                                                                                                                                                              |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Herramienta utilizada** | Codex (GPT-5.6)<!-- Nombre, o «No se ha utilizado ninguna» -->                                                                                                                                               |
| **Para qué la usaste**    | Resolver dudas sobre el enunciado, revisar la redacción y comprender la clasificación de datos, información e inteligencia.<!-- Corrección de texto, búsqueda de ideas, generación de código, redacción… --> |
| **En qué fase intervino** | Pasos 1 a 5 y revisión final<!-- Paso 1, paso 3, revisión final… -->                                                                                                                                         |

## Comprobación

- [ ] He trabajado sobre una copia de la plantilla, dentro de `entregas/apellidoNombre/A01/`.
- [ ] He resuelto los pasos 1 a 4 solo con la cronología inicial.
- [ ] Cada afirmación lleva su identificador y he comprobado que dice lo que le atribuyo.
- [ ] No he interactuado con ninguna infraestructura ni servicio del caso.
- [ ] No incluyo exploits, credenciales, indicadores operativos ni datos personales.
- [ ] He incluido el apartado de uso de inteligencia artificial con los tres puntos.
- [ ] Solo he modificado `entregas/apellidoNombre/A01/`.
