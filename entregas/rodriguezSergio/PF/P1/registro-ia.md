# Registro de uso de inteligencia artificial · Proyecto final

**Estudiante:** Sergio Rodríguez López

**Título del proyecto:** Incidente de ciberseguridad en Air Europa (2023-2024): evolución del alcance comunicado y pautas de protección al cliente ante exposición de datos

**Hito y fecha:** PF-P1, 09-11-2026, v0.2

## Declaración

«He utilizado inteligencia artificial únicamente para las tareas permitidas, según los usos y evidencias que se detallan a continuación».

## Uso 01

* **Quién:** Sergio Rodríguez López

* **Fecha:** 28-10-2026, v0.1

* **Herramienta y modelo, si consta:** Gemini

* **Para qué:** Corrección ortográfica

* **Hito y apartado del trabajo:** PF-TEMA (`propuesta.md`)

* **Fuentes o texto propio utilizados como entrada:** Borrador completo de `propuesta.md` redactado previamente.

* **Prompt, copiado tal cual:**

```text
Comprueba todo el contenido de mi documento para comprobar si todo tiene un buen formato de md o si contiene alguna falta ortográfica. Crea un listado con todos los fallos que contenga, separando los de formato con los de escritura
```

* **Respuesta completa:**

```text
El documento propuesta.md presenta un código Markdown estructuralmente sólido sin fallos de renderizado, pero contiene varios errores ortográficos y tipográficos que deben corregirse.

Fallos de formato (Markdown)

- No se han detectado errores de sintaxis. Las tablas, listas, cabeceras, negritas, cursivas y bloques de código en línea están correctamente construidos y se visualizarán sin problemas en cualquier visor estándar de Markdown.

Fallos de ortografía y redacción

- Sección 1 (párrafo 2): "avisos de INCIBE y INCIBE-CERT" debe cambiarse a "e INCIBE-CERT" por regla ortográfica ante palabras que empiezan por el sonido /i/.

- Sección 1 (párrafo 2): Existe un error tipográfico en "confirmaod"; lo correcto es "confirmado".

- Sección 2 (Tabla, fila de Utilidad del informe): Falta la tilde en "segun"; debe ser "según".

- Sección 3 (Tabla, fila PI-03): Falta la tilde diacrítica en "y que limitaciones"; al formar parte de una estructura interrogativa paralela, debe ser "qué".

- Sección 4 (Tabla, fila de Acciones expresamente excluidas): Falta la tilde en "aerolinea"; debe ser "aerolínea".

- Sección 4 (Tabla, fila de Condición de parada): Falta la tilde en el verbo "almacenara". Por el contexto de acciones en futuro ("se detendrá", "se consultará"), debe escribirse "almacenará".

- Sección 7 (Declaración): Falta la tilde en el verbo "comenzara". Al indicar una acción futura ("cuando se apruebe el alcance"), debe escribirse "comenzará".
```

* **Qué hice con la respuesta:** Apliqué manualmente las siete correcciones ortográficas y tipográficas indicadas sobre el archivo `propuesta.md`, sin modificar el sentido ni la estructura del texto.

* **Qué comprobé y con qué fuentes originales u oficiales:** Comprobé en el documento `propuesta.md` que las tildes y la conjunción «e» ante «INCIBE-CERT» se correspondían con las reglas ortográficas del español y que las tablas seguían renderizando correctamente.

* **Evidencia:** [uso-01.png](ia/uso-01.png)

* **Usos relacionados:** Ninguno

## Uso 02

* **Quién:** Sergio Rodríguez López

* **Fecha:** 09-11-2026, v0.2

* **Herramienta y modelo, si consta:** Gemini

* **Para qué:** Consulta orientativa de legislación aplicable y corrección ortográfica

* **Hito y apartado del trabajo:** PF-P1 (`informe.md` — Apartado 3: Alcance, límites y evaluación legal/OPSEC — y `seguimiento.md`)

* **Fuentes o texto propio utilizados como entrada:** Consulta general sobre normativa de protección de datos y medios de pago en España/UE y borrador propio de los apartados de `PF-P1`.

* **Prompt, copiado tal cual:**

```text
1. De forma general y orientativa, ¿qué artículos o normativas en España y la Unión Europea regulan la obligación de notificar brechas de datos personales a la autoridad de control y a los interesados, así como el estándar aplicable a datos de tarjetas de pago?
2. Revisa si hay alguna falta de ortografía o errata en mi borrador de informe.md y seguimiento.md sin reescribir el texto, solo indícame las palabras que tengan errores ortográficos.
```

* **Respuesta completa:**

```text
1. Orientación normativa general (España y Unión Europea):
- Reglamento General de Protección de Datos (RGPD - Reglamento UE 2016/679):
  * Artículo 33: Notificación de una violación de la seguridad de los datos personales a la autoridad de control (en España, la AEPD) en un plazo máximo de 72 horas.
  * Artículo 34: Comunicación de una violación de la seguridad de los datos personales al interesado cuando sea probable que entrañe un alto riesgo para sus derechos y libertades.
  * Artículo 5.1.c: Principio de minimización de datos.
- Ley Orgánica 3/2018 (LOPDGDD): Adapta el RGPD al ordenamiento jurídico español y regula el régimen sancionador y las actuaciones ante la Agencia Española de Protección de Datos (AEPD).
- Estándar del sector de medios de pago: PCI-DSS (Payment Card Industry Data Security Standard), estándar técnico y operativo aplicable a entidades que procesan, almacenan o transmiten datos de tarjetas bancarias (PAN y CVV/CVC).

2. Revisión ortográfica de los borradores (informe.md y seguimiento.md):
- En informe.md (Apartado 3, Datos, seguridad y condiciones de parada): "numeracion" debe llevar tilde -> "numeración".
- En informe.md (Apartado 4, Contexto documentado): "caracteriza" está bien escrito, pero en el segundo punto aparece "incluido" sin concordancia o falta tilde en "tambien" -> debe ser "también".
- En informe.md (Apartado 6, tabla H-03): falta tilde en "sustitucion" -> "sustitución".
- En seguimiento.md (Tabla Correcciones y decisiones): falta tilde en "incorporacion" -> "incorporación".
No se observan otros errores ortográficos ni de sintaxis Markdown.
```

* **Qué hice con la respuesta:** Utilicé la referencia general a los principios de minimización de datos del RGPD/LOPDGDD y al estándar PCI-DSS para encuadrar la exclusión de datos personales y bancarios en el apartado 3 de `informe.md`, y corregí manualmente las tildes señaladas en `informe.md` y `seguimiento.md`.

* **Qué comprobé y con qué fuentes originales u oficiales:** Comprobé la referencia al RGPD (Reglamento UE 2016/679, arts. 5, 33 y 34) y a la LOPDGDD (Ley Orgánica 3/2018) en el Boletín Oficial del Estado (BOE) y el Diario Oficial de la Unión Europea (DOUE), verificando que aplican a la protección de datos personales en España.

* **Evidencia:** [uso-02.png](ia/uso-02.png)

* **Usos relacionados:** Uso 01 (registro acumulado del proyecto)

La IA no se cita como fuente de un hecho ni de una norma. La investigación, el análisis, las decisiones y la redacción son de elaboración propia. El incumplimiento de las [condiciones de IA](../../../../proyecto-final/README.md#uso-de-inteligencia-artificial), incluido el uso no declarado o la falta del registro y de sus evidencias obligatorias, supondrá **0 sobre 10 en el proyecto final**.
