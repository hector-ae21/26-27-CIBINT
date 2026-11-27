# Registro de uso de inteligencia artificial · Proyecto final

**Estudiante: Cayetano Castillo Ruiz**  
**Título del proyecto: Análisis de las vulnerabilidades PHP2Shell: ciclo de vida, evasión de parches y revisión de las evidencias sobre la implicación de la IA.**  
**Hito y fecha: P1 09/11/2026**

## Declaración

- [Con uso de IA: «He utilizado inteligencia artificial únicamente para las tareas permitidas, según los usos y evidencias que se detallan a continuación».]

## Uso 01

- **Quién:** Cayetano Castillo
- **Fecha:** 09/11/2026
- **Herramienta y modelo, si consta:** Gemini Pro 3.1
- **Para qué:** Para evitar caer en sesgos de confirmación y saber que falta por comprobar
- **Hito y apartado del trabajo:** P1 Contexto y Conología
- **Fuentes o texto propio utilizados como entrada:** vulnerabilidades PHP2Shell (CVE-2026-109618 y CVE-2026-109619). 
Sabiendo que los parches oficiales de PHP salieron el 21 de octubre
- **Prompt, copiado tal cual:**

```text
Estoy redactando el apartado de 'Contexto y cronología' de mi informe de ciberinteligencia sobre las vulnerabilidades PHP2Shell (CVE-2026-109618 y CVE-2026-109619). La plantilla me pide separar estrictamente los 'hechos conocidos' de las 'afirmaciones pendientes de verificar'. Sabiendo que los parches oficiales de PHP salieron el 21 de octubre y que algunos blogs de Threat Intel afirman que se usó IA para evadir estos parches, ¿cómo me sugieres redactar las entradas de la tabla para no caer en sesgos de confirmación y dejar claro qué falta por comprobar?
```

- **Respuesta completa:**

```text
Para estructurar el apartado de «Contexto y cronología» evitando el sesgo de confirmación, debes aplicar un enfoque estrictamente descriptivo, cumpliendo con la exigencia de atribuir cada afirmación a su emisor. La clave está en registrar la publicación de la vulnerabilidad como un hecho técnico demostrable y la participación de la IA como una declaración atribuida a un tercero que tu investigación debe auditar.A continuación tienes una propuesta de redacción para las entradas de tu tabla:Fecha y zona horaria del hechoPublicación u observaciónHecho o afirmación atribuidaFuenteLimitación21/10/2026 (Global)Publicación de parchesHecho: El equipo de desarrollo publica actualizaciones de seguridad corrigiendo las vulnerabilidades PHP2Shell (CVE-2026-109618 y CVE-2026-109619).PHP Group (Aviso Oficial)Confirma la existencia del fallo y su corrección técnica, pero no documenta cómo fue descubierto originalmente ni menciona explotación activa.[Fecha exacta] (Global)Reporte de Threat IntelAfirmación atribuida: Diversos informes técnicos sugieren que se ha descubierto una evasión del parche en tiempo récord (CVE-2026-115560), atribuyendo esta velocidad al uso de herramientas de Inteligencia Artificial.[Nombre del Blog / Empresa de Threat Intel]Declaración de terceros pendiente de verificación; requiere auditar si el reporte aporta evidencias técnicas (TTPs, logs, trazas) que demuestren el uso de IA, o si es una suposición comercial.Razonamiento analítico aplicado:Uso de verbos atributivos: Al utilizar fórmulas como «[La fuente] sugiere» o «[La fuente] afirma», creas un cortafuegos analítico. El informe no asume que la IA evadió el parche, sino que constata que un actor específico sostiene esa hipótesis.Función de la limitación: La columna de «Limitación» actúa como tu justificación metodológica. Al declarar explícitamente que el aviso oficial carece de contexto de explotación y que el blog de inteligencia requiere verificación de evidencias, conectas directamente este contexto con tus Preguntas de Inteligencia (PI), demostrando por qué necesitas seguir investigando.
```

- **Qué hice con la respuesta:** Revise la respuesta detalladamente para incluir en el informe el contenido necesario teniendo como referencia una tabla ya creada 
- **Qué comprobé y con qué fuentes originales u oficiales:** 
- **Evidencia:** [Gemini](https://share.gemini.google/1QN3OfGVWJQu)
- **Usos relacionados:** 

## Uso 02

- **Quién:** Cayetano Castillo
- **Fecha:** 09/11/2026
- **Herramienta y modelo, si consta:** Gemini Pro 3.1
- **Para qué:** Pedirle a la ia una recomendación de medidas OPSEC para mantener el trabajo como una recolección pasiva y no entrar en interacciónes con atacantes.
- **Hito y apartado del trabajo:** P1 Evaluación Legal
- **Fuentes o texto propio utilizados como entrada:** medidas de OPSEC
- **Prompt, copiado tal cual:**

```text
Vale esta muy bien, ahora necesito que me ayudes a redactar la 'Evaluación legal, OPSEC y condiciones de parada'. Mi investigación es mediante OSINT sobre vulnerabilidades públicas de PHP y voy a buscar repositorios con pruebas de concepto (PoCs) en GitHub y reportes de seguridad. ¿Qué medidas de OPSEC (a nivel de red y navegación) y qué 'condiciones de parada' concretas me recomiendas documentar para garantizar que mi trabajo se mantiene como recolección pasiva y no roza la explotación activa ni la interacción con atacantes?
```

- **Respuesta completa:**

```text
Para redactar el apartado de «Datos, seguridad y condiciones de parada» de tu informe, debes estructurar el contenido detallando las precauciones legales, la protección de tu entorno y los límites estrictos de la investigación.

Aquí tienes la redacción recomendada basada en los requisitos de tu asignatura:

**Evaluación Legal y Manejo de Datos**
La investigación se limita estrictamente a la recolección de Inteligencia de Fuentes Abiertas (OSINT) de forma pasiva. La aprobación académica no concede permiso para interactuar con sistemas ajenos ni realizar escaneos activos. Únicamente se almacenarán fragmentos de código neutralizados, *hashes* y direcciones IP ofuscadas. No se recopilarán datos de carácter personal (PII) de las víctimas y cualquier evidencia se conservará en un entorno local cifrado.

**Medidas de OPSEC (Navegación y Red)**

* **Aislamiento de red:** Las consultas a repositorios de *exploits* y foros técnicos se realizarán a través de una conexión VPN sin registros (no-logs) para enmascarar la IP de origen y evitar la correlación de consultas (*leakage* de intenciones).
* **Entorno de análisis seguro:** Las Pruebas de Concepto (PoCs) alojadas en GitHub se consultarán y descargarán exclusivamente dentro de una Máquina Virtual (VM) aislada y sin conexión a la red anfitriona. Los repositorios de PoCs suelen estar infectados con *malware* secundario o *backdoors* dirigidos a investigadores.
* **Separación de identidades:** No se utilizarán perfiles personales ni correos institucionales de la universidad para acceder a repositorios o plataformas de *Threat Intel*. La navegación se realizará sin iniciar sesión o mediante identidades de investigación (*sockpuppets*) dedicadas.



**Condiciones de parada**
El trabajo de recolección se detendrá inmediatamente y se consultará al profesorado utilizando el canal privado de la asignatura si ocurre cualquiera de los siguientes escenarios:

* **Hallazgo de Zero-Days:** Se localiza código de explotación funcional que no ha sido divulgado públicamente o parcheado, superando la barrera de vulnerabilidad conocida.
* **Riesgo de interacción:** El acceso a un reporte, repositorio o foro técnico exige la interacción directa con presuntos atacantes (por ejemplo, necesidad de responder a un hilo para desbloquear un enlace o unirse a un canal de Telegram privado).
* **Datos sensibles:** Aparece contenido sensible inesperado o bases de datos expuestas con información personal o corporativa confidencial de las víctimas de los ataques.


* **Infraestructura activa:** Se identifica infraestructura de Comando y Control (C2) activa cuya evaluación requeriría el envío de paquetes directos desde la máquina de análisis.
```

- **Qué hice con la respuesta:** Revise la redacción dada para entender como podia enfocar mi propia redacción sobre la Evaluación legal y el manejo de datos. También revise las medidas OPSEC y condiciones de paradas que me brindó.
- **Qué comprobé y con qué fuentes originales u oficiales:** Las medidas de OPSEC documentadas (aislamiento de red, entorno seguro y separación de identidades) se comprobaron y justificaron mediante el cruce de las directrices metodológicas de la asignatura con fuentes oficiales y mejores prácticas de la industria en ciberinteligencia.

**Aislamiento de red (VPN sin registros):** Se verificó la necesidad de enmascarar la IP de origen para evitar el leakage de intenciones consultando las guías de recolección OSINT pasiva. El uso de conexiones no correlacionables garantiza que la investigación no alerte a los administradores de los foros o repositorios, cumpliendo con la prohibición académica de realizar escaneos activos.

**Entorno de análisis seguro (Máquina Virtual aislada):** La comprobación de esta medida se basó en reportes oficiales de empresas de Threat Intel y alertas de agencias gubernamentales (como CISA) que documentan campañas recientes donde actores de amenazas publican Pruebas de Concepto (PoCs) falsas en GitHub. Estas PoCs suelen contener malware secundario o backdoors dirigidos específicamente a investigadores de seguridad, haciendo indispensable el uso de una VM desconectada de la red anfitriona para neutralizar el riesgo.

**Separación de identidades (Sockpuppets):** Se contrastó con los manuales de seguridad operativa (OPSEC) para analistas, los cuales dictaminan que el uso de correos institucionales o personales en plataformas de inteligencia o foros técnicos expone la identidad real y la afiliación del investigador. Se determinó que la navegación sin inicio de sesión o mediante identidades sintéticas (sockpuppets) es la única vía para mantener la pasividad y el anonimato exigidos en las condiciones de alcance.
- **Evidencia:** [Gemini](https://share.gemini.google/2EF0a2VSPn47)
- **Usos relacionados:** 

## Uso 03

- **Quién:** Cayetano Castillo
- **Fecha:** 27/11/2026
- **Herramienta y modelo, si consta:** Gemini Pro 3.1
- **Para qué:**Revisar y refinar los criterios de redacción de la tabla de contexto y cronología tras las correcciones de P1, asegurando la separación de fuentes secundarias y la trazabilidad de afirmaciones sobre IA.
- **Hito y apartado del trabajo:** P1 (v0.2) · Apartado 4 (Contexto y cronología) y Apartado 5 (Fuentes y método)
- **Fuentes o texto propio utilizados como entrada:** Correcciones recibidas en P1 (23/11/2026) y datos iniciales de CVE-2026-109618 y CVE-2026-109619.
- **Prompt, copiado tal cual:**
Estoy redactando el apartado de 'Contexto y cronología' de mi informe de ciberinteligencia sobre las vulnerabilidades PHP2Shell (CVE-2026-109618 y CVE-2026-109619). La plantilla me pide separar estrictamente los 'hechos conocidos' de las 'afirmaciones pendientes de verificar'. Sabiendo que los parches oficiales de PHP salieron el 21 de octubre y que algunos blogs de Threat Intel afirman que se usó IA para evadir estos parches, ¿cómo me sugieres redactar las entradas de la tabla para no caer en sesgos de confirmación y dejar claro qué falta por comprobar?
- **Respuesta completa:**
Para redactar el apartado de **Contexto y cronología** sin caer en sesgos de confirmación, aplica un criterio estrictamente descriptivo: registra la publicación oficial de los parches como un **hecho verificable** y cualquier mención al uso de IA como una **afirmación atribuida** a un emisor concreto que tu investigación debe auditar.

La siguiente propuesta respeta las columnas exactas de la plantilla oficial del informe:

| Fecha y zona horaria del hecho | Publicación u observación | Hecho o afirmación atribuida | Fuente | Limitación |
| --- | --- | --- | --- | --- |
| 21/10/2026 (Global) | Publicación de parches | **Hecho:** El equipo de desarrollo publica actualizaciones de seguridad para corregir las vulnerabilidades PHP2Shell (CVE-2026-109618 y CVE-2026-109619). | PHP Group (Aviso oficial) | Confirma la existencia técnica de los fallos y su corrección, pero no documenta explotación activa ni detalla las herramientas empleadas para su descubrimiento. |
| [Fecha exacta] (Global) | Reporte de *Threat Intel* | **Afirmación atribuida:** El informe sugiere que se descubrió una evasión parcial del parche (CVE-2026-115560) en tiempo récord y atribuye esa velocidad al uso de herramientas de Inteligencia Artificial. | [Nombre del blog o proveedor, p. ej. Snyk / Sygnia] | Declaración de terceros pendiente de verificación; falta comprobar si aporta evidencias técnicas propias (trazas, metodología reproducible) o si repite afirmaciones de otra fuente sin contraste independiente. |

Criterios para evitar el sesgo de confirmación:
- Etiquetado explícito en la redacción: Iniciar cada celda con Hecho: o Afirmación atribuida: impide que el lector —o el propio análisis posterior— trate una hipótesis como un dato confirmado.
- Verbos atributivos y neutros: Emplear fórmulas como «el reporte afirma», «la fuente sugiere» o «atribuye» en lugar de «la IA evadió el parche» mantiene la distancia analítica y atribuye cada declaración a su emisor.
- Separación de fuentes: Si varios blogs de Threat Intelligence sostienen la misma idea sobre la IA, regístralos en filas separadas (por organización y fecha real) para comprobar después si aportan pruebas independientes o si todos dependen de un mismo origen.
- Uso estratégico de la columna «Limitación»: Úsala para declarar exactamente qué no demuestra esa entrada y qué queda por comprobar (por ejemplo, si existe evidencia documental del uso de IA o si se trata de una estimación comercial), conectando directamente la cronología con tus Preguntas de Inteligencia.

- **Qué hice con la respuesta:** Apliqué el criterio de separar en fuentes y filas independientes a Snyk (F-04) y Sygnia (F-05) y reforzé la columna de limitaciones para señalar qué queda pendiente de auditar en P2 respecto a dependencias entre fuentes.
- **Qué comprobé y con qué fuentes originales u oficiales:** Comprobé directamente en navegador las URLs y fechas reales de PHP Group (F-01), CISA (F-02), NVD (F-03), Snyk (F-04) y Sygnia (F-05), registrando cada acceso en P1/registros/fuentes.csv y P1/registros/bitacora.csv.
- **Evidencia:** [Gemini](https://share.gemini.google/fudQ5ZfMIayL)
- **Usos relacionados:** Uso 01

## Uso 04

- **Quién:** Cayetano Castillo
- **Fecha:** 27/11/2026
- **Herramienta y modelo, si consta:** Gemini Pro 3.1
- **Para qué:**Corregir la redacción de OPSEC y del protocolo de condición de parada en v0.2 para excluir la descarga/apertura de código PoC y asegurar que al detenerse no se captura ni descarga nada.
- **Hito y apartado del trabajo:** P1 (v0.2) · Apartado 3 (Alcance, límites y condiciones de trabajo)
- **Fuentes o texto propio utilizados como entrada:** Observaciones 4 y 5 de la resolución del profesorado del 23/11/2026 sobre condición de parada y repositorios de PoC.
- **Prompt, copiado tal cual:**
Vale esta muy bien, ahora necesito que me ayudes a redactar la 'Evaluación legal, OPSEC y condiciones de parada'. Mi investigación es mediante OSINT sobre vulnerabilidades públicas de PHP y voy a buscar repositorios con pruebas de concepto (PoCs) en GitHub y reportes de seguridad. ¿Qué medidas de OPSEC (a nivel de red y navegación) y qué 'condiciones de parada' concretas me recomiendas documentar para garantizar que mi trabajo se mantiene como recolección pasiva y no roza la explotación activa ni la interacción con atacantes?
- **Respuesta completa:**
Para redactar el subapartado Datos, seguridad y condiciones de parada manteniendo la investigación estrictamente dentro de la recolección pasiva, conviene establecer primero un límite clave respecto a GitHub: no descargues, abras ni ejecutes código de explotación (PoC), ya que la ingeniería inversa y la manipulación de exploits quedan fuera del alcance pasivo y te exponen a malware secundario. Si necesitas referenciar la existencia de pruebas de concepto públicas, limítate a documentar lo que reportan sobre ellas las fuentes secundarias de Threat Intelligence.

La siguiente propuesta está estructurada para encajar directamente en el Apartado 3 de la plantilla del informe:

Evaluación legal y manejo de datos
Alcance pasivo: La recolección se limita exclusivamente a fuentes abiertas y públicas (OSINT) sobre vulnerabilidades ya divulgadas; la aprobación académica no autoriza el acceso a sistemas ajenos, escaneos activos ni pruebas contra infraestructura de terceros.

Exclusión de código de explotación: Quedan expresamente excluidas la descarga, apertura, ejecución o ingeniería inversa de repositorios con código PoC.

Minimización de datos: No se recopilan datos personales (PII) ni telemetría privada de organizaciones víctimas. Solo se conservan metadatos de avisos oficiales, identificadores CVE, referencias bibliográficas e indicadores neutralizados en un entorno local controlado.

Medidas de OPSEC (red y navegación)
Privacidad de red y DNS: Realizar todas las consultas mediante una conexión cifrada (VPN sin registros) y resolución DNS cifrada (DoH) para evitar la correlación de búsquedas y la fuga de intenciones (leakage).

Separación de identidades: Utilizar un perfil de navegador dedicado exclusivamente a la práctica, sin iniciar sesión en cuentas personales ni correos institucionales de la universidad, evitando dejar rastro de afiliación académica.

Navegación estrictamente pasiva: Consultar las fuentes de forma manual y moderada, evitando scripts de raspado agresivo (scraping) que puedan alertar a los administradores o activar bloqueos.

Neutralización de artefactos (defanging): Ofuscar cualquier enlace o indicador técnico potencialmente malicioso (por ejemplo, hxxps:// o 192[.]0[.]2[.]1) antes de incorporarlo a los registros o al informe para impedir accesos accidentales.

Condiciones de parada y procedimiento de consulta
La recolección se detendrá de forma inmediata si se presenta cualquiera de estos escenarios:

Código no divulgado (Zero-Day): Aparición de un exploit funcional o vulnerabilidad crítica que no haya sido publicada oficialmente ni parcheada.

Riesgo de interacción con actores: Cualquier fuente, foro o repositorio que exija interactuar directa o indirectamente con presuntos atacantes (registrarse en canales cerrados, responder a hilos para desbloquear enlaces o contactar con autores).

Contenido sensible inesperado: Hallazgo de bases de datos expuestas, credenciales filtradas o información personal/corporativa confidencial de víctimas reales.

Infraestructura activa (C2): Identificación de servidores de Comando y Control activos o infraestructura maliciosa cuya comprobación requeriría tráfico directo hacia sistemas de terceros.

Protocolo de actuación al detenerse: Ante cualquiera de los supuestos anteriores no se captura pantalla, ni se copia ni se descarga ningún contenido. Se cierra inmediatamente la consulta, se anota únicamente la fecha, hora, búsqueda exacta y categoría del incidente en registros/bitacora.csv, y se consulta al profesorado por el canal privado de la asignatura antes de reanudar el trabajo.

- **Qué hice con la respuesta:** Adapté e incorporé la exclusión total de código PoC, las medidas OPSEC pasivas y el protocolo corregido de parada (sin captura ni descarga, registrando solo la categoría en bitacora.csv) en el Apartado 3 de P1/informe.md (v0.2) y en TEMA/propuesta.md.
- **Qué comprobé y con qué fuentes originales u oficiales:** Comprobé la adecuación punto por punto frente a las correcciones 4 y 5 de la resolución del profesorado del 23/11/2026 y las condiciones generales del enunciado del proyecto final (exclusión de acceso a sistemas, ingeniería inversa y conservación de material sensible no autorizado).
- **Evidencia:** [Gemini](https://share.gemini.google/fudQ5ZfMIayL)
- **Usos relacionados:** Uso 02

