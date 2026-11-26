# Registro de uso de inteligencia artificial · Proyecto final

Estudiante: Eirik Alberto Rosete León  
Título del proyecto: HSE de Irlanda: ¿qué prioridades de continuidad y controles defensivos se justifican en una red sanitaria interconectada?  
Hito y fecha: PF-P1 (informe v0.1) · 11 de noviembre de 2026

## Declaración

"He utilizado inteligencia artificial únicamente para las tareas permitidas, según los usos y evidencias que se detallan a continuación".

Precisión: los usos 01 y 02 corresponden a PF-TEMA y están registrados en [`../TEMA/registro-ia.md`](../TEMA/registro-ia.md); por eso la numeración de este hito empieza en el uso 03. El uso 03 (PF-P1) es la creación de la estructura de carpetas del hito a partir de las plantillas oficiales y una explicación de los requisitos del enunciado. El uso 04 (PF-P1) es una revisión ortográfica y gramatical, que es un uso permitido, junto con el recuento de palabras y la actualización de este registro. Salvo la revisión ortográfica, ninguno de estos usos es síntesis de información, corrección ortográfica ni consulta de legislación, así que los declaro por transparencia. En ninguno de ellos la IA investigó el caso, buscó fuentes, analizó datos ni redactó contenido de la propuesta o del informe.

## Uso 03

- Quién: Eirik Alberto Rosete León
- Fecha: 8 de noviembre de 2026
- Herramienta y modelo, si consta: Claude Code (extensión de VS Code), modelo Claude Opus 5.5 (`claude-opus-5-5`)
- Para qué: Creación de la estructura de carpetas de PF-P1 y explicación de los requisitos del hito según el enunciado. No encaja en las tareas permitidas; se declara por transparencia.
- Hito y apartado del trabajo: PF-P1, estructura de `entregas/roseteEirik/PF/`
- Fuentes o texto propio utilizados como entrada: La resolución del docente del 4 de noviembre de 2026; `proyecto-final/02-proceso-y-entregas.md`, `proyecto-final/README.md` y las plantillas de `proyecto-final/plantillas/` (documentos del curso); `TEMA/propuesta.md` y `TEMA/registro-ia.md` (texto propio)
- Acciones de la herramienta: Leyó los documentos indicados. Creó la rama local `PF/p1` y las carpetas `P1/`, `P1/registros/`, `P1/ia/`, `P1/recursos/` y `TEMA/ia/`. Copió sin modificar las plantillas oficiales (`informe.md`, `seguimiento.md` y los cuatro CSV) y `TEMA/registro-ia.md`. Creó `PF/README.md`, `TEMA/README.md` y `P1/README.md`, que solo contenían índices de archivos. No hizo commit ni redactó contenido del informe.
- Prompt, copiado tal cual:

````text
Vale Claude, la entrega del PF-01 se acerca y debo entregarlo en tiempo. Realicemos la estructura de los directorios., dime en que consiste esta entrega y cómo continuar con mi trabajo si el docente me marcó lo siguiente:

Fecha: 4 de noviembre de 2026
Aprobada con condiciones

Sustituye F-03: el enlace pasa por removepaywall.com, un servicio para eludir el muro de pago del medio. Eludir controles de acceso está prohibido por las normas de la asignatura. Cita la URL original del Irish Independent solo si puedes leerla legítimamente, o usa otra fuente de prensa de acceso abierto.
Mantén las cifras de cancelaciones y del volumen exfiltrado como afirmaciones atribuidas a quien las hace, no como hechos, hasta contrastarlas.
En P1, concreta en qué fecha y con qué fuentes revisarás cada pregunta.
Esto lo tendrás en tu archivo de propuesta en la sección 8 de Resolución de propuesta
````

- Respuesta completa:

````text
[Mensajes intermedios]
Voy a revisar el repositorio para entender qué pide PF-01 y cómo está tu propuesta.
PF-01 parece ser `PF-P1` (primer avance), que vence **mañana, lunes 9 de noviembre a las 23:59**. Leo qué exige exactamente.
Ahora reviso las plantillas, tu registro de IA y la entrega de un compañero como referencia de formato.
Antes de crear nada, compruebo las reglas de IA del enunciado, porque condicionan qué puedo hacer yo y qué tienes que escribir tú.
Tengo lo que necesito. Creo una rama para el hito y la estructura de `P1/`, copiando las plantillas oficiales sin cambios (no escribo contenido del informe; te explico el motivo abajo).

[Mensaje final]
He creado la estructura del primer avance en la rama `PF/p1` (no he hecho commit). Una aclaración: "PF-01" corresponde al hito **PF-P1, primer avance**. Vence **mañana, lunes 9 de noviembre, a las 23:59 (Europe/Madrid)**, y antes de esa hora tiene que estar abierto el pull request.

## Lo que he creado

```text
entregas/roseteEirik/PF/
├── README.md              ← índice de hitos (faltaba)
├── TEMA/
│   ├── README.md          ← faltaba
│   └── ia/                ← vacía (ver punto 1 abajo)
└── P1/
    ├── README.md          ← faltan la versión y el número de palabras
    ├── informe.md         ← plantilla oficial, sin rellenar
    ├── seguimiento.md     ← plantilla oficial
    ├── registro-ia.md     ← copia de tu registro de TEMA (usos 01 y 02)
    ├── registros/         ← fuentes, hallazgos, bitácora, integridad (solo encabezados)
    ├── ia/
    └── recursos/
```

Solo he copiado las plantillas y creado los índices. No he escrito contenido porque las normas (nivel C) prohíben usar IA para redactar apartados, elaborar tablas, buscar o seleccionar fuentes y diseñar el método. Por eso tampoco te propongo una fuente que sustituya a F-03.

## Qué pide PF-P1 (según [02-proceso-y-entregas.md](proyecto-final/02-proceso-y-entregas.md))

El cuerpo de `informe.md` tiene un máximo de 2.500 palabras. Los apartados que aún no hayas trabajado se marcan como pendientes. Tiene que incluir:

1. **El encargo y el alcance aprobados**, con las condiciones del docente ya incorporadas.
2. **El contexto del caso**, separando los hechos de las afirmaciones pendientes de contrastar.
3. **El plan de fuentes y consultas**, donde cada acción responde a una PI.
4. **La evaluación legal y de OPSEC**, con los datos excluidos y las condiciones de parada.
5. **Al menos 5 fuentes en `fuentes.csv`**, dos de ellas primarias. F-01 y F-02 ya lo son.
6. **Las primeras observaciones con su referencia**, sin adelantar conclusiones.
7. **La bitácora, el registro de IA y `seguimiento.md`.**

## Cómo aplicar cada condición del docente

- **F-03:** retírala. En su lugar usa la URL original del Irish Independent solo si puedes leerla sin eludir el muro de pago, o busca tú otra fuente de prensa de acceso abierto. Anota el cambio en `seguimiento.md`, en «Correcciones y decisiones», y la consulta en `bitacora.csv`.
- **Cifras:** las cancelaciones y el volumen exfiltrado se redactan como afirmaciones atribuidas («según X…»), no como hechos. Esto también afecta al §1 de tu propuesta, donde las cancelaciones aparecen como hecho citando F-03.
- **Calendario por pregunta:** para cada pregunta, de PI-01 a PI-04, indica la fecha de revisión y las fuentes que usarás. Encaja en la tabla «Estado de las preguntas» de `seguimiento.md` y en el §5 del informe.

## Dos riesgos que debes atender ya

1. **Faltan las evidencias de IA de TEMA.** Tu `registro-ia.md` cita `ia/uso-01.md` y `ia/uso-02.md`, pero esos archivos no existen en el repositorio. Si faltan evidencias, el proyecto final se califica con 0/10. La entrega de TEMA ya está cerrada, así que pregunta al docente si puedes añadirlas allí. En `P1/ia/` tienes que incluirlas de todos modos, porque el registro es acumulado.
2. **Esta conversación cuenta como uso 03.** Tienes que declararla en `P1/registro-ia.md` con el prompt y la respuesta completos, y guardar la exportación en `P1/ia/uso-03.md`. Igual que en los usos 01 y 02, no es uno de los usos permitidos, así que conviene declararla por transparencia.

Cuando termines, cuenta las palabras con `node proyecto-final/contar-palabras.mjs` (revisa en el script qué opción corresponde a un informe de avance). Después haz commit y push de `PF/p1` y abre el PR titulado `[PF-P1] roseteEirik`.
````

- Qué hice con la respuesta: Usé la estructura propuesta inicialmente, pero la simplifiqué eliminando README que colocó la IA innecesariamente
- Qué comprobé y con qué fuentes originales u oficiales: Las fuentes proporcionadas son correctas y están en el .csv de fuentes
- Evidencia: `ia/uso-ia-p1.txt`
- Usos relacionados: Ninguno (conversación anterior a la del uso 04, en la misma sesión de la herramienta)

## Uso 04

- Quién: Eirik Alberto Rosete León
- Fecha: 11 de noviembre de 2026
- Herramienta y modelo, si consta: Claude Code (extensión de VS Code), modelo Claude Opus 5.5 (`claude-opus-5-5`)
- Para qué: Corrección ortográfica y gramatical de textos propios, que es un uso permitido; la herramienta solo señaló los errores y no reescribió los textos. También el recuento de palabras con el script oficial y la actualización de este registro, que no encajan en las tareas permitidas y se declaran por transparencia.
- Hito y apartado del trabajo: PF-P1, `informe.md`, `README.md`, `seguimiento.md` y `registro-ia.md`; PF-TEMA, `propuesta.md`
- Fuentes o texto propio utilizados como entrada: `P1/informe.md`, `P1/README.md`, `P1/seguimiento.md`, `P1/registros/fuentes.csv`, `P1/registros/bitacora.csv`, `P1/registro-ia.md` y `TEMA/propuesta.md` (texto propio); `proyecto-final/contar-palabras.mjs` (script del curso)
- Acciones de la herramienta: Leyó los archivos indicados. Ejecutó `node proyecto-final/contar-palabras.mjs entregas/roseteEirik/PF/P1/informe.md` (resultado: 2113 palabras) y `node proyecto-final/contar-palabras.mjs entregas/roseteEirik/PF/TEMA/propuesta.md --propuesta` (resultado: 1106 palabras). Añadió los usos 03 y 04 a este registro y actualizó la «Precisión» de la declaración. No modificó ningún otro archivo.
- Prompt, copiado tal cual:

```text
Vale, revisa si hay errores de redacción y también haz el conteo de palabras. Al finalizar, coloca el registro en registro IA, toma como referencia la plantilla
```

- Respuesta completa:

````text
[Mensajes intermedios]
La estructura ha cambiado desde la última vez (estás en `main` y faltan algunos archivos). Leo el informe y el resto de lo que has escrito.
He terminado la revisión. Ahora añado los usos 03 y 04 al registro de IA de P1.
El registro ahora solo tiene 14 líneas y termina en «## Uso 01». Antes de tocar nada, compruebo qué ha pasado.
El registro se ha recortado justo después de mi primera edición, y `informe.md` y `README.md` también han cambiado en los últimos minutos. Parece que estás editando a la vez en el IDE. Compruebo si los errores que encontré siguen ahí.
Los errores siguen en las mismas líneas. Ya has corregido el recuento en `README.md` (2113), pero `seguimiento.md` todavía dice 1759. El problema es el registro de IA: no quiero sobrescribir algo que estés editando tú.

[Pregunta de la herramienta: «P1/registro-ia.md se ha recortado hace un momento: termina en "## Uso 01" y han desaparecido los usos 01 y 02. ¿Lo has borrado tú a propósito o ha sido un accidente del editor? ¿Cómo sigo?» Opciones: «Restaurar y añadir» / «Lo estoy editando yo». Respuesta del estudiante: «Los eliminé porque corresponden al PF/TEMA y están ahí documentados. Ahora el uso de ia corresponde al informe y parte 1».]

Entendido. Respeto tu decisión, pero el enunciado exige que el registro de cada hito sea acumulado; te lo explico en el resumen. Mantengo la numeración 03 y 04 para que no coincida con los usos de TEMA, y sustituyo el encabezado vacío «## Uso 01».

[Mensaje final]
Revisión de redacción y recuento de palabras de PF-P1. No he cambiado el texto de tus archivos: te indico los errores y tú decides cómo corregirlos (la corrección ortográfica solo es un uso permitido si no reescribe el contenido). Sí he añadido los usos 03 y 04 a `P1/registro-ia.md`.

## Recuento de palabras (script oficial)

| Archivo | Resultado | Límite |
|---|---|---|
| `P1/informe.md` (apartados 1 a 10) | 2113 | 2500 |
| `TEMA/propuesta.md` (`--propuesta`) | 1106 | 900 |

`P1/README.md` ya dice 2113, pero la línea 10 de `P1/seguimiento.md` sigue diciendo 1759.

## Errores de redacción en `P1/informe.md`

| Línea | Texto | Problema |
|---|---|---|
| 93 y 136 | «El NCSC (F-02) informa que se aplazaron» | En el español de España se recomienda «informa **de** que». |
| 108 | «Descifrado el 100 % de los servidores y restauradas el 99 % de las aplicaciones» | Concordancia desigual: «descifrado» (singular) y «restauradas» (plural). Usa la misma forma en ambos. |
| 116 | «…identificando estos elementos censurados como limitaciones de información y analizaremos las fuentes de prensa…» | Cambio de persona: la frase empieza impersonal («se limitará») y termina en primera persona del plural («analizaremos»). Además, el gerundio queda coordinado con un verbo conjugado. |
| 118 | «Formará parte de la siguiente entrega, conjunta a P2.» | «Conjunta a» no es correcto: sería «junto con» o «conjuntamente con». Además, falta el sujeto de «formará». |
| 135 | «Ni el volumen total real de citas perdidas ni permite calcular…» | Los dos «ni» no coordinan elementos equivalentes (un sustantivo y un verbo). |
| 136 | «La eficacia operativa de esos planes de continuidad ni si los procedimientos…» | Hay un «ni» sin otra negación delante. |
| 137 | «Cómo es que las dependencias técnicas… explican» | «Cómo es que» es coloquial; en un informe sobra «es que». |
| 138 | «(F-01),  durante» | Hay doble espacio. |

## Errores de redacción en otros archivos

- **`TEMA/propuesta.md`**
  - Línea 4: «09 de noviembre». En fechas escritas con letra, el día va sin cero: «9 de noviembre».
  - Apartado 6: «Se implementarán conjuntamente a la segunda entrega» tiene el mismo error que la línea 118 del informe.
- **`P1/seguimiento.md`**, «Revisión de esta entrega»: «Decisión que necesitas consultar: Se consultará…». Después de dos puntos va minúscula, como en el resto de puntos de esa lista.

## Otros problemas (no son de redacción)

1. **El registro de IA tiene que ser acumulado.**
   - El enunciado pide «conservarse un registro acumulado y entregarse una copia actualizada en cada hito», y la plantilla añade que «se conservarán los usos anteriores».
   - La falta del registro o su manipulación se califica con 0/10.
   - Te recomiendo volver a poner los usos 01 y 02 en `P1/registro-ia.md`. Si prefieres no hacerlo, consúltalo antes con el docente.
2. **Has modificado `TEMA/propuesta.md`, que ya se entregó y evaluó.**
   - La versión editada pasa de 899 a 1106 palabras (el límite es 900).
   - Las normas dicen que no se sustituyan entregas anteriores ni la versión evaluable sin autorización.
   - Las condiciones del docente ya están incorporadas en el informe de P1, así que puedes devolver la propuesta a su estado anterior con `git restore entregas/roseteEirik/PF/TEMA/propuesta.md`, o consultar antes de dejar la versión 0.2.
   - Al quitar las negritas, las líneas de la cabecera ya no tienen salto de línea y se mostrarán juntas en un solo párrafo.
3. **Fecha de F-02:** la propuesta v0.2 pone 16/05/2021, mientras que `informe.md` y `fuentes.csv` ponen 14/05/2021.
4. **Faltan las evidencias de IA:** no existe ninguna carpeta `ia/`, ni en TEMA ni en P1. Los registros citan `uso-01.md` a `uso-04.md` y, sin esas evidencias, la calificación del proyecto final es 0/10.
5. **No hay rama de entrega:** estás en `main` y el PR de P1 no está abierto. El plazo de PF-P1 terminó el 9 de noviembre, así que avisa al docente.

## Registro de IA

En `P1/registro-ia.md` he sustituido el encabezado vacío «## Uso 01» por dos usos:
- **Uso 03:** la sesión del 8 de noviembre, en la que se creó la estructura de carpetas.
- **Uso 04:** esta revisión, con el prompt, los mensajes intermedios, la pregunta que te hice y esta respuesta completos.

También he ajustado la «Precisión» de la declaración. Te quedan por rellenar dos campos de cada uso: «Qué hice con la respuesta» y «Qué comprobé», porque solo tú sabes qué aceptas y qué descartas. Además, exporta la conversación a `P1/ia/uso-03.md` y `P1/ia/uso-04.md`.
````

- Qué hice con la respuesta: Hice cambios en la redacción y agregué el registro IA al directorio corresponiente. Con la modificación de TEMA/propuesto.md , fue hacer los cambios de la retroalimentación ahí para pasarlo a limpio en el informe.
- Qué comprobé y con qué fuentes originales u oficiales: Que la ejecución del script fuera correcta y analizar la gramática propuesta
- Evidencia: `ia/uso-ia-p1.txt`
- Usos relacionados: Uso 03 (misma sesión de la herramienta)

La IA no se cita como fuente de un hecho ni de una norma. La investigación, el análisis, las decisiones y la redacción son de elaboración propia. El incumplimiento de las [condiciones de IA](../../../../proyecto-final/README.md#uso-de-inteligencia-artificial), incluido el uso no declarado o la falta del registro y de sus evidencias obligatorias, supondrá 0 sobre 10 en el proyecto final.

