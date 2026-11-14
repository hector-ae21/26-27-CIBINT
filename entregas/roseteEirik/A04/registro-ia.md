# Registro de uso de inteligencia artificial · A04

## Uso 1

- **Herramienta y modelo:** Claude Code, Claude Opus 5.5
- **Para qué:** Crear la estructura de carpetas de la actividad y entender cómo se usan las herramientas del Tema 4.
- **Apartado del informe:** 3. Plan de obtención
- **Prompt, copiado tal cual:**

  ```text
  Necesito que me ayudes a realizar la actividad A04 en mi directorio, dame la estructura de archivos que debe llevar la actividad. El objetivo es el mismo que el de mi investigación del proyecto final: HSE y el hackeo de ransomware Conti en 2021. Dicho avance está en @cibint/entregas/roseteEirik/PF

  Sigue las reglas marcadas en el README con las políticas de inteligencia artifical, siempre sigue las reglas.

  Igualmente lo que te pediré es que me ayudes con la documentación de todos los temas en @documentation/contenidos y la documentacion especifica del tema que tienes en @documentation/contenidos/04-osint-tecnico-infraestructura-y-exposicion

  Más que nada para saber el uso de herramientas y yo redactar el trabajo.
  ```

- **Qué hice con la respuesta:** Usé la estructura de carpetas. Usé la guía de herramientas solo como consulta y no la copié en el informe. Elegí yo las consultas de Shodan dentro de las reglas reforzadas: hostname:, ssl: y ssl.cert.subject.cn:. Usé crt.sh como contraste y no hice consultas DNS. Cambié FOCA por Maltego por indicación del docente.
- **Evidencia:** `ia/uso-01.txt`

## Uso 2

- **Herramienta y modelo:** Claude Code, Claude Opus 5.5
- **Para qué:** Resolver dudas de git, tapar nombres de persona en una captura y saber cómo montar el grafo final en Maltego.
- **Apartado del informe:** 5.4 Grafo final y 8. Índice de evidencias (EV-07 y EV-08)
- **Prompt, copiado tal cual:**

  ```text
  Vale, ya hice la rama desde main y ahora tengo la rama actual. Copie a03 finalizada para tenerlo aqui y poder trabajar aqui mismo sin hacer git checkout
  ```

  ```text
  Subi los nuevos grafos de maltego, por favor tapa los nombres de las personas para evitar que se filtren datos sensibles
  ```

  ```text
  explicame como hacer el ultimo grafo con sus relaciones
  ```

  ```text
  Ya está
  ```

  ```text
  La repeti para que se viera toda
  ```

- **Qué hice con la respuesta:** No añadí la carpeta de la A03 a la rama de la A04. La IA tapó los nombres de persona en EV-07. Monté a mano el grafo final sobre el de la A03, con las 8 entidades nuevas y sus enlaces. Puse los autores como USR-01 a USR-04, sin nombres reales. Repetí la exportación de EV-08 para que el grafo se viera entero.
- **Evidencia:** `ia/uso-02.txt`
