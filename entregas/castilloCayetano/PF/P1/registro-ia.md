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
