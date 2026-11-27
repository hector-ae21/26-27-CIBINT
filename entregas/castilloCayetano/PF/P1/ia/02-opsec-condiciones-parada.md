# Exportación IA 02 · Borrador inicial de evaluación legal, OPSEC y condiciones de parada

- **Herramienta:** Gemini
- **Fecha y hora:** 2026-11-09 17:11:00 (Europe/Madrid)
- **Relación con `registro-ia.md`:** Entrada 02

## Prompt del estudiante

> Vale esta muy bien, ahora necesito que me ayudes a redactar la 'Evaluación legal, OPSEC y condiciones de parada'. Mi investigación es mediante OSINT sobre vulnerabilidades públicas de PHP y voy a buscar repositorios con pruebas de concepto (PoCs) en GitHub y reportes de seguridad. ¿Qué medidas de OPSEC (a nivel de red y navegación) y qué 'condiciones de parada' concretas me recomiendas documentar para garantizar que mi trabajo se mantiene como recolección pasiva y no roza la explotación activa ni la interacción con atacantes?

## Respuesta completa del modelo

Para redactar el subapartado Datos, seguridad y condiciones de parada manteniendo la investigación estrictamente dentro de la recolección pasiva, conviene establecer primero un límite clave respecto a GitHub: no descargues, abras ni ejecutes código de explotación (PoC), ya que la ingeniería inversa y la manipulación de exploits quedan fuera del alcance pasivo y te exponen a malware secundario. Si necesitas referenciar la existencia de pruebas de concepto públicas, limítate a documentar lo que reportan sobre ellas las fuentes secundarias de Threat Intelligence.

La siguiente propuesta está estructurada para encajar directamente en el Apartado 3 de la plantilla del informe:

**Evaluación legal y manejo de datos**
**Alcance pasivo:** La recolección se limita exclusivamente a fuentes abiertas y públicas (OSINT) sobre vulnerabilidades ya divulgadas; la aprobación académica no autoriza el acceso a sistemas ajenos, escaneos activos ni pruebas contra infraestructura de terceros.

**Exclusión de código de explotación:** Quedan expresamente excluidas la descarga, apertura, ejecución o ingeniería inversa de repositorios con código PoC.

**Minimización de datos:** No se recopilan datos personales (PII) ni telemetría privada de organizaciones víctimas. Solo se conservan metadatos de avisos oficiales, identificadores CVE, referencias bibliográficas e indicadores neutralizados en un entorno local controlado.

**Medidas de OPSEC (red y navegación)**
**Privacidad de red y DNS:** Realizar todas las consultas mediante una conexión cifrada (VPN sin registros) y resolución DNS cifrada (DoH) para evitar la correlación de búsquedas y la fuga de intenciones (leakage).

**Separación de identidades:** Utilizar un perfil de navegador dedicado exclusivamente a la práctica, sin iniciar sesión en cuentas personales ni correos institucionales de la universidad, evitando dejar rastro de afiliación académica.

**Navegación estrictamente pasiva:** Consultar las fuentes de forma manual y moderada, evitando scripts de raspado agresivo (scraping) que puedan alertar a los administradores o activar bloqueos.

**Neutralización de artefactos (defanging):** Ofuscar cualquier enlace o indicador técnico potencialmente malicioso (por ejemplo, hxxps:// o 192[.]0[.]2[.]1) antes de incorporarlo a los registros o al informe para impedir accesos accidentales.

**Condiciones de parada y procedimiento de consulta**
La recolección se detendrá de forma inmediata si se presenta cualquiera de estos escenarios:

**Código no divulgado (Zero-Day):** Aparición de un exploit funcional o vulnerabilidad crítica que no haya sido publicada oficialmente ni parcheada.

**Riesgo de interacción con actores:** Cualquier fuente, foro o repositorio que exija interactuar directa o indirectamente con presuntos atacantes (registrarse en canales cerrados, responder a hilos para desbloquear enlaces o contactar con autores).

**Contenido sensible inesperado:** Hallazgo de bases de datos expuestas, credenciales filtradas o información personal/corporativa confidencial de víctimas reales.

**Infraestructura activa (C2):** Identificación de servidores de Comando y Control activos o infraestructura maliciosa cuya comprobación requeriría tráfico directo hacia sistemas de terceros.

Protocolo de actuación al detenerse: Ante cualquiera de los supuestos anteriores no se captura pantalla, ni se copia ni se descarga ningún contenido. Se cierra inmediatamente la consulta, se anota únicamente la fecha, hora, búsqueda exacta y categoría del incidente en registros/bitacora.csv, y se consulta al profesorado por el canal privado de la asignatura antes de reanudar el trabajo.

## Revisión y corrección posterior por parte del estudiante

Tras la revisión del profesor del 23/11/2026 (`v0.2`), se descartó la recomendación de descargar o consultar PoCs en GitHub incluso dentro de una VM (al quedar excluida la apertura o descarga de código de explotación) y se corrigió el protocolo de condición de parada para garantizar que, al detenerse, no se captura ni descarga ningún contenido y solo se anota la categoría en `bitacora.csv` antes de consultar.