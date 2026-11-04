# Registro de uso de inteligencia artificial · Proyecto final

**Estudiante:** Eirik Alberto Rosete León  
**Título del proyecto:** HSE de Irlanda: ¿qué prioridades de continuidad y controles defensivos se justifican en una red sanitaria interconectada?  
**Hito y fecha:** PF-TEMA (propuesta v0.1) · 28 de octubre de 2026

## Declaración

«He utilizado inteligencia artificial únicamente para las tareas permitidas, según los usos y evidencias que se detallan a continuación».

Precisión: los dos usos registrados son una verificación mecánica del recuento de palabras y la ayuda para rellenar este registro. No son síntesis de información, corrección ortográfica ni consulta de legislación, así que los declaro por transparencia. En ninguno de ellos la IA investigó el caso, analizó datos ni redactó contenido de la propuesta.

## Uso 01

- **Quién:** Eirik Alberto Rosete León
- **Fecha:** 28 de octubre de 2026
- **Herramienta y modelo, si consta:** Claude Code (CLI), modelo Claude Sonnet 5.5 (`claude-sonnet-5-5`)
- **Para qué:** Verificación del recuento de palabras de la propuesta con el script oficial `contar-palabras.mjs`. No encaja en síntesis, corrección ortográfica ni consulta de legislación; se declara por transparencia.
- **Hito y apartado del trabajo:** PF-TEMA, propuesta v0.1, cabecera (línea «Número de palabras y método de recuento»)
- **Fuentes o texto propio utilizados como entrada:** `entregas/roseteEirik/PF/TEMA/propuesta.md` (texto propio) y `proyecto-final/contar-palabras.mjs` (script del curso)
- **Prompt, copiado tal cual:**

```text
cuenta las palabras de @fork-entregas/entregas/roseteEirik/PF/TEMA/propuesta.md y compara con el script @fork-entregas/proyecto-final/contar-palabras.mjs
```

- **Respuesta completa:**

```text
El script cuenta **899 palabras** en `propuesta.md`, la misma cifra que declaras en la línea 9. Esa cifra coincide con lo que mide el script.

| Método | Resultado |
|---|---|
| `contar-palabras.mjs --propuesta` | **899** |
| `wc -w` sobre el archivo completo | 1206 |

La diferencia de 307 palabras con `wc -w` se debe a qué texto cuenta cada método. El script solo cuenta desde `## 1.` hasta antes de `## 8.`, así que deja fuera:

- **El encabezado** (líneas 1–9), con título, estudiante, versión, modalidad y la propia línea del recuento.
- **La tabla de referencias del apartado 5**, porque descarta las líneas que empiezan por `|` en esa sección. Las tablas de los apartados 2, 3 y 4 sí se cuentan.
- **El apartado 8 y los enlaces finales.**

Dentro del tramo que cuenta, el script también:

- elimina las URLs y deja solo el texto visible de los enlaces Markdown;
- no cuenta los símbolos de formato, como `**`, `|`, `---` y `#`;
- trata como una sola palabra las expresiones con apóstrofo, punto, coma o guion, como `art. 5.1.c` o `80 %`.

No hay discrepancia entre lo declarado y lo medido. Si el límite de la propuesta se mide con este script, el valor oficial es 899.
```

- **Qué hice con la respuesta:** No incorporé nada al texto de la propuesta. La cifra 899 ya estaba declarada por mí; la respuesta solo la confirmó y explicó la diferencia con `wc -w`.
- **Qué comprobé y con qué fuentes originales u oficiales:** La herramienta ejecutó `node proyecto-final/contar-palabras.mjs entregas/roseteEirik/PF/TEMA/propuesta.md --propuesta` y devolvió 899. He revisado el código del script (tramo `## 1.` a `## 8.`, exclusión de la tabla del apartado 5) y es coherente con la explicación.
- **Evidencia:** `ia/uso-01.md`
- **Usos relacionados:** Uso 02 (misma conversación)

## Uso 02

- **Quién:** Eirik Alberto Rosete León
- **Fecha:** 28 de octubre de 2026
- **Herramienta y modelo, si consta:** Claude Code (CLI), modelo Claude Sonnet 5.5 (`claude-sonnet-5-5`)
- **Para qué:** Ayuda para cumplimentar este registro. No encaja en las tareas permitidas; se declara por transparencia.
- **Hito y apartado del trabajo:** PF-TEMA, `registro-ia.md`
- **Fuentes o texto propio utilizados como entrada:** La plantilla `registro-ia.md` y la conversación del Uso 01
- **Prompt, copiado tal cual:**

```text
Rellena el uso ia
```

- **Respuesta completa:**

```text
Puedo rellenar el encabezado, pero la declaración y los usos solo puedes confirmarlos tú. El propio documento dice que un uso no declarado o un registro falso supone un 0 en el proyecto final, y no tengo forma de saber si usaste IA en otras conversaciones.

Antes de escribir nada, hay un punto sobre esta sesión: te ayudé a contar palabras y a comparar la cifra con el script. Eso no encaja con ninguno de los tres usos permitidos (síntesis de información ya encontrada, corrección ortográfica o consulta de legislación). No creo que tengas que registrarlo si no influyó en el contenido de la propuesta, pero te lo señalo para que lo decidas tú.

[Pregunta: «¿Qué declaración corresponde en este hito?» Opciones: Sin uso de IA / Con uso de IA / Incluir esta sesión. Respuesta elegida: Incluir esta sesión.]
```

- **Qué hice con la respuesta:** Decidí registrar la sesión completa y pedí que se redactara este documento a partir de ella. Revisé el resultado antes de entregarlo.
- **Qué comprobé y con qué fuentes originales u oficiales:** Comprobé que la plantilla y el [enunciado](../README.md#uso-de-inteligencia-artificial) exigen declarar cualquier uso y que los textos copiados coinciden con la conversación.
- **Evidencia:** `ia/uso-02.md`
- **Usos relacionados:** Uso 01

La IA no se cita como fuente de un hecho ni de una norma. La investigación, el análisis, las decisiones y la redacción son de elaboración propia. El incumplimiento de las [condiciones de IA](../README.md#uso-de-inteligencia-artificial), incluido el uso no declarado o la falta del registro y de sus evidencias obligatorias, supondrá **0 sobre 10 en el proyecto final**.
