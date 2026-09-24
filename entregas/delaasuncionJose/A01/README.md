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

- Nombre: Jose Luis de la Asuncion Saura
- Carpeta personal: delaasuncionJose

---

## 1. Ordena lo que sabes

### 1.1 Clasificación de las frases

| Frase | Categoría           | Justificación                                                                                                                                                                                                                  |
| ----- | ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| A     | Dato                | Es una fila aislada que no se pone en relación con ningun otro dato, es lo mismo que aparece en `(C03)`.                                                                                                                       |
| B     | Dato                | Es un dato aislado explicando que no se ha encontrado un responsable identificado`(C13)`.                                                                                                                                      |
| C     | Informacion         | Junta dos datos como el "acceso inicial" `(C05)` y que la plataforma declara "no comprometida su cadena de suministros" `(C08)`, para de ello sacar una informacion clave, de que el problema esta "en sus sistemas internos". |
| D     | Ninguna de las tres | Es una premisa falsa basada en un dato, que no se haya encontrado evidencia `(C07)` no implica que los modelos descargados no se hayan visto afectados.                                                                        |
| E     | Inteligencia        | Es un trozo de información a la que se le da un plan de accion `(O3)` Y `(O7)` mediante una interpretacion logica de la informacion con fin de salvaguardarse.                                                                 |

### 1.2 Dato, información e inteligencia propios

| Capa         | Formulación                                                                                                                                                                                                                                                                                                                                                                               | Filas usadas                          | Qué limitación tiene                                                                                                                                                                            |
| ------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Dato         | Hugging face detecto y respondio a un acceso no autorizado a su infrastructura de produccion que luego publico el 202                                                                                                                                                                                                                                                                     | `(C03)`                               | Explica que hubo un ataque, no que ocurrio y que partes se vieron afectadas.                                                                                                                    |
| Información  | En 2024, Hugging face sufrio un ataque `(C01)`, y tras el cual aumento su seguridad `(C02)` que se vio comprometida una vez mas en 2026 `(C06, S10)`. Este antecedente fue publicado por varios medios `(F07, F08)` y se cambiaron los tokens `(S05)` en pro de un servicio   e   e   i   .                                                                                               | `(C01, C02, C06, S05, S10, F07, F08)` | Limitacion temporal, ayuda a entender el contexto previo de seguridad de la plataforma, pero no determina si en el ataque de 2026 se llegaron a comprometer los tokens activos de los usuarios. |
| Inteligencia | Debido a que no se ha encontrado evidencia de la manipulacion de los modelos abiertos `(C07)` y que ya se han tomado las medidas para rechzar y limpiar todo lo afectado `(C11)` y que nuestros modelos son de pesos abiertos `(S01)` , mi sugerencia seria `O2` temporalmente y verificar su integridad `O4` , ya que que no hayan encontrado evidencia no implica que no haya ocurrido. | `(C07, C11, S01, O2, O4)`             | Es una respuesta agresiva, tiene una limitacion donde se va a tener que comprobar los modelos y eso cuesta tiempo y dinero.                                                                     |

---

## 2. Completa el requerimiento

### 2.1 Revisión de los componentes de la petición

| Componente   | ¿Está? | Qué dice, o qué falta                                         |
| ------------ | ------ | ------------------------------------------------------------- |
| Destinatario | No     | No aclara que el destinatario final es el comite a las 13:00. |
| Decisión     | Si     | Decir si afecta o no pero no da decisiones concretas.         |
| Objeto       | Si     | Aparece de forma ambigua como "la brecha de Hugging Face".    |
| Horizonte    | No     | Falta el plazo dado, horas limite.                            |
| Alcance      | No     | DIce "dime si nos afecta" sin acotar especificamente a que.   |
| Exclusiones  | No     | No hay ninguna exlusion.                                      |
| Producto     | No     | No especifica como se debe entregar.                          |

### 2.2 Componentes completados

<!-- Contenido de los componentes que faltaban o que estaban sin concretar. -->

| Componente   | Explicacion                                                                                                                                      |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| Destinatario | El destinatario final es el comite a las 13:00.                                                                                                  |
| Decisión     | Incluir las opciones de `O1` a `O8`.                                                                                                             |
| Objeto       | Incidente de seguridad en Hugging Face el 16 de julio de 2026.                                                                                   |
| Horizonte    | 20 de Julio a las 13:00                                                                                                                          |
| Alcance      | Exclusivamente el servicio interno de modelos de pesos abiertos `(S01)` y las credenciales y tokens propios vinculados `(S05)`                   |
| Exclusiones  | Atribución del atacante `(C13)`, análisis forense de la infraestructura ajena `(S10)` y servicios de la plataforma no utilizados por la empresa. |
| Producto     | Una nota ejecutiva de inteligencia breve con nivel de confianza, opciones recomendadas.                                                          |

### 2.3 Requerimiento en una frase

>« Evaluar antes del comité de las 13:00 (horizonte) el impacto del acceso no autorizado a Hugging Face del 16 de julio (C03) sobre nuestros modelos descargados (S01) y tokens de acceso (S05), para recomendar al comité de dirección si activar medidas de congelación (O2), rotación (O3) o verificación (O4). »

### 2.4 Preguntas de inteligencia

| Prioridad | Pregunta                                                                                                                                                                                    | Te ayuda a decidir                                                                                                           |
| --------: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
|         1 | ¿Existe riesgo real o residual de que se hayan expuesto nuestros tokens de acceso a la plataforma `(S05)` debido al compromiso de credenciales internas y acceso a datos `(C04, C06, C09)`? | Decidir si rotar inmediatamente las credenciales propias `(O3)` o revisar claves fuera `(O5)`.                               |
|         2 | ¿Se ha detectado alguna alteración en los pesos y modelos públicos que ya tenemos descargados `(S01, C07)` o en su cadena de suministro `(C08)`?                                            | Decidir entre congelar descargas automatizadas `(O2)` y verificar la integridad local `(O4)` o continuar descargando `(O1)`. |

---

## 3. Planifica el ciclo

### 3.1 Recorrido por las fases

| **Fase**                  | **Entrada utilizada**                                                                                        | **Decisión o tarea**                                                                                              | **Salida**                                                                           | **Siguiente fase**            |
| ------------------------- | ------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ | ----------------------------- |
| Dirección y planificación | Requerimiento del responsable de las 09:00 y opciones del comité (O1 a O7).                                  | Definir las preguntas prioritarias, el alcance (S01, S05) y fijar el límite temporal de las 13:00.                | Plan de obtención priorizado y preguntas clave acotadas.                             | **Obtención**                 |
| Obtención                 | Fuentes iniciales disponibles (F01 a F12) y consultas sobre antecedentes (F07, F08).                         | Recopilar los comunicados de la plataforma (C03 a C13) y la cobertura pública inicial (C14).                      | Cronología de hechos brutos y registro de superficies (C01 a C14, S01 a S10).        | **Procesamiento**             |
| Procesamiento             | Hechos brutos recopilados y tabla de superficies del sistema.                                                | Cruzar los hechos técnicos con los activos que usa nuestra empresa (S01, S05) y descartar ruidos.                 | Información contextualizada sobre vectores comprometidos y componentes no afectados. | **Análisis y producción**     |
| Análisis y producción     | Información procesada y evaluación de corroboración de fuentes (F01, una parte).                             | Evaluar si la falta de evidencia en C07 garantiza seguridad, contrastar hipótesis y elegir opciones (O2, O3, O4). | Borrador de nota ejecutiva con estimación de riesgo y opciones recomendadas.         | **Difusión**                  |
| Difusión                  | Nota de inteligencia terminada con nivel de confianza y limitaciones.                                        | Presentar la nota de evaluación de impacto y recomendaciones al comité de las 13:00.                              | Decisión ejecutiva tomada por el comité sobre qué medidas operativas activar.        | **Retroalimentación**         |
| Retroalimentación         | Dudas del comité sobre la persistencia del riesgo y nueva información que se vaya publicando tras las 13:00. | Revisar si las hipótesis se mantienen firmes ante nuevos comunicados técnicos y ajustar el seguimiento (O7).      | Nuevos requerimientos de seguimiento o cancelación de medidas de contención.         | **Dirección y planificación** |

---

## 4. Responde

### 4.1 Nota para el comité

**Qué puedes afirmar el 20 de julio**

**Afectación a fecha 20 de julio:** No consta alteración en los modelos de pesos abiertos descargados (S01), pues no hay evidencia de manipulación en artefactos públicos (C07) y la cadena de suministro se verificó íntegra (C08). Sin embargo, hubo compromiso de credenciales internas (C04, C06) y la evaluación sobre datos de clientes sigue abierta (C09), por lo que persiste un riesgo residual sobre nuestros tokens (S05).

**Nivel de confianza y justificación**

**Nivel de confianza:** **Media-Baja.** Se sustenta exclusivamente en una declaración unilateral de la entidad afectada (F01, C03), sin auditoría externa independiente y con prensa que solo reproduce el comunicado (C14, F05).

**Recomendación al comité**

| Opción | ¿La activas? | Por qué, y por qué es proporcionada |
| --- | --- | --- |
| **O1** | **No** | Imprudente: la investigación sobre afectación a datos de clientes sigue abierta (C09) y el análisis no ha concluido.

 |
| **O2** | **Sí** | Proporcionada: frena preventivamente la entrada de modelos externos (S01) sin detener el servicio privado en producción.

 |
| **O3** | **Sí** | Crítica y proporcionada: no corta el servicio y mitiga el vector de credenciales robadas (C04, C06) que amenaza a nuestros tokens (S05).

 |
| **O4** | **Sí** | Proporcionada: es un chequeo interno de *hashes* en local (S01) que confirma sin impacto operativo la ausencia de alteración (C07).

 |
| **O5** | **No** | Innecesaria: la intrusión fue en la infraestructura ajena vía datasets (C03, C05), no por fugas públicas de nuestra empresa.

 |
| **O6** | **No** | Desproporcionada: crearía alarma sin existir evidencia de que nuestros modelos o datos de clientes estén comprometidos (C07, C08).

 |
| **O7** | **Sí** | Indispensable: ante un comunicado unilateral de una sola parte (F01, C03), mantener la vigilancia activa no tiene coste y asegura seguimiento.

 |

**Limitación**

**Limitación y qué no cubre:** Se limita a lo reportado hasta las 09:00 del 20 de julio (C03-C14); **no cubre** la autoría del incidente (C13) ni garantiza la seguridad de las descargas futuras mientras la investigación forense de clientes siga inconclusa (C09).

### 4.2 Hechos, inferencias y supuestos

| Afirmación de tu nota                                                                                             | ¿Hecho, inferencia o supuesto? | Por qué                                                                                                                                              |
| ----------------------------------------------------------------------------------------------------------------- | ------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| «El ataque alcanzó credenciales internas (C04) y la evaluación sobre clientes sigue abierta (C09).»               | **Hecho**                      | Reproduce de forma objetiva y literal lo declarado por la fuente oficial (F01, C04, C09).                                                            |
| «Existe riesgo residual sobre nuestras credenciales (S05) debido al compromiso de claves del sistema (C04, C06).» | **Inferencia**                 | Deducción lógica que vincula el robo admitido de claves internas con una posible exposición de tokens de usuario mientras C09 esté abierta.          |
| «Los modelos públicos descargados de la plataforma (S01) no han sido manipulados (C07).»                          | **Supuesto**                   | Se asume provisionalmente como premisa válida confiando en el comunicado (F01), aunque la ausencia de evidencia (C07) no garantiza certeza absoluta. |

---

## 5. Revisa

### 5.1 Revisión de conclusiones

|**Conclusión previa**|**¿Cambia o se confirma?**|**Hecho que lo provoca**|**Nueva formulación**|
|---|---|---|---|
|**Origen desconocido:** Se desconoce al actor responsable y el modelo concreto de lenguaje que operaba el enjambre (C13).|**Cambia**|C17|La intrusión provino de modelos de OpenAI con salvaguardas reducidas en una evaluación de seguridad interna, actuando de forma autónoma sin dirección humana (C17).|
|**Riesgo en datos de clientes:** Existía incertidumbre sobre si datos de clientes o socios habían sido extraídos o comprometidos al seguir la investigación abierta (C09).|**Cambia**|C19|La exposición de clientes fue marginal (solo cinco conjuntos de datos de pruebas), la base de datos se accedió en solo lectura y no hubo extracción masiva (C19).|
|**Integridad de los artefactos:** Los modelos públicos descargados no sufrieron alteraciones ni manipulación de software (C07, C08).|**Se confirma**|C20|Se ratifica la integridad de los modelos: aunque se obtuvo acceso de escritura al control de versiones, no se llegó a publicar ningún cambio en la plataforma (C20).|

### 5.2 Efecto sobre la recomendación

**No cambiaría la recomendación planteada el 20 de julio.**

Mantener las descargas activas bajo observación (O1/O7) y no alertar a los clientes (descartar O6) fue una postura proporcionada y correcta, ya que posteriormente se ratificó que ningún artefacto público fue alterado (C07, C20) y no existió fuga masiva de datos (C19). Medidas drásticas como congelar la operativa (O2) o emitir alertas externas habrían generado una disrupción innecesaria e infundada para el servicio de la empresa.

### 5.3 Conclusión sobre la retroalimentación

La retroalimentación demuestra que la inteligencia es un proceso dinámico en el que contrastar hechos nuevos permite reducir la incertidumbre y validar o corregir juicios preliminares sin desestabilizar las decisiones operativas iniciales.

---

## Uso de inteligencia artificial

> **Apartado obligatorio.** Si no lo completas, tu entrega está incompleta y no se califica.

| **Herramienta utilizada** | Gemini                                      |
| ------------------------- | ------------------------------------------- |
| **Para qué la usaste**    | Comprobar respuestas y ayudarme a entender. |
| **En qué fase intervino** | Principalmente paso 3-5.                    |

## Comprobación

- [x] He trabajado sobre una copia de la plantilla, dentro de `entregas/apellidoNombre/A01/`.
- [x] He resuelto los pasos 1 a 4 solo con la cronología inicial.
- [x] Cada afirmación lleva su identificador y he comprobado que dice lo que le atribuyo.
- [x] No he interactuado con ninguna infraestructura ni servicio del caso.
- [x] No incluyo exploits, credenciales, indicadores operativos ni datos personales.
- [x] He incluido el apartado de uso de inteligencia artificial con los tres puntos.
- [x] Solo he modificado `entregas/apellidoNombre/A01/`.
