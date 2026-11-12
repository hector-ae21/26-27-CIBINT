# A04 · Exposición técnica y documental

## Estudiante

- Nombre: Cayetano Castillo Ruiz
- Carpeta personal: entregas/castilloCayetano/A04/
- Modalidad: A
- Objetivo: Entidad Publica (Renfe)
- Entrega de la A03 (enlace al *pull request* o «entregada en el Campus Virtual»): https://github.com/hector-ae21/26-27-CIBINT/pull/27
- Periodo de obtención, con zona horaria: 04/11/2026 - 13:30 - UTC+1 (Madrid)

---

## 1. Resumen ejecutivo

La auditoría de exposición técnica y documental de la Entidad Pública Empresarial Renfe-Operadora (renfe.com) revela una superficie perimetral adecuadamente protegida frente a accesos directos no deseados, sustentada principalmente en la red de distribución de contenidos (CDN) de Akamai Technologies (más de 230 activos), con concentración estricta en el protocolo seguro HTTPS (puerto 443). No se observan paneles de gestión remota ni bases de datos expuestas en los dominios corporativos. No obstante, se constatan dos vectores de exposición relevantes: la identificación de infraestructura directa vinculada al servicio PlayRenfe alojada en Telefónica de España, y una notable fuga involuntaria de información en metadatos documentales. El análisis de documentos públicos descargados evidenció la presencia de nombres propios de personal, formatos de cuentas de usuario corporativas (LRCMU84) y software de diseño con versiones específicas. Se recomienda implementar pasarelas automatizadas de desinfección de metadatos previa a la publicación web y restringir el tráfico a los servidores de origen exclusivamente a las IPs de la CDN para mitigar riesgos de spear phishing y ataques de elusión perimetral.

| Pregunta | Respuesta breve | Confianza | Referencias |
|---|---|---|---|
|P1. Servicios y puertos visibles vs CDN |Tráfico perimetral web gestionado casi en su totalidad por Akamai Technologies en puerto 443. Localizado servidor de PlayRenfe en Telefónica con redirección HTTP a HTTPS. |Alta |OBT-01, OBT-02, OBT-04 / EV-01.png, EV-02.png, EV-04.png |
|P2. Información de software y servidores en metadatos |Uso extendido de Adobe InDesign e Illustrator, coexistencia de sistemas Windows y macOS, y pervivencia de PDFs generados en 2008 mediante Acrobat Distiller 5.0. | Alta|OBT-06 / EV-06.png |
|P3. Exposición de usuarios y cuentas internas |Detección de cuentas de empleado alfanuméricas (LRCMU84) y nombres propios en la autoría de normativas públicas. |Alta|OBT-06 / EV-06.png |

---

## 2. Punto de partida

### 2.1 Ficha del objetivo de la A03

| Campo | Dato | Referencia | Entrada para |
|---|---|---|---|
|Nombre legal matriz |Entidad Pública Empresarial Renfe-Operadora |A03 OBT-01 |Contexto corporativo e identificación de titularidad de activos. |
|Filial operativa principal |Renfe Viajeros, S.M.E., SA |A03 OBT-01 |Búsqueda en metadatos documentales de autoría jurídica. |
|Dominio principal |renfe.com |A03 OBT-02, A03 OBT-06 |Filtro base en Shodan (hostname:renfe.com, ssl:renfe.com) y proyecto FOCA. |
|Subdominios oficiales identificados |grupo.renfe.com, blog.renfe.com, renfeviajes.renfe.com, empleo.renfe.com |A03 OBT-02, A03 OBT-04 |Dorking documental en FOCA y consultas específicas hostname: en Shodan. |
|Infraestructura de terceros observada |Cloudflare Inc. (CDN/DNS) |A03 OBT-06 |Identificación de proveedores en resultados de Shodan para discernir activos directos vs proxies. |


### 2.2 Requerimiento

| Componente | Contenido |
|---|---|
| Destinatario |Responsable de Seguridad de la Información (CISO / Dirección de Ciberseguridad) de Renfe. |
| Decisión |Evaluar la superficie técnica expuesta hacia Internet (servicios de red y certificados) y la fuga de información involuntaria en documentos públicos para definir directivas de endurecimiento (hardening), políticas de borrado de metadatos y mitigación de vectores de reconocimiento. |
| Objeto |La exposición técnica de servicios perimetrales y los metadatos de ficheros publicados por Renfe accesibles pasivamente desde fuentes abiertas. |
| Horizonte |Estado técnico actual en índices pasivos y recopilación histórica de documentos publicados disponibles. |
| Alcance |Dominios corporativos del grupo (renfe.com y subdominios asociados) y ficheros ofimáticos/PDFs alojados públicamente en sus portales. |
| Exclusiones |Escaneos de puertos directos o activos sobre la red de Renfe; uso de filtros invasivos o búsqueda de sistemas industriales/internos; análisis de vulnerabilidades sobre IPs concretas; investigación o difusión de nombres personales hallados en metadatos. |
| Producto |Informe técnico A04 de exposición técnica y documental con registro de consultas, categorización de metadatos anonimizada, grafo de relaciones integrado en Maltego y medidas preventivas. |

### 2.3 Preguntas de inteligencia

| Prioridad | Pregunta | Huella que cubre | Te ayuda a decidir |
|---:|---|---|---|
|1 |¿Qué servicios y puertos asociados a los dominios de Renfe son visibles desde índices de escaneo pasivo y cuáles dependen de intermediarios/CDNs frente a infraestructura propia? |Técnica (Shodan / Censys) |Si existen activos o servicios expuestos que eluden el perímetro de protección (CDN/WAF) o si la superficie visible está adecuadamente intermediada. |
|2 |¿Qué información sobre estructura interna, software ofimático, servidores de red e impresoras revelan los metadatos de los documentos publicados por la entidad? |Documental (FOCA) |Qué políticas técnicas de ofuscación o herramientas de limpieza de metadatos (sanitization) deben imponerse en los flujos de publicación externa. |
|3 |¿Qué nombres de usuarios de red, cuentas de correo o formatos de nomenclatura interna quedan expuestos en los ficheros descargables de libre acceso? |Documental / Relaciones |Dónde reforzar las medidas contra ataques de ingeniería social dirigida, spear phishing o ataques de fuerza bruta basados en nombres de usuario reales. |

---

## 3. Plan de obtención

### 3.1 Consultas y documentos previstos

| Pregunta | Herramienta | Consulta, filtro o criterio | Fuente de contraste | Qué expone y a quién | Resultado esperado |
|---|---|---|---|---|---|
|P1 |Shodan |hostname:renfe.com |Censys / crt.sh |Envía la consulta a los servidores de Shodan. No contacta con Renfe. |Listado de servicios y puertos abiertos indexados pasivamente bajo el dominio corporativo. |
|P1 |Shodan |ssl:"renfe.com" |crt.sh |Consulta a los índices de certificados de Shodan. No toca al objetivo. |Detección de servidores web que presentan certificados emitidos para renfe.com o sus subdominios. |
|P1 |Shodan |ssl.cert.subject.cn:renfe.com |whois sobre ASN |Consulta pasiva de certificados con Common Name específico en Shodan. |Identificación de hosts que utilizan el certificado principal y verificación de la titularidad de su IP. |
|P2, P3 |FOCA |Descarga y análisis de entre 15 y 30 documentos PDF de renfe.com (obtenidos vía dorking de la A03). |Lectura manual de propiedades del documento |Peticiones HTTP estándar de descarga pública a portales web como visitante ordinario |Extracción de metadatos de autor, software de creación/conversión, rutas de almacenamiento y nombres de usuario. |
|P1 |crt.sh / Censys (Contraste) |Dominio renfe.com |Shodan |Consulta a bases de datos de transparencia de certificados (CT Logs). |Validación independiente de si una IP o certificado pertenece formalmente a Renfe o a un proveedor (ej. Cloudflare). |

### 3.2 Configuración y seguridad de la operación

**Cuenta de Shodan:** Uso de cuenta gratuita académica, sin vincular a perfiles personales y sin recurrir a opciones de escaneo bajo demanda (on-demand scan).

**Instalación y modo de FOCA:**

- Ejecución en máquina con Windows 64-bit y base de datos local.

- Modo de obtención: Análisis local de documentos previamente descargados o búsqueda pasiva vía motor Google, con límite fijado entre 15 y 30 documentos.

- Extensiones permitidas: Exclusivamente documentos ofimáticos (.pdf, .docx, .xlsx).

- Funciones estrictamente deshabilitadas: No se utilizarán los módulos de red (Network), resolución DNS forzada (Domains), plugins de enumeración ni rastreo activo de servidores.

**Carpeta de trabajo y minimización:**

- Los documentos analizados y la base de datos de FOCA residirán en un directorio local temporal (workspace_a04/temp_docs/), fuera del repositorio de Git.

- Todos los nombres de usuario extraídos en FOCA serán sustituidos en el informe por identificadores anónimos (USR-01, USR-02...).

- En todas las capturas de Shodan se ocultarán de forma opaca los dos últimos octetos de cualquier IP (XXX.XXX.XX.XX).

- Al concluir la práctica, los archivos PDF descargados y los proyectos temporales de FOCA serán eliminados de forma segura, conservando únicamente las capturas anonimizadas en evidencias/.

**Modalidad B · Fecha y hora de cierre del plan:**

---

## 4. Obtención

### 4.1 Registro de obtención


| ID | Herramienta | Consulta o acción exacta | Fecha y hora | Resultado | Límite | Evidencia |
|---|---|---|---|---|---|---|
| OBT-01 |Shodan |hostname:renfe.com    |2026-11-06 20:25 CET |323 resultados. Concentración en puerto 443 (311). Dominio de Akamai como CDN global (233) y Telefónica de España alojando servicios específicos como PlayRenfe. |Shodan refleja nodos pasivos indexados en caché; muchos son servidores edge del proveedor de CDN y no servidores de origen de Renfe. |EV-01.png |
| OBT-02 |Shodan |ssl:"renfe.com"    |2026-11-06 20:30 CET |303 resultados. Concentración casi total en puerto 443 (302) y 8443 (1). Identificación de proveedores perimetrales: Akamai (250), AWS (19) y presencia de ADIF (14). |Muestra hosts que presentan la cadena en el certificado; incluye proxies y servidores de terceros con certificados delegados |EV-02.png |
| OBT-03 |Shodan |ssl.cert.subject.cn:renfe.com |2026-11-06 20:35 CET |303 resultados idénticos al filtro general de SSL. Confirma que renfe.com está fijado como Common Name principal en los certificados activos. Persisten Akamai (250), AWS (19), ADIF (14) y Telefónica de España. |Muestra solo hosts con el CN exacto; no revela servidores con certificados emitidos exclusivamente a subdominios de tercer nivel si usan otro CN. |EV-03.png |

### 4.2 Shodan

| Consulta | Resultados | Facetas relevantes | Referencia |
|---|---:|---|---|
|hostname:renfe.com    |323 |Puertos: 443 (311), 80 (11). Orgs: Akamai (233). Países: EE. UU. (88), España (60). |OBT-01 / EV-01 |
|ssl:"renfe.com" |303 |Puertos: 443 (302), 8443 (1). Orgs: Akamai (250), AWS (19), ADIF (14). |OBT-02 / EV-02.png |
|ssl.cert.subject.cn:renfe.com |303 |Coincidencia exacta con filtro SSL. Confirma que renfe.com es el CN principal en todos los certificados. |OBT-03 / EV-03.png|

| Grupo | Servicios o puertos observados | Fechas de observación | Cómo se ha contrastado | Referencias |
|---|---|---|---|---|
| Del objetivo |Puertos 80 (HTTP 302) y 443 (HTTPS) asociados a playrenfe.renfe.com |2026-11-06 |Certificado SSL emitido a nombre de Renfe Operadora y resolución DNS oficial. |OBT-01, OBT-04 / EV-04.png |
| De un proveedor |Puerto 443 (HTTPS) con producto AkamaiGHost (CDN), servidores en AWS y red de Telefónica de España |2026-11-06 |Titularidad ASN de Akamai Technologies, Amazon y Telefónica de España S.A.U. |OBT-01, OBT-02 / EV-01.png, EV-02.png |
| Relación no demostrada |Nodos extranjeros que devuelven 400 Bad Request sin hostname directo o en rangos no asignados a contratos públicos. |2026-11-06 |Banners genéricos de CDN intermediarios sin confirmación de host origen. |OBT-01 / EV-01.png |

### 4.3 FOCA

**Documentos legacy sin sanear:** Los archivos solicitud_empresas.pdf y solicitud_individual.pdf datan de julio de 2008. Llevan más de 18 años publicados sin haber sido actualizados ni saneados, conservando el identificador del puesto de trabajo que los imprimió (PScript5.dll, Distiller 5.0.5).

**Heterogeneidad de software:** Se constata que la entidad no utiliza una pasarela centralizada de publicación que elimine metadatos antes de subir archivos a renfe.com, permitiendo identificar versiones concretas de software comercial y la existencia de herramientas de scripting interno (python-docx).

| Tipo de documento | Localizados | Analizados | Intervalo de fechas |
|---|---:|---:|---|
|PDF (Documentos corporativos, memorias, normativas y formularios) |15 |15 |2008-07-04 a 2026-09-17 |

| Categoría | Elementos | Patrón observado | Interpretación y límite | Referencia |
|---|---:|---|---|---|
| Usuarios |2 |Se identifican dos patrones: nombre y apellidos personales (USR-01) y código alfanumérico interno de empleado o puesto (USR-02: LRCMU84). |USR-01 evidencia autoría directa en documentos de diseño normativo. USR-02 refleja la nomenclatura interna de cuentas de usuario corporativas en puestos Windows. |OBT-06 / EV-06.png|
| Carpetas y rutas |0 |No se observan rutas locales absolutas de disco (C:...) ni montajes SMB expuestos directamente en los campos estándar de los PDFs. |Los motores de maquetación modernos (InDesign/Quartz) eliminaron las rutas locales durante la compilación del binario. |OBT-06 / EV-06.png |
| Impresoras |1 |Controlador de impresión PostScript (PScript5.dll Version 5.2.2). | Utilizado en documentos legados (solicitud_empresas.pdf, solicitud_individual.pdf) para generar PDFs mediante impresión virtual.|OBT-06 / EV-06.png |
| Software |6 |Ecosistema de diseño predominante: Adobe InDesign (v16.2 a v21.5), Adobe Illustrator (v24.0 a v28.5) y Microsoft Word. Uso de librerías automatizadas (python-docx). Herramientas legacy: Acrobat Distiller 5.0.5. |El departamento de comunicación utiliza la suite profesional de Adobe para memorias y guías. Destaca la generación programática de documentos mediante scripts Python en convocatorias técnicas (bases-hackathon). |OBT-06 / EV-06.png |
| Correos |0 |No se observan direcciones de correo electrónico corporativo incrustadas en los metadatos ofimáticos directos. |Los documentos analizados no conservan propiedades de correspondencia o mensajería activa. |OBT-06 / EV-06.png |
| Sistemas operativos |2 |Coexistencia de plataformas cliente: Windows (entornos de maquetación y ofimática legacy) y Macintosh / macOS (versión 26.5.1 Quartz PDFContext e InDesign Mac). |Revela una división operativa: puestos de diseño gráfico en entornos Apple y puestos administrativos/gestión en puestos Windows. |OBT-06 / EV-06.png |
| Servidores |1 |Motor gráfico de renderizado PDF de Apple: macOS Versión 26.5.1 Quartz PDFContext. |Indica generación directa de documentos finales exportados desde estaciones de trabajo macOS sin pasar por pasarelas centralizadas. |OBT-06 / EV-06.png |

### 4.4 Revisión de la elección

| Pregunta | Prevista | Utilizada | Evidencia obtenida | ¿Resuelve la pregunta? | Cambio justificado |
|---|---|---|---|---|---|
|P1 |Shodan (consultas con filtros y fichas) |Shodan |EV-01.png, EV-02.png, EV-03.png, EV-04.png |Sí |No hubo cambio; se aplicaron los filtros hostname:, ssl: y ssl.cert.subject.cn: respetando las restricciones de sector sensible. |
|P2 |FOCA (metadatos de software y sistemas) |Script Python local (pypdf) alternativo |EV-05.png (fallo BD), EV-06.png (extracción) |Sí |Sí; FOCA presentó incompatibilidad de arranque por falta de SQL Server local (Database not found). Se aplicó la alternativa prevista en el catálogo (extracción local con CLI/script) sobre 15 PDFs. |
|P3 |FOCA (usuarios y cuentas internas) |Script Python local (pypdf) alternativo |EV-06.png |Sí |Sí; misma justificación metodológica que en P2. El script extrajo los campos de autoría y perfiles de maquetación de los 15 documentos sin restricciones. |

---

## 5. Análisis e integración con la A03

### 5.1 Huella técnica

**Observado:** En Shodan se identifican más de 300 resultados asociados al dominio principal. La inmensa mayoría corresponden a nodos de red perimetral del CDN de Akamai Technologies (puerto 443 HTTPS), actuando como escudo y distribuidor de contenidos. Adicionalmente, se identifica un servicio directo (playrenfe.renfe.com) alojado en el ASN de Telefónica de España S.A.U., el cual presenta el puerto 80 (HTTP) redirigiendo a HTTPS (puerto 443) y exhibe un certificado SSL corporativo formal emitido a nombre de Renfe Operadora. No se detectan puertos administrativos (SSH, RDP, Telnet) ni paneles de bases de datos expuestos hacia Internet en los dominios corporativos evaluados.   
**Valoración:** Fiabilidad de la fuente alta (Shodan y certificados X.509 públicos); credibilidad confirmada. La huella técnica perimetral está fuertemente consolidada detrás de CDNs profesionales. Como limitación, la intermediación de Akamai impide observar la dirección IP real de los servidores web de origen. 
### 5.2 Huella documental

**Observado:** El análisis de metadatos sobre 15 documentos PDF públicos (con fechas de creación entre 2008 y 2026) evidencia la exposición de dos identificadores de usuario: un nombre propio formal (USR-01: Joan L. Díaz) en normativas de transporte y un identificador alfanumérico interno de empleado/puesto (USR-02: LRCMU84) en formularios de solicitud para empresas. Asimismo, se descubre la coexistencia de entornos operativos Windows y macOS, el empleo continuado de suites comerciales de diseño (Adobe InDesign, Illustrator) y la presencia de documentos históricos generados en 2008 mediante controladores de impresión antiguos (PScript5.dll, Acrobat Distiller 5.0.5) que siguen publicados sin sanitizar.   
**Valoración:** Fiabilidad alta (análisis de metadatos extraídos de los propios binarios oficiales); credibilidad confirmada. Pone de manifiesto la ausencia de una pasarela centralizada de publicación que desinfecte metadatos ofimáticos con carácter previo a su subida a la web pública.

### 5.3 Ficha del objetivo actualizada

| Campo | Dato en la A03 | Cambio en la A04 | Referencia |
|---|---|---|---|
|Infraestructura CDN/WAF |Cloudflare identificado a nivel de DNS (A03 OBT-06) |Modificado: El tráfico web perimetral HTTPS se distribuye masivamente a través de la infraestructura CDN de Akamai Technologies (233+ activos). |OBT-01, OBT-02 |
|Servicios e IPs específicas |No identificados en la A03 |Añadido: Descubrimiento de infraestructura dedicada para el portal playrenfe.renfe.com en rango perteneciente a Telefónica de España S.A.U |OBT-01, OBT-04 |
|Puestos clientes y usuarios |No identificados en la A03 |Añadido: Identificación de estructura de cuentas internas (USR-02: LRCMU84) y puestos macOS/Windows. |OBT-06 |


### 5.4 Grafo final

| Relación | Tipo | Referencia |
|---|---|---|
|renfe.com $\to$ Renfe Viajeros, S.M.E., SA |Declarada (A03) |A03 OBT-01 / BOE-A-2026-17682 |
|renfe.com $\to$ Cloudflare (DNS) |Observada (A03) |A03 OBT-06 / EV-06.png (A03) |
|renfe.com $\to$ Redes Oficiales (YouTube, LinkedIn) |Observada (A03) |A03 OBT-07 |
|renfe.com $\to$ Akamai Technologies (CDN global) |Observada (A04) |OBT-01, OBT-02 / EV-01.png, EV-02.png |
|renfe.com $\to$ playrenfe.renfe.com |Observada (A04) |OBT-01, OBT-04 / EV-04.png |
|playrenfe.renfe.com $\to$ Telefónica de España S.A.U. |Observada (A04) |OBT-04 / EV-04.png |
|renfe.com $\to$ Adobe InDesign / Illustrator (Software maquetación) |Observada (A04) |OBT-06 / EV-06.png |

### 5.5 Valoración de hallazgos clave

| Hallazgo | Referencias | Fiabilidad de la fuente | Credibilidad de la información | Hecho o inferencia | Contraste independiente |
|---|---|---|---|---|---|
| Distribución masiva del tráfico perimetral a través de Akamai Technologies|OBT-01, OBT-02|Alta (Shodan) |Confirmada |Hecho |Cabeceras HTTP (AkamaiGHost) y titularidad ASN de los rangos. |
|Alojamiento del portal PlayRenfe en red de Telefónica |OBT-04 |Alta (Shodan / Whois)|Confirmada |Hecho |Certificado SSL emitido a Renfe Operadora sobre IP de Telefónica. |
|Exposición de identificadores y nombres internos en documentos públicos |OBT-05 |Alta (Binarios oficiales) |Confirmada |Hecho |Extracción directa de metadatos en ficheros descargados de renfe.com. |
|Pervivencia de formularios obsoletos sin actualización desde 2008 |OBT-05 |Alta (Metadatos PDF) |Confirmada |Hecho |Fechas de creación y compilación registradas por Acrobat Distiller 5.0. |

---

## 6. Perspectiva del atacante y recomendaciones

| Información visible | Referencia | Cómo podría aprovecharla un atacante | A qué afectaría | Medida defensiva | Prioridad |
|---|---|---|---|---|---|
|Nombres de usuario y patrones de cuentas internas (USR-01, USR-02) en metadatos |OBT-05 |Elaboración de diccionarios específicos para ataques de fuerza bruta/password spraying contra paneles de acceso o campañas de spear phishing dirigidas de alta credibilidad. |Confidencialidad de credenciales e integridad de accesos internos. |Implementar un pipeline de sanitización automática (eliminación de metadatos EXIF/XMP) antes de la publicación web y exigir doble factor de autenticación (MFA) en todos los accesos. |Alta |
|Identificación de IP directa y servidor de PlayRenfe en Telefónica |OBT-04 |Intento de elusión de las defensas perimetrales y WAF del CDN general atacando directamente la infraestructura subyacente. |Disponibilidad del servicio a bordo de trenes e integridad de la plataforma. |Restringir el tráfico entrante hacia la IP de origen permitiendo exclusivamente peticiones procedentes de los proxies autorizados de la entidad. |Alta |
|Versiones concretas de software expuestas en documentos (ej. InDesign, Distiller 5.0) |OBT-05 |Reconocimiento de versiones de software cliente para el envío de ficheros señuelo maliciosos específicamente adaptados a vulnerabilidades de esas suites. |Seguridad del endpoint del personal de administración y diseño. |Estandarización de las estaciones de trabajo y actualización periódica de suites ofimáticas |Media |
|Exposición de formularios no actualizados desde 2008 (solicitud_empresas.pdf) |OBT-05 |Desorientación de clientes corporativos mediante procesos administrativos obsoletos o aprovechamiento de canales de recepción desatendidos. |Reputación de la entidad y calidad del servicio al cliente. |Retirada y sustitución periódica de formularios legacy por formularios web interactivos y controlados. |Baja |
|Concentración de certificados SSL en Akamai y AWS con renfe.com en el CN | OBT-01, OBT-02|Monitorización de logs de transparencia de certificados (CT logs) para descubrir de forma inmediata nuevos subdominios de pruebas o desarrollo (dev.renfe.com, prep.renfe.com).    |Exposición de entornos no productivos. |Aplicar certificados comodín (wildcard) en entornos de desarrollo y restringir el acceso a entornos previos mediante VPN interna. |Media |

**Qué no cubren estas recomendaciones:**
Estas medidas no cubren vulnerabilidades internas de día cero (0-day) en el software de los servidores de origen, fallos de configuración en las redes de señalización ferroviaria (redes OT/SCADA aisladas del perímetro web analizado) ni ataques originados por empleados desleales con acceso físico o lógico legítimo.
---

## 7. Limitaciones, datos descartados e incidencias

**Limitaciones:** El uso masivo de CDN (Akamai) oculta la dirección IP real de la mayoría de servidores de producción de Renfe. No se realizaron escaneos de puertos directos ni comprobación de vulnerabilidades sobre los hosts para no vulnerar el marco pasivo de la actividad.   
**Datos descartados:** Se descartaron nodos IP internacionales que devolvían errores genéricos HTTP 400 sin mostrar hostnames directos ni certificados atribuibles formalmente a Renfe.   **Incidencias y alternativas aplicadas:** Al intentar iniciar FOCA v3.4 se produjo un fallo por ausencia de base de datos SQL Server local (Database not found). Conforme al procedimiento alternativo autorizado en el catálogo, se sustituyó por la extracción local automatizada mediante script de metadatos sobre 15 documentos. No hubo incidencias de seguridad ni detección de datos especialmente sensibles que requirieran reporte confidencial.

---

## 8. Índice de evidencias

| Evidencia | Qué muestra | Fila del registro | Qué se ha ocultado |
|---|---|---|---|
|EV-01 |Consulta hostname:renfe.com en Shodan con facetas de puertos y CDN Akamai |OBT-01 |Dos últimos octetos de las IPs y nombre de cuenta de Shodan. |
|EV-02 |Consulta ssl:"renfe.com" mostrando resultados agregados y presencia de ADIF y AWS |OBT-02 |Dos últimos octetos de las IPs y datos de sesión de Shodan. |
|EV-03 |Consulta ssl.cert.subject.cn:renfe.com validando el Common Name principal |OBT-03 |Dos últimos octetos de las IPs y sesión de Shodan |
|EV-04 |Ficha detallada de la IP de PlayRenfe alojada en Telefónica de España |OBT-04 |Dos últimos octetos de la IP principal y sesión de Shodan. |
|EV-05 |Captura de error de arranque de FOCA por falta de servicio SQL Server |OBT-05 |Marco de ventana del sistema operativo. |
|EV-06 |Extracción CLI de metadatos de los 15 PDFs analizados |OBT-06 |Nombre de persona real detectado en el campo Autor (Joan L. Díaz). |
|EV-07 |Grafo final integrado en Maltego con relaciones técnicas y documentales |Fases 4 y 5 |Barras de interfaz de Maltego y barra de tareas del sistema.   |
---

## 9. Uso de inteligencia artificial

Ver [registro-ia.md](registro-ia.md).

---

## Comprobación

- [ ] Trabajo sobre el mismo objetivo y la misma modalidad que en la A03.
- [ ] Cerré los apartados 2 y 3 antes de la obtención: *commit* en la modalidad A, fecha de cierre en la modalidad B.
- [ ] Cada afirmación lleva su referencia `OBT` y la he comprobado.
- [ ] Las capturas están recortadas y anonimizadas, con las IP ocultas.
- [ ] Entrego antes del viernes 6 de noviembre a las 23:59.
- [ ] Modalidad A: solo he modificado `entregas/apellidoNombre/A04/`. Modalidad B: nada está en el repositorio del curso.
