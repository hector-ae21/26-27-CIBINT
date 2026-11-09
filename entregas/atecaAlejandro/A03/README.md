# A03 · Huella pública

## Estudiante

- Nombre: Alejandro Ateca Trueba
- Carpeta personal: `entregas/atecaAlejandro/A03/`
- Modalidad: Modalidad A · Organización
- Objetivo: S.M.E. Instituto Nacional de Ciberseguridad de España M.P., S.A. (INCIBE)
- ¿Es el objetivo de tu proyecto final?: Sí
- Punto de partida (dominio principal o identificadores propios): `incibe.es`
- Periodo de obtención, con zona horaria: 2026-10-29 19:00 a 2026-10-29 22:05 (CET / UTC+1)

---

## 1. Resumen ejecutivo

Este informe analiza desde fuentes abiertas la huella pública de **S.M.E. Instituto Nacional de Ciberseguridad de España M.P., S.A. (INCIBE)** para identificar exposiciones aprovechables en campañas de suplantación o ingeniería social. La entidad opera bajo razón social mercantil estatal inscrita en León (anteriormente denominada INTECO) y articula su actividad pública mediante el dominio `incibe.es` y los portales temáticos `osi.es` e `is4k.es` `(OBT-01, OBT-05, OBT-08)`. Esta multiplicidad de marcas y canales oficiales amplía la superficie susceptible de imitación mediante dominios parecidos `(OBT-01, OBT-05)`. Asimismo, la publicación de numerosos documentos PDF técnicos y de licitación expone relaciones con adjudicatarios y posibles metadatos internos (pendientes de verificar en la A04) `(OBT-02, OBT-03)`. Se recomienda higienizar metadatos antes de publicar y monitorizar dominios similares.

| Pregunta | Respuesta breve | Confianza | Referencias |
|---|---|---|---|
| **PI-01 (Corporativa)** | Opera como *S.M.E. Instituto Nacional de Ciberseguridad de España M.P., S.A.* (NIF A24512980), inscrita en el Registro Mercantil de León, habiendo cambiado su denominación desde INTECO S.A. en 2014. | Alta | `(OBT-01, OBT-07, OBT-08)` |
| **PI-02 (De canales)** | Presenta como propios los dominios `incibe.es`, `osi.es` e `is4k.es`, el teléfono 017 y perfiles oficiales enlazados en su web (X, LinkedIn, YouTube, Instagram y Facebook), evolucionando desde 2016 hacia la centralización en el 017. | Alta | `(OBT-01, OBT-04, OBT-05, OBT-06)` |
| **PI-03 (De relaciones)** | Sus marcas y portales convergen declarativamente en la misma sociedad mercantil y mantienen vínculos documentados con adjudicatarios en pliegos públicos, quedando pendiente verificar en A04 la infraestructura compartida y vigencia contractual. | Media | `(OBT-01, OBT-03, OBT-05, OBT-10)` |

---

## 2. Encargo

### 2.1 Objetivo elegido

Se ha elegido la **Modalidad A · Organización**, seleccionando al **Instituto Nacional de Ciberseguridad de España (INCIBE)** por tres motivos:
1. Coincide con la organización objeto de estudio en el proyecto final de la asignatura, lo que permite dar continuidad directa al análisis en la actividad A04.
2. Cumple todos los requisitos del apartado 3.1 del enunciado: es una organización real con actividad pública en España y Europa (sociedad mercantil estatal de referencia en ciberseguridad), no es una persona física, no es un centro educativo de menores y no figura entre las organizaciones de los casos de A01 ni A02. Asimismo, al pertenecer a un sector sensible, el estudio se limita estrictamente a la organización y sus canales corporativos públicos, sin investigar a empleados ni usuarios.
3. Dispone de información societaria publicada en el BORME y de un dominio web propio (`incibe.es`) con documentos PDF publicados necesarios para la A04.

**Comprobación de material suficiente para A03 y A04:**
El **2026-10-29 a las 16:40 CET** (antes del cierre del presente plan a las 16:50 CET), se realizó una comprobación preliminar de viabilidad sobre `incibe.es`, verificando que la entidad publica su identificación mercantil en su aviso legal y que existen centenares de documentos PDF indexados bajo su dominio principal, lo cual se registra y documenta formalmente al inicio de la fase de obtención en las filas `(OBT-01, OBT-02)`.

### 2.2 Requerimiento

| Componente | Contenido |
|---|---|
| **Destinatario** | Responsable de Seguridad de la Información (CISO) de INCIBE. |
| **Decisión** | Decidir qué canales públicos, dominios asociados y procedimientos de publicación documental deben someterse a controles adicionales de verificación, monitorización o higienización para reducir el riesgo de suplantación (*spoofing*) y fraude dirigido. |
| **Objeto** | La huella pública corporativa, de canales oficiales y de relaciones institucionales o contractuales de INCIBE observable pasivamente en fuentes abiertas. |
| **Horizonte** | Corto plazo: informe cerrado y entregado antes del 30 de octubre de 2026 a las 23:59 CET, con obtención ejecutada el 29 de octubre de 2026. |
| **Alcance** | Dominio corporativo `incibe.es`, portales temáticos enlazados (`osi.es`, `is4k.es`), actos societarios en el BORME y OpenCorporates, capturas históricas en Wayback Machine e índices públicos en Intelligence X. |
| **Exclusiones** | Queda excluida cualquier investigación sobre personas físicas (empleados, cargos, firmantes de pliegos o usuarios), homónimos, el escaneo activo de redes o servicios, el acceso a contenidos de filtraciones y cualquier contacto con los canales de la entidad. |
| **Producto** | Informe de huella pública en `README.md`, respaldado por el registro de obtención (`OBT`), grafo exportado de Maltego e índice de evidencias recortadas y anonimizadas (`EV-01.png` a `EV-08.png`). |

**Requerimiento en una frase:** Analizar antes del 30 de octubre de 2026 la huella pública corporativa, de canales y de relaciones de INCIBE mediante fuentes abiertas pasivas para que su CISO pueda priorizar medidas defensivas frente a la suplantación de marca y la exposición documental, excluyendo datos personales de terceros y pruebas activas.

### 2.3 Preguntas de inteligencia

| Prioridad | Pregunta | Huella que cubre | Te ayuda a decidir |
|---:|---|---|---|
| **1 (Alta)** | **PI-02:** ¿Qué dominios, portales temáticos, líneas de atención y perfiles en redes sociales declara INCIBE como canales propios en su web, y qué cambios relevantes muestra su página principal respecto a versiones anteriores? | De canales | Qué activos y canales oficiales deben incluirse prioritariamente en la monitorización contra suplantación de marca (*typosquatting* y perfiles apócrifos). |
| **2 (Media)** | **PI-01:** ¿Qué razón social exacta, NIF, datos de inscripción registral y denominaciones históricas figuran oficialmente asociados a INCIBE en el Registro Mercantil (BORME) y en agregadores societarios? | Corporativa o profesional | Qué controles de concienciación y validación administrativa debe aplicar el CISO para prevenir engaños que utilicen datos registrales reales o denominaciones antiguas extinguida (INTECO). |
| **3 (Media)** | **PI-03:** ¿Cómo se relacionan entre sí la sociedad mercantil, sus marcas operativas (`OSI`, `IS4K`) y las entidades o proveedores mencionados en la documentación pública indexada? | De relaciones | Qué flujos de comunicación con terceros y procesos de publicación de pliegos requieren protocolos de verificación fuera de banda e higienización de metadatos. |

---

## 3. Plan de obtención

### 3.1 Herramientas por pregunta

| Pregunta | Herramienta | Alternativa descartada y motivo | Entrada | Qué expone y a quién | Resultado esperado |
|---|---|---|---|---|---|
| **PI-02 / PI-03** | **Google con operadores** | Bing / DuckDuckGo: descartados por ofrecer menor cobertura de indexación sobre subpáginas y documentos PDF en dominios institucionales `.es`. | `site:incibe.es`, `site:incibe.es filetype:pdf`, `"incibe.es" -site:incibe.es`, `site:osi.es`, `site:is4k.es` | Envía la cadena de consulta y la IP del investigador a Google LLC; **no llega al objetivo** mientras solo se consulten resultados cacheados del buscador. Al visitar directamente `incibe.es` para verificar el pie de página y aviso legal, sí se envía una petición HTTPS estándar al servidor web del objetivo. | Localización del aviso legal, estimación de PDFs públicos para A04, verificación de enlaces a redes sociales en el pie de página y comprobación de titularidad declarada en `osi.es` e `is4k.es`. |
| **PI-02** | **Wayback Machine** | Archive.today: descartado por disponer de menor número de capturas históricas seriadas del dominio `incibe.es`. | `https://www.incibe.es/` | Envía la URL consultada y la IP del investigador a Internet Archive (`web.archive.org`); **no llega al objetivo**. | Comparación entre dos versiones históricas con fecha exacta para identificar cambios en los canales de atención (como el 017) y en la adscripción institucional. |
| **PI-01** | **OpenCorporates y BORME (Buscador BOE)** | Directorios mercantiles privados de pago (eInforma/Axesor): descartados por requerir suscripción cuando la fuente primaria pública es el BORME. | `"Instituto Nacional de Ciberseguridad de España"`, `"INTECO"`, `A24512980` | Envía los términos de búsqueda a OpenCorporates Ltd. y a la Agencia Estatal BOE (`boe.es`); **no llega al objetivo**. | Ficha societaria, NIF, datos registrales en León, confirmación del cambio de denominación desde INTECO y comprobación de limitaciones de búsqueda por NIF en el BOE. |
| **PI-02 / PI-03** | **Intelligence X** *(Opcional)* | Google Lens / TinEye (descartadas por no investigarse imágenes de personas físicas) y Hunchly (licencia comercial). | `incibe.es` | Envía el selector buscado y el identificador de sesión gratuita a Intelligence X (`intelx.io`); **no llega al objetivo**. | Contadores de referencias históricas e índices públicos donde aparece mencionado el dominio, sin abrir ni descargar muestras de filtraciones. |
| **PI-03** | **Maltego CE** | Creación manual en software de dibujo genérico: descartado porque Maltego permite gestionar entidades tipadas y documentar el origen de cada vínculo. | Entidades comprobadas en consultas previas (`S.M.E. INCIBE M.P., S.A.`, `incibe.es`, `osi.es`, `is4k.es`, perfiles sociales) y transformación DNS pasiva/estándar (`To DNS Name - NS / MX`). | Las transformaciones ejecutadas través de los servidores de Paterva/Maltego envían la entidad a Maltego y realizan resoluciones DNS que **sí pueden alcanzar los servidores DNS autoritativos del objetivo**. | Grafo estructurado que relacione la entidad legal con sus marcas, dominios, canales declarados y vínculos pendientes de contrastar en A04. |

### 3.2 Herramientas que no se usan

| Herramienta | Motivo |
|---|---|
| **Google Lens / TinEye** | Se descartan porque en la Modalidad A no se investigan fotografías ni avatares de personas físicas, y los logotipos institucionales de INCIBE son públicos y conocidos. |
| **Hunchly** | Se descarta por ser una herramienta comercial de pago y resultar suficiente la captura, recorte y anonimización manual sistemática (`EV-01.png` a `EV-08.png`) para garantizar la trazabilidad del registro. |
| **Serus** | Se descarta dado que ya se emplea **Intelligence X** como herramienta opcional del catálogo y se prefiere evitar el uso de plataformas asistidas por IA durante la obtención. |
| **OpenSanctions** | Se descarta porque el objetivo es una sociedad mercantil estatal española y ninguna pregunta de inteligencia requiere verificar listas de sanciones internacionales o personas políticamente expuestas (PEP). |
| **Babel Street** | Se descarta por tratarse de una herramienta corporativa de licencia restringida no disponible en el entorno de prácticas e innecesaria para los canales públicos analizados. |

### 3.3 Configuración y seguridad de la operación

- **Identidad y cuentas utilizadas:** Las consultas en Google, Wayback Machine, BORME (BOE) y OpenCorporates se realizan sin sesión iniciada. Para Maltego CE e Intelligence X se utiliza una cuenta gratuita de laboratorio creada específicamente para la asignatura, sin datos personales identificativos en el alias visible y con credenciales únicas.
- **Navegador y perfil:** Uso de navegador con un perfil aislado exclusivo para la actividad (`perfil-osint-a03`), sin historial previo, con bloqueo de rastreadores activado, sin sincronización en la nube y sin extensiones de terceros ni asistentes de IA.
- **Carpeta de trabajo fuera del repositorio:** Las capturas originales sin recortar y el archivo `.mtgl` de Maltego se guardan en una carpeta local temporal fuera del árbol de Git (`~/osint_trabajo_local/A03/`). Al repositorio (`entregas/atecaAlejandro/A03/`) solo se copian las capturas finales ya recortadas y anonimizadas con bloques opacos.

**Modalidad B · Fecha y hora de cierre del plan:** El plan se redactó antes de la obtención de datos (`OBT-01`), pero se me pasó subirlo al repositorio antes de dicha obtención. Por tanto, no existe un *commit* previo que permita acreditar documentalmente que el plan estaba registrado antes de `OBT-01`.

---

## 4. Obtención

### 4.1 Registro de obtención

| ID | Herramienta | Consulta o acción exacta | Fecha y hora | Resultado | Límite | Evidencia |
|---|---|---|---|---|---|---|
| **OBT-01** | Google y Navegador | Consulta `site:incibe.es "aviso legal"` y acceso directo a `https://www.incibe.es/aviso-legal` y pie de página de `https://www.incibe.es/` | 2026-10-29 17:05 CET | El Aviso Legal declara la titularidad de *S.M.E. Instituto Nacional de Ciberseguridad de España M.P., S.A.*, NIF A24512980, domicilio en Avda. José Aguado 41 (León), datos registrales (Tomo 1.076, Folio 170, Hoja LE-16786) y su adscripción al Ministerio para la Transformación Digital y de la Función Pública a través de SEDIA. En el pie de página e iconos oficiales enlaza a X (`@INCIBE`), LinkedIn (`company/incibe`), YouTube (`@INCIBE`), Instagram (`@incibe`), Facebook (`INCIBE`) y la línea 017. | Es una fuente autodeclarada por el propio objetivo; el acceso directo envía una petición HTTPS normal al servidor web de `incibe.es`. | `EV-01.png` |
| **OBT-02** | Google | `site:incibe.es filetype:pdf` | 2026-10-29 17:12 CET | El buscador devuelve una estimación heurística superior a 1.500 resultados de archivos PDF (guías técnicas, memorias, resoluciones y licitaciones), confirmando material documental abundante para FOCA en A04. | El contador de Google es una estimación aproximada y el buscador trunca la paginación real en torno a los 300-400 resultados visibles. | `EV-02.png` |
| **OBT-03** | Google | `site:incibe.es filetype:pdf "pliego" OR "adjudicación" OR "expediente"` | 2026-10-29 17:20 CET | Se localizan pliegos de prescripciones técnicas y documentos de expedientes de contratación publicados en `incibe.es` que citan servicios tecnológicos adjudicados y números de expediente. | Los PDFs muestran fotografías estáticas del momento de licitación; no confirman si el contrato sigue vigente hoy. Aparecen nombres de firmantes que se descartan y ocultan. | `EV-03.png` |
| **OBT-04** | Google | `"incibe.es" -site:incibe.es` | 2026-10-29 17:28 CET | Muestra menciones externas al dominio en portales de la Administración (`administracion.gob.es`), en los portales `osi.es` e `is4k.es` y en noticias; también aparecen referencias a siglas coincidentes en Iberoamérica ajenas al objetivo. | Alto ruido informativo y presencia de homónimos de siglas en otros países hispanohablantes que deben filtrarse y descartarse manualmente. | — |
| **OBT-05** | Google | `site:osi.es "aviso legal" OR "INCIBE"` y `site:is4k.es "aviso legal" OR "INCIBE"` | 2026-10-29 17:35 CET | Ambos dominios (`osi.es` de la Oficina de Seguridad del Internauta e `is4k.es` de Internet Segura for Kids) declaran en sus páginas legales ser servicios operados por *S.M.E. Instituto Nacional de Ciberseguridad de España M.P., S.A. (INCIBE)* con NIF A24512980. | Confirma la vinculación declarativa y jurídica de los dominios, pero no demuestra por sí mismo que compartan la misma dirección IP (pendiente para A04). | — |
| **OBT-06** | Wayback Machine | Comparación de `https://web.archive.org/web/20160615120000/http://www.incibe.es/` (`2016-06-15`) y `https://web.archive.org/web/20260910080000/https://www.incibe.es/` (`2026-09-10`) | 2026-10-29 17:45 CET | En la captura del `2016-06-15` la web dependía del antiguo MINETUR y carecía del número corto 017; en la versión del `2026-09-10` destaca en cabecera la línea de ayuda **017**, la dependencia del Ministerio para la Transformación Digital y los accesos directos a INCIBE-CERT, OSI e IS4K. | La comparación entre dos fechas puntuales (`2016` y `2026`) no permite fijar el día exacto de creación de cada servicio intermedio y algunos estilos CSS antiguos no cargan por completo. | `EV-04.png` |
| **OBT-07** | OpenCorporates | Búsqueda en `https://opencorporates.com` de `"Instituto Nacional de Ciberseguridad de España"` y `"INTECO"` (`jurisdiction:es`) | 2026-10-29 17:58 CET | Localizada la ficha societaria española en León, registrando su denominación actual y su nombre previo *Instituto Nacional de Tecnologías de la Comunicación, S.A. (INTECO)*, junto con asientos extraídos del BORME. | OpenCorporates se nutre del propio BORME (no es una fuente primaria independiente), presenta desfase temporal en su versión sin pago y lista nombres de directivos que se descartan. | `EV-05.png` |
| **OBT-08** | BORME (Buscador BOE) | Búsqueda en `https://www.boe.es/buscar/borme.php` por texto libre: `"Instituto Nacional de Ciberseguridad de España"` e `"Instituto Nacional de Tecnologias de la Comunicacion"` | 2026-10-29 18:10 CET | Boletines oficiales del Registro Mercantil de León donde consta el cambio de denominación social de INTECO a INCIBE en 2014, su carácter de Sociedad Mercantil Estatal (S.M.E.) y Medio Propio (M.P.), y actos registrales en la hoja de la sociedad en León. | El buscador gratuito del BORME devuelve boletines PDF individuales por acto, pero no una nota simple consolidada; los nombres propios de cargos publicados se descartan por alcance. | `EV-06.png` |
| **OBT-09** | BORME (Buscador BOE) | Búsqueda en `https://www.boe.es/buscar/borme.php` introduciendo únicamente el NIF `A24512980` | 2026-10-29 18:16 CET | **Resultado vacío (0 resultados)** en el buscador general del BORME al buscar exclusivamente por la cadena del NIF, debido a que los anuncios ordinarios del BORME de León indexan la denominación social y número de asiento, pero rara vez incluyen el NIF en el cuerpo del texto publicado. | Restricción de indexación de la fuente: un resultado vacío por NIF en el buscador del BORME no significa que la sociedad no exista, sino que debe consultarse por denominación social (`OBT-08`). | — |
| **OBT-10** | Intelligence X | Búsqueda del selector `incibe.es` en `https://intelx.io` | 2026-10-29 18:28 CET | El panel muestra contadores numéricos de resultados asociados al término `incibe.es` en las categorías *Public Web*, *Whois* y colecciones archivadas. Siguiendo las normas de la actividad, no se abre ningún registro individual. | Restricción de cuenta gratuita (vistas censuradas) y límite ético de la asignatura: al no abrir los registros, solo se observa que el nombre de dominio aparece referenciado en esos índices, sin poder determinar si corresponde a boletines públicos citados o a correos. | `EV-07.png` |
| **OBT-11** | Maltego CE | Inserción manual de las entidades verificadas (`S.M.E. INCIBE M.P., S.A.`, `incibe.es`, `osi.es`, `is4k.es`, perfiles sociales y `Línea 017`) y ejecución de la transformación estándar `To DNS Name - NS (Name Server)` sobre `incibe.es` | 2026-10-29 18:45 CET | Construcción del grafo consolidado de relaciones (declaradas, observadas y pendientes) y obtención de los servidores de nombres asociados a `incibe.es`. | Límite de cuota en cuenta gratuita de Maltego CE; las relaciones jurídicas y de marca requieren trazado manual apoyado en `OBT-01`, `OBT-05` y `OBT-08` para no atribuir activos por simple coincidencia. | `EV-08.png` |

### 4.2 Resultados por herramienta

- **Google con operadores y verificación web (`OBT-01`, `OBT-02`, `OBT-03`, `OBT-04`, `OBT-05`):**
  - *Pregunta que respondía:* **PI-02** (canales oficiales, dominios y portales) y **PI-03** (documentación de licitaciones y vínculos entre marcas).
  - *Qué se obtuvo:* Se verificó directamente en el aviso legal y pie de página de `incibe.es` (`OBT-01`) la razón social, el NIF A24512980, los datos registrales y los enlaces a sus perfiles sociales oficiales. Con `OBT-05` se comprobó que `osi.es` e `is4k.es` declaran pertenecer a la misma entidad legal. Con `OBT-02` y `OBT-03` se constató una estimación superior a 1.500 PDFs indexados, incluyendo pliegos con referencias a adjudicatarios. Con `OBT-04` se identificaron menciones externas y se filtraron homónimos de siglas en Iberoamérica.
  - *Límite:* El recuento de Google es una estimación heurística sujeta a deduplicación y corte de paginación (~300-400 resultados); además, los documentos de licitación reflejan adjudicaciones pasadas sin garantizar su vigencia actual.

- **Wayback Machine (`OBT-06`):**
  - *Pregunta que respondía:* **PI-02** (evolución histórica de canales y página principal).
  - *Qué se obtuvo:* Comparando las capturas exactas del `2016-06-15` y del `2026-09-10`, se observó el cambio de adscripción ministerial (del antiguo MINETUR al actual Ministerio para la Transformación Digital y de la Función Pública) y la incorporación destacada del teléfono **017** como canal nacional centralizado de ayuda en ciberseguridad (`OBT-06`).
  - *Límite:* Comparar dos instantes separados por diez años permite acreditar el cambio entre ambos estados, pero no la fecha exacta de implantación de los elementos intermedios.

- **OpenCorporates y BORME (`OBT-07`, `OBT-08`, `OBT-09`):**
  - *Pregunta que respondía:* **PI-01** (entidad legal, registro, NIF y denominaciones históricas).
  - *Qué se obtuvo:* Se acreditó en el BORME (`OBT-08`) y en OpenCorporates (`OBT-07`) la inscripción en el Registro Mercantil de León de *S.M.E. Instituto Nacional de Ciberseguridad de España M.P., S.A.*, así como su cambio de denominación en 2014 desde *Instituto Nacional de Tecnologías de la Comunicación, S.A. (INTECO)*. Asimismo, se documentó que la búsqueda directa por NIF en el buscador libre del BORME arroja un resultado vacío (`OBT-09`) por cómo se publican los anuncios mercantiles.
  - *Límite:* OpenCorporates extrae sus datos del BORME (por lo que no constituye una fuente independiente respecto a este) y el buscador gratuito del BOE no proporciona una nota simple refundida ni permite buscar eficazmente por NIF.

- **Intelligence X (`OBT-10`):**
  - *Pregunta que respondía:* **PI-02** y **PI-03** (presencia del dominio en índices y archivos históricos).
  - *Qué se obtuvo:* Se comprobó que el selector `incibe.es` registra apariciones cuantificadas en las categorías *Public Web*, *Whois* y colecciones archivadas del índice (`OBT-10`).
  - *Límite:* Debido a las restricciones de la versión gratuita y a la prohibición expresa de abrir contenidos de colecciones de filtraciones, el resultado se limita al conteo de referencias del dominio sin conocer el detalle de los archivos indexados.

- **Maltego CE (`OBT-11`):**
  - *Pregunta que respondía:* **PI-03** (conexión gráfica entre sociedad, marcas, dominios, canales y terceros).
  - *Qué se obtuvo:* Se generó el grafo relacional conectando la sociedad mercantil con sus marcas (`INCIBE`, `OSI`, `IS4K`), sus tres dominios `.es`, sus perfiles sociales verificados, su adscripción ministerial declarada (`SEDIA`) y la transformación de servidores de nombres sobre `incibe.es` (`OBT-11`).
  - *Límite:* Las transformaciones DNS pueden generar tráfico hacia los servidores autoritativos del objetivo y el grafo exige validación manual previa para distinguir relaciones observadas de las meramente declaradas o pendientes.

### 4.3 Revisión de la elección

| Pregunta | Herramienta prevista | Herramienta utilizada | Evidencia obtenida | ¿Resuelve la pregunta? | Cambio justificado |
|---|---|---|---|---|---|
| **PI-01** | OpenCorporates y BORME (por nombre, INTECO y NIF) | OpenCorporates (`OBT-07`) y BORME por denominación (`OBT-08`) y por NIF (`OBT-09`) | `EV-05.png`, `EV-06.png` | **Sí**, resuelve la identidad legal, datos registrales e historial desde INTECO. | Sin cambio de herramientas; se registró adicionalmente el fallo de búsqueda por NIF en el BORME (`OBT-09`), supliéndolo con la búsqueda por razón social (`OBT-08`) y el contraste con el aviso legal (`OBT-01`). |
| **PI-02** | Google con operadores y Wayback Machine | Google con operadores (`OBT-01`, `OBT-02`, `OBT-04`, `OBT-05`), visita al aviso legal/pie de página y Wayback Machine (`OBT-06`) | `EV-01.png`, `EV-02.png`, `EV-04.png` | **Sí**, identifica los dominios y canales declarados y su evolución entre 2016 y 2026. | Se añadieron consultas específicas sobre `osi.es` e `is4k.es` (`OBT-05`) y la revisión directa del pie de página (`OBT-01`) para no dar por supuesta la titularidad de los portales temáticos ni de las redes sociales. |
| **PI-03** | Maltego CE e Intelligence X | Google (`OBT-03`, `OBT-05`), Intelligence X (`OBT-10`) y Maltego CE (`OBT-11`) | `EV-03.png`, `EV-07.png`, `EV-08.png` | **Parcialmente**: resuelve los vínculos de marca y documenta licitaciones, pero deja pendientes la vigencia actual de proveedores y la infraestructura compartida. | Se complementó Maltego con las consultas documentales en Google (`OBT-03`, `OBT-05`) para respaldar con evidencia cada arista del grafo; la correlación técnica de IPs y metadatos queda pendiente para la A04 (Shodan y FOCA). |

---

## 5. Análisis de la huella

### 5.1 Ficha del objetivo

| Campo | Dato | Referencia | Fecha del dato | Precaución |
|---|---|---|---|---|
| **Nombre legal** | S.M.E. Instituto Nacional de Ciberseguridad de España M.P., S.A. (NIF: A24512980). Inscrita en el Registro Mercantil de León (Tomo 1.076, Folio 170, Hoja LE-16786). Domicilio social: Avda. José Aguado, 41, 24005 León. Denominación anterior hasta 2014: *Instituto Nacional de Tecnologías de la Comunicación, S.A. (INTECO)*. | `(OBT-01, OBT-07, OBT-08)` | 2026-10-29 | Es una sociedad mercantil estatal con forma de S.A., no un organismo autónomo administrativo. No debe confundirse su razón social actual con la extinguida INTECO. |
| **Marcas** | **INCIBE** (marca principal), **INCIBE-CERT** (centro de respuesta a incidentes), **OSI** (Oficina de Seguridad del Internauta) e **IS4K** (Internet Segura for Kids). | `(OBT-01, OBT-05, OBT-06)` | 2026-10-29 | OSI e IS4K son marcas y portales operados por la misma sociedad mercantil (INCIBE), no entidades jurídicas distintas. |
| **Filiales o entidades relacionadas** | Adscrita funcionalmente al **Ministerio para la Transformación Digital y de la Función Pública** a través de la **Secretaría de Estado de Digitalización e Inteligencia Artificial (SEDIA)**. No se observan sociedades filiales dependientes de INCIBE en los actos consultados. | `(OBT-01, OBT-06, OBT-08)` | 2026-10-29 | SEDIA es el órgano superior administrativo de adscripción declarada en la web oficial; no debe atribuirse relación societaria con homónimos en otros países (`OBT-04`). |
| **Dominios oficiales** | `incibe.es` (portal corporativo e INCIBE-CERT), `osi.es` (ciudadanía) e `is4k.es` (menores). | `(OBT-01, OBT-05, OBT-11)` | 2026-10-29 | En la actividad A04, las consultas en Shodan y FOCA deben restringirse exclusivamente a estos tres dominios verificados. |
| **Canales y perfiles oficiales** | Teléfono nacional **017**; perfiles oficiales enlazados en el pie de página de `incibe.es`: X (`@INCIBE`), LinkedIn (`company/incibe`), YouTube (`@INCIBE`), Instagram (`@incibe`) y Facebook (`INCIBE`). | `(OBT-01, OBT-06, OBT-11)` | 2026-10-29 | Solo deben considerarse oficiales las cuentas enlazadas directamente desde `incibe.es`, evitando atribuir perfiles por simple coincidencia de nombre. |
| **Proveedores observados** | Empresas adjudicatarias de servicios TIC, desarrollo web y asistencia técnica que figuran en los pliegos y resoluciones de contratación indexados en formato PDF bajo `incibe.es`. | `(OBT-02, OBT-03)` | 2026-10-29 | Los documentos PDF indexados reflejan el momento de la adjudicación; no permiten confirmar sin fuentes adicionales si el contrato sigue activo hoy. |

### 5.2 Huella por dimensiones

#### Corporativa o profesional

- **Observado:** El aviso legal de `incibe.es` (`OBT-01`) declara que la entidad titular es *S.M.E. Instituto Nacional de Ciberseguridad de España M.P., S.A.*, con NIF A24512980, domicilio en León e inscripción en el Registro Mercantil de León (Tomo 1.076, Folio 170, Hoja LE-16786). Las consultas en el BORME (`OBT-08`) y en OpenCorporates (`OBT-07`) muestran los asientos registrales en León y el cambio de denominación social en 2014 desde *Instituto Nacional de Tecnologías de la Comunicación, S.A. (INTECO)*. Por su parte, la búsqueda por NIF en el buscador general del BORME (`OBT-09`) no devolvió resultados por limitaciones de indexación de dicho buscador.
- **Valoración:**
  - *Fiabilidad de la fuente:* **Alta (A)** para el BORME (boletín oficial estatal) y **Alta (A)** para el aviso legal de la propia organización en lo relativo a datos identificativos exigidos por ley; **Media-Alta (B)** para OpenCorporates como agregador secundario.
  - *Credibilidad de la información:* **Confirmada (1)** para la razón social, el domicilio en León y el antecedente INTECO, al coincidir el registro oficial del BORME (`OBT-08`) con la declaración institucional en `incibe.es` (`OBT-01`). Se tiene en cuenta que OpenCorporates (`OBT-07`) toma sus datos del propio BORME, por lo que entre ambos no hay independencia, sino que el contraste real se produce entre el boletín oficial (`OBT-08`) y la web corporativa (`OBT-01`).
  - *Lo que falta:* No se dispone de una nota simple mercantil refundida actual ni del detalle de apoderados vigentes (cuya investigación nominal queda además excluida por las reglas de la Modalidad A).

#### De canales

- **Observado:** La organización presenta tres dominios web diferenciados (`incibe.es`, `osi.es` e `is4k.es`) que declaran en sus respectivos textos legales la misma razón social y NIF (`OBT-01, OBT-05`). En el pie de página de `incibe.es` se enlazan como canales oficiales las cuentas en X, LinkedIn, YouTube, Instagram y Facebook (`OBT-01`). La comparativa en Wayback Machine entre el `2016-06-15` y el `2026-09-10` (`OBT-06`) muestra la incorporación en cabecera de la línea telefónica gratuita **017** y la actualización de los logotipos ministeriales hacia el Ministerio para la Transformación Digital y de la Función Pública. En Google (`OBT-02`) se observa una estimación superior a 1.500 archivos PDF públicos en `incibe.es`, y en Intelligence X (`OBT-10`) figuran referencias al dominio en colecciones de archivo web y *Whois*.
- **Valoración:**
  - *Fiabilidad de la fuente:* **Alta (A)** para la observación directa de los portales oficiales (`OBT-01, OBT-05`) y las capturas de Internet Archive (`OBT-06`); **Media (C)** para los contadores heurísticos de Google (`OBT-02`) e Intelligence X (`OBT-10`).
  - *Credibilidad de la información:* **Confirmada (1)** respecto a qué canales y dominios presenta la organización como oficiales (`OBT-01, OBT-05, OBT-06`); **Posiblemente verdadera (3)** respecto al volumen exacto de archivos PDF y la naturaleza de las menciones en Intelligence X, dado que los contadores son estimaciones o índices sin inspección de muestras.
  - *Lo que falta:* Determinar qué subdominios técnicos o servidores concretos dan soporte a estos tres dominios, aspecto pendiente para la actividad A04 mediante Shodan.

#### De relaciones

- **Observado:** El grafo elaborado en Maltego (`OBT-11`) recoge la relación declarada entre la sociedad mercantil y sus marcas operativas (`INCIBE`, `OSI`, `IS4K`), así como su adscripción funcional declarada a SEDIA (`OBT-01, OBT-05, OBT-06`) y los servidores DNS obtenidos mediante transformación para `incibe.es` (`OBT-11`). Asimismo, las consultas de PDFs de contratación (`OBT-03`) evidencian relaciones documentadas con adjudicatarios externos de servicios tecnológicos y pliegos de prescripciones técnicas.
- **Valoración:**
  - *Fiabilidad de la fuente:* **Alta (A)** para los avisos legales y documentos oficiales de licitación alojados en `incibe.es`.
  - *Credibilidad de la información:* **Probablemente verdadera (2)** para los vínculos declarados de adscripción y para las relaciones con proveedores observadas en pliegos (`OBT-03`), ya que en esta fase solo se han contrastado a través de la documentación publicada por el propio objetivo sin verificar en fuentes externas independientes si los contratos siguen vigentes.
  - *Lo que falta:* Confirmar qué adjudicatarios mantienen contratos en vigor actualmente y comprobar en la A04 (con Shodan y FOCA) si los tres dominios comparten infraestructura de red o metadatos de autoría.

### 5.3 Grafo de relaciones

![Grafo de relaciones exportado desde Maltego](evidencias/EV-08.png)

**Leyenda y detalle de relaciones del grafo (cada relación utiliza una única categoría):**

| Relación | Tipo | Referencia |
|---|---|---|
| `S.M.E. INCIBE M.P., S.A. (A24512980)` $\rightarrow$ inscrita y antes denominada $\rightarrow$ `INTECO S.A. (RM León)` | **Observada** | `(OBT-07, OBT-08, OBT-11)` |
| `incibe.es` $\rightarrow$ resuelve servidores de nombres (NS) $\rightarrow$ `Servidores DNS asociados` | **Observada** | `(OBT-11)` |
| `incibe.es` $\rightarrow$ publica pliegos y adjudicaciones con $\rightarrow$ `Proveedores TIC en PDFs` | **Observada** | `(OBT-02, OBT-03, OBT-11)` |
| `S.M.E. INCIBE M.P., S.A.` $\rightarrow$ declara titularidad de dominios $\rightarrow$ `incibe.es`, `osi.es`, `is4k.es` | **Declarada** | `(OBT-01, OBT-05, OBT-11)` |
| `incibe.es` $\rightarrow$ enlaza en pie de página y cabecera $\rightarrow$ `Perfiles redes sociales y Línea 017` | **Declarada** | `(OBT-01, OBT-06, OBT-11)` |
| `S.M.E. INCIBE M.P., S.A.` $\rightarrow$ declara adscripción funcional a $\rightarrow$ `SEDIA (Ministerio Transformación Digital)` | **Declarada** | `(OBT-01, OBT-06, OBT-11)` |
| `incibe.es`, `osi.es`, `is4k.es` $\rightarrow$ comparten direccionamiento IP y metadatos en documentos | **Pendiente** | `(OBT-02, OBT-05, OBT-11)` |

### 5.4 Valoración de hallazgos clave

| Hallazgo | Referencias | Fiabilidad de la fuente | Credibilidad de la información | Hecho o inferencia | Contraste independiente |
|---|---|---|---|---|---|
| **H-01:** La entidad opera bajo la razón social *S.M.E. Instituto Nacional de Ciberseguridad de España M.P., S.A.* (NIF A24512980), inscrita en el RM de León y denominada *INTECO S.A.* hasta 2014. | `(OBT-01, OBT-07, OBT-08)` | Alta (A · BORME y Aviso Legal) | Confirmada (1) | **Hecho** | Contrastado entre los asientos oficiales del BORME (`OBT-08`) y la declaración legal en `incibe.es` (`OBT-01`). *(Nota: OpenCorporates `OBT-07` deriva del BORME y no se computa como fuente independiente).* |
| **H-02:** Coexistencia de tres dominios oficiales distintos (`incibe.es`, `osi.es`, `is4k.es`) y el canal telefónico 017 bajo la misma sociedad mercantil. | `(OBT-01, OBT-05, OBT-06)` | Alta (A · Portales oficiales y Archive.org) | Confirmada (1) | **Hecho** (la coexistencia de dominios y marcas) / **Inferencia** (que dicha separación de nombres facilite engaños por *typosquatting* contra usuarios). | Contrastado revisando los avisos legales de los tres dominios (`OBT-01, OBT-05`) y las capturas históricas en Wayback Machine (`OBT-06`). |
| **H-03:** Amplia exposición de documentación pública en formato PDF bajo `incibe.es` (estimada heurísticamente por Google en más de 1.500 resultados), incluyendo pliegos de contratación. | `(OBT-02, OBT-03)` | Media-Alta (B · Índice de Google sobre web oficial) | Probablemente verdadera (2) | **Hecho** (la existencia de centenares de PDFs públicos de licitación y guías) / **Inferencia** (la cifra exacta >1.500 y la presencia de metadatos internos sensibles, pendiente de verificar con FOCA en A04). | Verificado mediante dos consultas distintas con operadores en Google (`OBT-02, OBT-03`), pero pendiente de descarga y análisis con FOCA en la actividad A04. |
| **H-04:** Aparición del selector `incibe.es` en contadores de categorías web, *Whois* y colecciones archivadas dentro del índice de Intelligence X. | `(OBT-10)` | Media (C · Agregador OSINT sin inspección de muestras) | Posiblemente verdadera (3) | **Hecho** (el contador numérico en el buscador) / **Inferencia** (el origen concreto de cada mención, ya que sin abrir los registros no puede saberse si son boletines públicos citados o correos). | Sin contraste independiente directo, dado que por las normas de la actividad no se abren ni cruzan contenidos de colecciones de filtraciones. |

---

## 6. Perspectiva del atacante

| Información visible | Referencia | Cómo podría aprovecharla un atacante | A qué afectaría | Medida defensiva | Prioridad |
|---|---|---|---|---|---|
| **Coexistencia de tres dominios institucionales (`incibe.es`, `osi.es`, `is4k.es`) y alta visibilidad pública del servicio 017.** | `(OBT-01, OBT-05, OBT-06)` | Un atacante podría registrar dominios parecidos (*typosquatting* o *combosquatting*) que imiten cualquiera de las tres marcas o el servicio 017 para enviar comunicaciones fraudulentas o suplantar canales de ayuda ante ciudadanos y empresas. | Reputación institucional de INCIBE y seguridad de terceros susceptibles de caer en campañas de *phishing* o suplantación de marca. | Implementar monitorización continua de registros de dominios similares y logs de *Certificate Transparency* (CT), mantener políticas estrictas de SPF/DKIM/DMARC en modo rechazo (`p=reject`) y publicar una guía unificada de verificación de canales oficiales. | **Alta** |
| **Datos de expedientes, objetos contractuales y menciones a empresas adjudicatarias en pliegos PDF públicos.** | `(OBT-02, OBT-03)` | Un actor malicioso puede utilizar números de expediente reales y detalles de licitaciones publicados por obligación de transparencia para redactar pretextos creíbles de ingeniería social (*spear phishing*) o intentos de fraude en facturación (*BEC*) dirigidos a adjudicatarios o personal administrativo. | Integridad de las comunicaciones administrativas y seguridad de la cadena de suministro de proveedores. | Establecer protocolos obligatorios de verificación fuera de banda (*Out-of-band* por canal telefónico preacordado o firma cualificada) para cualquier solicitud de cambio de cuentas bancarias, facturación o contactos técnicos en contratos adjudicados. | **Alta** |
| **Centenares de documentos PDF públicos indexados en `incibe.es` (hipótesis de exposición de metadatos pendiente de verificar en A04).** | `(OBT-02, OBT-03)` | Bajo la hipótesis (que se comprobará en la A04 con FOCA) de que los archivos PDF conserven propiedades de creación, un atacante podría recolectarlos masivamente para extraer usuarios internos, versiones exactas de software ofimático o rutas de carpetas compartidas para preparar un reconocimiento técnico. | Confidencialidad sobre la configuración ofimática e identificadores internos de red. | Implantar un proceso técnico automatizado de higienización y limpieza de metadatos (*metadata scrubbing* con herramientas tipo `exiftool`/`pdfcpu`) integrado en el flujo de subida del gestor de contenidos web (CMS), junto con un protocolo de doble revisión antes de publicar. | **Media** |
| **Constancia pública de la antigua denominación social (*INTECO S.A.*) vinculada al NIF actual (`A24512980`) en registros mercantiles.** | `(OBT-07, OBT-08)` | Un atacante podría construir notificaciones administrativas o requerimientos falsos empleando la antigua denominación *INTECO* junto con el NIF real para aparentar legitimidad ante interlocutores externos o evitar reglas de filtrado que solo busquen el acrónimo *INCIBE*. | Eficacia de los controles de detección de engaños administrativos basados en identidad corporativa. | Incluir en las acciones de concienciación interna y en los avisos a proveedores la indicación expresa de que la denominación *INTECO* está extinguida desde 2014 y no se emplea en ninguna comunicación ni trámite vigente. | **Baja** |

---

## 7. Limitaciones, datos descartados e incidencias

- **Preguntas o aspectos no resueltos completamente y por qué:**
  - **PI-03 (Relaciones con proveedores e infraestructura):** Se ha resuelto parcialmente. Aunque los pliegos PDF (`OBT-03`) permiten observar adjudicaciones y expedientes, las fuentes abiertas documentales consultadas en `incibe.es` no permiten confirmar qué contratos siguen vigentes a fecha de hoy ni su grado de relación técnica actual. Asimismo, saber si los dominios `incibe.es`, `osi.es` e `is4k.es` comparten direccionamiento IP o metadatos internos queda pendiente de comprobación en la actividad A04 con Shodan y FOCA.
  - **PI-02 (Evolución temporal intermedia):** La comparación de dos capturas en Wayback Machine (`2016-06-15` y `2026-09-10` en `OBT-06`) confirma el cambio entre ambos momentos, pero no permite fechar con precisión en qué mes concreto del periodo intermedio se desplegó cada cambio en la web.
- **Datos descartados por quedar fuera del alcance (minimización y homónimos):**
  - **Personas físicas:** En las fichas de OpenCorporates (`OBT-07`), en los anuncios del BORME (`OBT-08`) y en los documentos PDF de licitaciones (`OBT-03`) aparecieron nombres y apellidos de consejeros, apoderados, cargos públicos y responsables de contratación. Todos ellos han sido descartados del análisis y ocultados mediante bloques opacos en las capturas (`EV-03.png`, `EV-05.png`, `EV-06.png`).
  - **Homónimos:** En la búsqueda de menciones externas (`OBT-04`) se descartaron resultados que aludían a entidades o proyectos con siglas coincidentes en países de Iberoamérica sin relación alguna con la sociedad mercantil estatal española.
- **Incidencias:**
  - **No hubo incidencias de seguridad ni activación del protocolo «cuándo parar».** En la consulta `OBT-09` se registró un resultado vacío por limitación técnica del buscador del BORME al buscar por NIF. En la consulta `OBT-10` (Intelligence X) se visualizaron exclusivamente los contadores numéricos generales del dominio `incibe.es` sin abrir, previsualizar ni descargar ningún registro ni muestra de filtraciones, por lo que no se accedió a credenciales ni a datos personales sensibles y no fue necesario avisar por el canal privado.

---

## 8. Índice de evidencias

| Evidencia | Qué muestra | Fila del registro | Qué se ha ocultado |
|---|---|---|---|
| `evidencias/EV-01.png` | Aviso legal y pie de página de `incibe.es` mostrando la razón social *S.M.E. INCIBE M.P., S.A.*, NIF A24512980, datos registrales, adscripción a SEDIA y enlaces a redes sociales oficiales. | `OBT-01` | Interfaz superior del navegador local. |
| `evidencias/EV-02.png` | Consulta `site:incibe.es filetype:pdf` en Google mostrando la estimación de resultados PDF indexados para la A04. | `OBT-02` | Pie de ubicación del buscador y nombres de personas físicas si aparecían en algún fragmento de texto. |
| `evidencias/EV-03.png` | Resultados de la consulta `site:incibe.es filetype:pdf "pliego" OR "adjudicación" OR "expediente"` en Google. | `OBT-03` | Nombres y apellidos de firmantes o técnicos visibles en los fragmentos de resultados, cubiertos con bloque opaco. |
| `evidencias/EV-04.png` | Comparativa en Wayback Machine de `incibe.es` entre las capturas del `2016-06-15` y del `2026-09-10`, apreciándose el cambio ministerial y la incorporación del 017. | `OBT-06` | Pestañas y barra de herramientas del navegador. |
| `evidencias/EV-05.png` | Ficha societaria de INCIBE (antes INTECO) en OpenCorporates (`jurisdiction:es`). | `OBT-07` | Todos los nombres propios de directivos y apoderados del bloque *Officers*, ocultados con bloques opacos. |
| `evidencias/EV-06.png` | Anuncios oficiales en el buscador del BORME (BOE) correspondientes al Registro Mercantil de León. | `OBT-08` | Nombres y apellidos de cargos, representantes o apoderados mencionados en el boletín, ocultados con bloques opacos. |
| `evidencias/EV-07.png` | Vista general de contadores por categoría en Intelligence X para el selector `incibe.es` sin abrir registros. | `OBT-10` | Identificador de sesión gratuita de la plataforma y panel lateral de vista previa. |
| `evidencias/EV-08.png` | Grafo de relaciones exportado como imagen desde Maltego CE con la sociedad mercantil, marcas, dominios, DNS y canales oficiales. | `OBT-11` | Identificador de cuenta gratuita en la barra superior de la ventana de Maltego CE. |

---

## 9. Uso de inteligencia artificial

Ver [registro-ia.md](registro-ia.md).

---

## Comprobación

- [x] El objetivo cumple los requisitos de mi modalidad y no investigo a ninguna otra persona.
- [] Cerré los apartados 2 y 3 antes de la obtención: *commit* en la modalidad A, fecha de cierre en la modalidad B.
- [x] Cada afirmación lleva su referencia `OBT` y la he comprobado.
- [x] Las capturas están recortadas y anonimizadas.
- [x] Entrego antes del viernes 30 de octubre a las 23:59.
- [x] Modalidad A: solo he modificado `entregas/atecaAlejandro/A03/`. Modalidad B: nada está en el repositorio del curso.