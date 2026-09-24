# A01 · Del dato a la inteligencia

Actividad individual evaluable del Tema 1. Se resuelve en cinco pasos encadenados sobre un caso real: cada paso utiliza el resultado del anterior.

## La situación

Trabajas en el equipo de ciberinteligencia de una empresa que incorpora en uno de sus servicios, modelos de pesos abiertos descargados de **Hugging Face**.

El **16 de julio de 2026** Hugging Face publica una comunicación de incidente de seguridad. El **lunes 20 de julio a las 09:00**, tu responsable te escribe:

> «He visto lo de la brecha de Hugging Face. Mira a ver todo lo que haya y dime si nos afecta.»

Tienes comité **a las 13:00** y debes llegar con una recomendación. Estas son las opciones sobre la mesa, que no son excluyentes entre sí:

| | Opción |
|---|---|
| **O1** | Seguir descargando con normalidad |
| **O2** | Congelar las descargas automatizadas |
| **O3** | Rotar las credenciales de la plataforma |
| **O4** | Verificar la integridad de los artefactos ya descargados |
| **O5** | Revisar qué credenciales propias están publicadas fuera de la empresa |
| **O6** | Avisar a los clientes del servicio |
| **O7** | Mantener la observación y fijar un punto de revisión |

**Puedes añadir opciones.** Si crees que falta una medida razonable, propónla con su código (`O8`, `O9`…) y justifícala igual que las demás.

## El material

| Archivo                                                        | Contenido                                                                                                              |
| -------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| [cronologia-inicial.csv](datos/cronologia-inicial.csv)         | `C01`–`C14`. Hechos públicos **hasta el 20 de julio**, cuando te llega la petición                                     |
| [cronologia-posterior.csv](datos/cronologia-posterior.csv)     | `C15`–`C25`. Hechos públicos **publicados después**                                                                    |
| [superficies-plataforma.csv](datos/superficies-plataforma.csv) | `S01`–`S10`. Qué partes tiene la plataforma, quién gestiona cada una y qué filas de la cronología inicial la mencionan |
| [fuentes.csv](datos/fuentes.csv)                               | `F01`–`F12`. Las fuentes de donde sale cada hecho                                                                      |

**Campos de las cronologías**

| Campo           | Qué contiene                                                                                                                                                              |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `id`            | Identificador del hecho, `C01`–`C25`                                                                                                                                      |
| `fecha`         | Fecha de publicación o de ocurrencia declarada                                                                                                                            |
| `actor`         | Quién lo afirma o de quién trata                                                                                                                                          |
| `tipo`          | `declaracion_oficial`, `cobertura`, `antecedente` o `cronologia`                                                                                                          |
| `contenido`     | El hecho, sin interpretación añadida                                                                                                                                      |
| `fuente_ref`    | Enlaza con `fuentes.csv`                                                                                                                                                  |
| `corroboracion` | `una_parte` si lo afirma solo una de las organizaciones implicadas · `prensa` si lo publica un medio sin aportar verificación propia · `dos_partes` si lo afirman las dos |

**Campos de las superficies**

| Campo | Qué contiene |
|---|---|
| `superficie_id` | Identificador, `S01`–`S10` |
| `elemento` | Parte de la plataforma |
| `descripcion` | Qué es |
| `gestionada_por` | `plataforma`, `usuario` o `compartida`: quién decide sobre ella |
| `mencion_en_cronologia_inicial` | Filas `C…` que hablan de esa parte |

**Puedes ampliar las fuentes.** Si encuentras otra fuente pública útil, añádela con su URL y su fecha de consulta y cítala como `F13`, `F14`… Tus fuentes cuentan igual que las dadas, siempre que respeten los límites de la actividad.

> Tres avisos antes de empezar.
>
> Una declaración oficial dice lo que **la organización afirma**, no lo que se ha verificado de forma independiente. Por eso existe la columna `corroboracion`: míratela antes de decidir tu nivel de confianza.
>
> Que un medio repita una declaración **no la corrobora**.
>
> Una fuente terciaria (`F09`) te sirve para orientarte, no para sostener un hecho.

## La fecha importa

Resuelves los pasos 1 a 4 **solo con la cronología inicial**. La posterior no la abres hasta el paso 5.

Si respondes una pregunta fechada con información que todavía no existía, no estás mejor documentado: cometes un error de método que invalida tu juicio. Y penaliza.

## Cómo referenciar

Debes acompañar cada afirmación que hagas con el identificador del que sale, entre paréntesis: `(C05)`, `(C07, C08)`, `(S06)`, `(F01)`. Sin identificador, tu afirmación no cuenta.

---

## Paso 1 · Ordena lo que sabes

**1.1.** Clasifica cada frase como **dato**, **información**, **inteligencia** o **ninguna de las tres**, con una línea de justificación.

|       | Frase                                                                                                                                                                                                                                                            |
| ----- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **A** | «El 16 de julio la plataforma publicó que había detectado un acceso no autorizado a su infraestructura de producción.»                                                                                                                                           |
| **B** | «No hay responsable identificado ni se conoce el modelo que operaba el marco de agentes.»                                                                                                                                                                        |
| **C** | «El acceso inicial entró por el procesamiento de conjuntos de datos y la propia plataforma declara verificada como no comprometida su cadena de suministro de software: el problema se concentra en sus sistemas internos, no en los artefactos que distribuye.» |
| **D** | «Como no hay evidencia de manipulación de los artefactos públicos, los modelos que ya hemos descargado son seguros.»                                                                                                                                             |
| **E** | «Es probable que el riesgo inmediato esté en nuestras credenciales de la plataforma y no en los modelos ya descargados; conviene rotarlas antes del comité y mantener las descargas bajo observación.»                                                           |

**1.2.** Formula ahora un dato, una información y una inteligencia propios a partir del material. La **información** debe combinar al menos dos filas **de archivos distintos** (por ejemplo, una superficie y un hecho de la cronología). La **inteligencia** debe servirte para elegir entre las opciones del comité.

| Capa | Formulación | Filas usadas | Qué limitación tiene |
|---|---|---|---|
| Dato | | | |
| Información | | | |
| Inteligencia | | | |

## Paso 2 · Completa el requerimiento

Lo único que tienes como encargo es lo que te escribió tu responsable:

> «He visto lo de la brecha de Hugging Face. Mira a ver todo lo que haya y dime si nos afecta.»

Así no puedes trabajar: **está incompleto**.

**2.1.** Revisa esa petición contra los siete componentes del requerimiento. Marca cuáles están y cuáles faltan.

| Componente | ¿Está? | Qué dice, o qué falta |
|---|---|---|
| Destinatario | | |
| Decisión | | |
| Objeto | | |
| Horizonte | | |
| Alcance | | |
| Exclusiones | | |
| Producto | | |

**2.2.** Completa los que faltan, con contenido concreto para este caso. Si alguno está pero resulta impreciso, concrétalo.

**2.3.** Escribe el requerimiento ya completo en **una frase**.

**2.4.** Formula **dos o tres preguntas de inteligencia** que se deriven de él, priorizadas, indicando a qué opción del comité te ayuda cada una.

| Prioridad | Pregunta | Te ayuda a decidir |
|---:|---|---|
| 1 | | |
| 2 | | |

Tienes la [plantilla de requerimiento de inteligencia](https://github.com/hector-ae21/CIBINT/blob/main/plantillas/plantilla-requerimiento-inteligencia.md) como apoyo.

## Paso 3 · Planifica el ciclo

Rellena una fila por fase. **Entrada** es con qué llegas a la fase, **salida** es qué produces, y **siguiente fase** es adónde va esa salida.

| Fase | Entrada utilizada | Decisión o tarea | Salida | Siguiente fase |
|---|---|---|---|---|
| Dirección y planificación | | | | |
| Obtención | | | | |
| Procesamiento | | | | |
| Análisis y producción | | | | |
| Difusión | | | | |
| Retroalimentación | | | | |

**La columna «Siguiente fase» no tiene por qué seguir el orden de la tabla.** Si la salida de una fase te obliga a volver a una anterior, indícalo ahí: eso es un retorno, y el ciclo los tiene.

## Paso 4 · Responde

**4.1.** Escribe la nota para el comité. Breve y con estas cuatro cosas:

1. qué puedes afirmar el 20 de julio sobre si les afecta;
2. tu **nivel de confianza** (baja, media o alta) y **por qué es esa**;
3. qué opciones recomiendas activar y cuáles no, y por qué tu medida es proporcionada;
4. una **limitación**: qué te falta saber y cómo condiciona lo anterior.

**4.2.** Repasa tu propia nota y marca tres de sus afirmaciones.

| Afirmación de tu nota | ¿Hecho, inferencia o supuesto? | Por qué |
|---|---|---|
| | | |

## Paso 5 · Revisa

Abre ahora [cronologia-posterior.csv](datos/cronologia-posterior.csv).

| | |
|---|---|
| **5.1.** | Dos conclusiones tuyas que **cambian** y una que **se confirma**, cada una con el hecho (`C…`) que lo provoca. |
| **5.2.** | ¿Cambiarías tu recomendación al comité? Sí o no, y por qué. |
| **5.3.** | En una frase: qué te enseña esto sobre la retroalimentación. |

---

## Límites

Este caso es real y afecta a organizaciones reales. Se te aplican las [normas de la asignatura](../../NORMAS.md) y, además:

**No puedes**

- interactuar con la infraestructura, las cuentas, las API o los servicios de las organizaciones citadas;
- escanear, sondear o comprobar la existencia de cualquier activo del caso;
- buscar, descargar, reconstruir o publicar exploits, cargas útiles, pruebas de concepto o indicadores operativos;
- buscar o conservar credenciales, tokens, volcados o conjuntos de datos relacionados con el incidente;
- investigar o perfilar a las personas citadas en las noticias: esto va de organizaciones, no de personas;
- atribuir responsabilidad o intención más allá de lo que las fuentes afirman de forma expresa;
- contactar con las organizaciones implicadas o sus canales.

**Sí puedes**

- leer y citar las fuentes de `fuentes.csv`, y añadir otras públicas con su URL y fecha de consulta;
- describir el incidente al nivel al que lo describen las fuentes;
- proponer medidas defensivas, reversibles y proporcionadas.

**Ante una duda:** para, no descargues nada y escribe por el canal privado de la asignatura. Preguntar no te penaliza.

---

## Uso de inteligencia artificial

**Nivel D · IA integrada.** Puedes usar cualquier herramienta de inteligencia artificial, para lo que quieras y sin justificarlo.

La única condición es que incluyas en tu entrega el apartado **«Uso de inteligencia artificial»** con, como mínimo:

1. **Herramienta utilizada** (o «No se ha utilizado ninguna»).
2. **Para qué la usaste**: corrección de texto, búsqueda de ideas, generación de código, redacción, etc.
3. **En qué fase del trabajo intervino**.

> Si no incluyes ese apartado, tu entrega está **incompleta y no se califica**.

---

## Entrega

Responde sobre la **[plantilla de respuesta](plantilla-respuesta.md)**, que ya trae el esquema completo con todos los apartados y las tablas vacías.

| Campo | Indicación |
|---|---|
| Código | `A01` |
| Modalidad | Individual |
| Ruta | `entregas/apellidoNombre/A01/README.md` |
| Canal | *Pull request* desde tu *fork* |
| Título del *pull request* | `[A01] Apellido Nombre` |
| Fecha límite | Lunes 21 de septiembre de 2026, antes de las 12:15 |

1. Actualiza tu *fork* y crea una rama para esta actividad, por ejemplo `a01-apellidoNombre`.
2. **Copia [plantilla-respuesta.md](plantilla-respuesta.md) a `entregas/apellidoNombre/A01/README.md`.** Ese es el archivo sobre el que trabajas, dentro de **tu** carpeta. No edites la plantilla original ni la carpeta de nadie más.
3. Rellena los apartados sin cambiar su orden ni su numeración. Si un apartado no te aplica, escribe por qué en lugar de borrarlo.
4. Abre el *pull request*. Solo puede tocar tu carpeta. Si te piden correcciones, sigue en la misma rama.

Todo es publicable: el material es público. Si aun así tu entrega contuviera algo que no deba publicarse, no la subas y avisa por el canal privado.

---

## Rúbrica

| Criterio | Peso | Excelente | Notable | Suficiente | Insuficiente |
|---|---:|---|---|---|---|
| **C1 · Dato, información e inteligencia**<br>Paso 1 | 2,5 | **2,2 – 2,5** · Clasifica bien las cinco frases, incluida la que no es ninguna, y da el motivo exacto. Formula tres piezas originales: la información cruza de verdad dos archivos distintos y la inteligencia apunta a una opción concreta del comité con su limitación. | **1,6 – 2,1** · Hasta dos clasificaciones discutibles pero razonadas; las formulaciones son correctas aunque la inteligencia se quede en resumen o la información cruce dos filas del mismo archivo. | **1,0 – 1,5** · Distingue las tres capas pero falla en los casos límite, o la información no combina dos filas. | **0,0 – 0,9** · Clasifica sin justificar, confunde inteligencia con opinión, o copia las frases dadas. |
| **C2 · Requerimiento y preguntas**<br>Paso 2 | 2,5 | **2,2 – 2,5** · Detecta exactamente qué componentes faltan en la petición y distingue los que están pero imprecisos de los que directamente faltan. Los completa con contenido propio del caso y con exclusiones que descartan algo que alguien intentaría de verdad. El requerimiento cabe en una frase con objeto, decisión, límite y plazo. Las preguntas se responden con evidencia y están priorizadas por utilidad para decidir. | **1,6 – 2,1** · Identifica bien las ausencias principales; el requerimiento es correcto y las preguntas útiles, con alguna cercana a una consulta de búsqueda o exclusiones genéricas. | **1,0 – 1,5** · Confunde algún componente presente con ausente; el requerimiento deja alcance o plazo abiertos; las preguntas son temas, no preguntas. | **0,0 – 0,9** · No revisa la petición, la reformula sin acotarla, o las preguntas son consultas a buscadores. |
| **C3 · Ciclo de inteligencia**<br>Paso 3 | 1,5 | **1,3 – 1,5** · Encadena de verdad: la salida de una fase es la entrada de la siguiente, todo referido a este caso y compatible con las 13:00. En «Siguiente fase» marca al menos un retorno a una fase anterior, justificado por la salida de esa fila. | **0,9 – 1,2** · Aplica las fases al caso con una cadena coherente, pero no marca retorno o lo justifica flojo. | **0,6 – 0,8** · Las fases son correctas pero intercambiables con cualquier otro caso, y las entradas y salidas no se relacionan entre sí. | **0,0 – 0,5** · Copia la definición de las fases, omite alguna o deja columnas sin contenido. |
| **C4 · Valoración y rigor**<br>Paso 4 | 2,0 | **1,8 – 2,0** · Justifica el nivel de confianza en vez de enunciarlo, y lo apoya en quién sostiene cada hecho (`corroboracion`). Recomienda de forma proporcionada a la evidencia, dice qué deja fuera y nombra una limitación concreta con su efecto. Etiqueta bien las tres afirmaciones como hecho, inferencia o supuesto. | **1,3 – 1,7** · Recomienda razonablemente pero justifica la confianza por encima, o etiqueta bien solo dos de las tres afirmaciones. | **0,8 – 1,2** · La medida es aceptable, pero la confianza es decorativa o la limitación es genérica. | **0,0 – 0,7** · Afirma o descarta la afectación sin sustento, recomienda algo desproporcionado, o confunde hecho con inferencia. |
| **C5 · Revisión**<br>Paso 5 | 1,0 | **0,9 – 1,0** · Las tres revisiones son honestas, incluye una conclusión propia corregida sin maquillarla, y ancla cada una en un hecho identificado de la cronología posterior. Distingue lo que cambia de lo que no. | **0,6 – 0,8** · Revisa correctamente pero en corto: confirma casi todo y corrige poco. | **0,3 – 0,5** · Resume la cronología posterior sin volver sobre las conclusiones propias. | **0,0 – 0,2** · No revisa nada, o reescribe la valoración fingiendo que ya decía eso. |
| **C6 · Trazabilidad**<br>Toda la entrega | 0,5 | **0,5** · Todas las afirmaciones llevan identificador y el identificador dice lo que se le atribuye. Las fuentes añadidas van con URL y fecha de consulta. | **0,3 – 0,4** · Referencia casi todo, con alguna afirmación suelta o alguna fuente sin fecha. | **0,2** · Referencia de forma irregular. | **0,0 – 0,1** · No referencia, o los identificadores no corresponden con lo que dicen. |
| | **10** | | | | |

**Qué separa un 8 de un 10.** Una entrega completa, correcta y bien escrita que aplica bien el esquema del tema es un **8**. Para subir hacen falta, a la vez:

- que no se filtre ni una sola vez la cronología posterior en los pasos 1 a 4;
- que los identificadores existan y digan de verdad lo que se les atribuye;
- que la recomendación diga explícitamente **qué no cubre**;
- que en el paso 5 se **corrija** una conclusión propia, no solo se confirme;
- que no haya ningún dato inventado ni ninguna fuente forzada a decir más de lo que dice.

**Penalizaciones.** Se restan de la suma. La nota no baja de 0 ni sube de 10.

| Incumplimiento | Efecto |
|---|---|
| Falta el apartado de uso de inteligencia artificial | Entrega incompleta: no se califica |
| Usar la cronología posterior en los pasos 1 a 4 | −1,0 por paso afectado, hasta −2,0 |
| Afirmar algo sin identificador, o con un identificador que no dice eso | −0,25 por caso, hasta −1,0 |
| Atribuir responsabilidad o intención más allá de las fuentes | −1,0 |
| Introducir datos o hechos que no están en el material ni en una fuente citada | −2,0 |
| Modificar archivos fuera de la carpeta personal | Se devuelve el *pull request* sin revisar |
| Realizar cualquier acción prohibida en los límites | Actividad no evaluable y aplicación de las [normas](../../NORMAS.md) |
| Incluir credenciales, cargas útiles, indicadores operativos o datos personales | Actividad no evaluable y aviso por canal privado |

---

## Antes de entregar

- [ ] He trabajado sobre una copia de la plantilla, dentro de `entregas/apellidoNombre/A01/`.
- [ ] He resuelto los pasos 1 a 4 solo con la cronología inicial.
- [ ] Cada afirmación lleva su identificador y he comprobado que dice lo que le atribuyo.
- [ ] No he interactuado con ninguna infraestructura ni servicio del caso.
- [ ] No incluyo exploits, credenciales, indicadores operativos ni datos personales.
- [ ] He incluido el apartado de uso de inteligencia artificial con los tres puntos.
- [ ] Solo he modificado `entregas/apellidoNombre/A01/`.
