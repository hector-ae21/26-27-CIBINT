# Registro de uso de inteligencia artificial · A03

## Uso 1

- **Herramienta y modelo:** Claude Code, Claude Opus 5.5
- **Para qué:** Crear la estructura de carpetas de la actividad y entender cómo se usa cada herramienta del Tema 3.
- **Apartado del informe:** 3. Plan de obtención
- **Prompt, copiado tal cual:**

  ```text
  Necesito que me ayudes a realizar la actividad A03 en mi directorio, dame la estructura de archivos que debe llevar la actividad. El objetivo es el mismo que el de mi investigación del proyecto final: HSE y el hackeo de ransomware Conti en 2021.

  Sigue las reglas marcadas en el README con las políticas de inteligencia artifical, siempre sigue las reglas.

  Igualmente lo que te pediré es que me ayudes con la documentación que tienes en @documentation\contenidos\03-osint-personas-y-organizaciones

  Más que nada para saber el uso de herramientas y yo redactar el trabajo.
  ```

- **Qué hice con la respuesta:** Usé la estructura de carpetas. Elegí yo las herramientas y las consultas del plan. Descarté Intelligence X y Serus por el riesgo de dar con material filtrado. Usé TinEye como herramienta opcional. El informe lo redacté yo.
- **Evidencia:** `ia/uso-01.txt`

## Uso 2

- **Herramienta y modelo:** Claude Code, Claude Opus 5.5
- **Para qué:** Saber cómo montar a mano el grafo en Maltego y resolver dudas sobre qué entidades incluir.
- **Apartado del informe:** 4.1 (OBT-15), 4.2 Maltego y 5.3 Grafo de relaciones
- **Prompt, copiado tal cual:**

  ```text
  Ayúdame a realizar en grafo de maltego de la actividad 03 en @C:\Users\hecto\Documents\Eirik\Personal\universidad\cibint\fork-entregas\entregas\roseteEirik\A03\README.md
  ```

  ```text
  Los proveedores careerhub y hepctest y alamy son necesarios?
  ```

  ```text
  Los proovedores que relacion mantienen con la entidad hse
  ```

- **Qué hice con la respuesta:** Monté el grafo a mano en Maltego, sin transformaciones. Quité alamy.com porque no responde a ninguna pregunta. Junté los dos proveedores en una sola entidad, «proveedores sin identificar». La enlacé al HSE como relación declarada, porque lo dicen sus políticas de privacidad. Revisé cada enlace con mis filas OBT. El grafo final tiene 27 entidades y 26 enlaces.
- **Evidencia:** `ia/uso-02.txt`
