# A03 · Huella pública

## Estudiante

- Nombre: Cayetano Castillo Ruiz
- Carpeta personal: entregas/castilloCayetano/A03/
- Modalidad: Modalidad A Organización
- Objetivo: Entidad Pública Empresarial Renfe-Operadora (Grupo Renfe)
- ¿Es el objetivo de tu proyecto final?: No
- Punto de partida (dominio principal o identificadores propios): renfe.com
- Periodo de obtención, con zona horaria: 30/10/2026 UTC+1 (Madrid)

---

## 1. Resumen ejecutivo

Se ha ejecutado una auditoría de huella pública sobre la Entidad Pública Empresarial Renfe-Operadora (renfe.com) mediante fuentes abiertas exclusivamente pasivas, orientada a evaluar los riesgos de reconocimiento previo y suplantación frente a un actor hostil. Se identificó la estructura societaria oficial de su principal filial operadora (Renfe Viajeros, S.M.E., SA) a través de registros públicos oficiales (BOE), descartando homónimos no relacionados. A nivel de canales, se constata una superficie web amplia estructurada en múltiples subdominios operativos (grupo, blog, empleo) protegidos perimetralmente mediante Cloudflare, observándose la persistencia de interfaces de autenticación y portales de selección indexados en buscadores. Asimismo, la documentación contractual pública expone relaciones técnicas con terceros y proveedores de consultoría. Se recomienda reforzar la política de indexación sobre paneles secundarios (noindex), exigir autenticación multifactor y desplegar monitorización proactiva de certificados y dominios para neutralizar vectores de phishing y fraude corporativo.

| Pregunta | Respuesta breve | Confianza | Referencias |
|---|---|---|---|
|P1. Estructura societaria y filiales |Razón social confirmada como Renfe Viajeros, S.M.E., SA (BOE-A-2026-17682), estructurada como sociedad mercantil estatal de transporte. |Alta |OBT-01 / EV-01 |
|P2. Canales, subdominios y activos web |Superficie distribuida en subdominios funcionales (blog, grupo, empleo) con interfaces de autenticación accesibles desde índices públicos. |Alta |OBT-02, OBT-04, OBT-05 / EV-02, EV-04, EV-05 |
|P3. Relaciones, terceros y proveedores |Protección perimetral delegada en Cloudflare y vínculos de suministro técnico y asistencial documentados en pliegos públicos (Ineco). |Alta |OBT-03, OBT-06, OBT-07 / EV-03, EV-06, EV-07 |

---

## 2. Encargo

### 2.1 Objetivo elegido

### 2.2 Requerimiento

| Componente | Contenido |
|---|---|
| Destinatario |Responsable de Seguridad de la Información (CISO / Dirección de Ciberseguridad) de Renfe. |
| Decisión |Determinar qué activos, canales web y relaciones institucionales expuestas pueden ser aprovechados por un actor hostil para preparar ataques de ingeniería social, suplantación o reconocimiento previo, y definir medidas defensivas de mitigación y reducción de superficie. |
| Objeto |La huella pública digital e institucional de Renfe-Operadora accesible mediante fuentes abiertas (OSINT). |
| Horizonte |Histórico consolidado y estado actual accesible en índices públicos. |
| Alcance |Dominios y subdominios corporativos públicos vinculados a renfe.com, perfiles oficiales en redes y registros mercantiles/oficiales de la entidad matriz y sus sociedades operativas. |
| Exclusiones |Datos personales de viajeros, tripulación y empleados; materiales o foros relacionados con incidentes operativos recientes; escaneos activos de puertos, vulnerabilidades o servicios. |
| Producto |Informe técnico de huella pública con registro trazable de obtención, grafo de entidades y matriz de perspectiva del atacante. |

**Requerimiento en una frase:**
Evaluar la exposición exterior de los canales web, la estructura societaria y las relaciones de Renfe-Operadora mediante fuentes abiertas para identificar vectores de suplantación y reconocimiento previo antes de que puedan ser explotados por terceros.

### 2.3 Preguntas de inteligencia

| Prioridad | Pregunta | Huella que cubre | Te ayuda a decidir |
|---:|---|---|---|
|1 |¿Cuál es la estructura societaria oficial de Renfe, qué filiales la componen y qué administradores o representantes figuran formalmente vinculados a la marca? |Corporativa / Institucional |Qué entidades jurídicas y marcas derivadas requieren supervisión de marca defensiva y monitorización contra registros fraudulentos. |
|2 |¿Qué dominios, subdominios y canales digitales oficiales tiene expuestos Renfe, y qué servicios obsoletos o desatendidos siguen indexados o archivados? |Canales |Qué portales, portales de empleo/proveedores o entornos legacy deben ser saneados, redirigidos o retirados de la visibilidad pública. |
|3 |¿Qué vínculos institucionales, proveedores tecnológicos o plataformas de terceros son reconocibles a través de su huella y documentos públicos? |Relaciones |Dónde reforzar medidas contra vectores de suplantación de identidad corporativa (phishing / BEC) o ataques a la cadena de suministro. |

---

## 3. Plan de obtención

### 3.1 Herramientas por pregunta

| Pregunta | Herramienta | Alternativa descartada y motivo | Entrada | Qué expone y a quién | Resultado esperado |
|---|---|---|---|---|---|
|P1|BORME / OpenCorporates |Informes de solvencia de pago (Axesor, Informa): descartados para evitar costes y uso de plataformas con autenticación invasiva. |"Renfe-Operadora", "Renfe Viajeros" |Envía la cadena de búsqueda a los servidores de OpenCorporates/Boletín Oficial. No interactúa con Renfe. |Denominación social exacta, CIF, filiales formalmente constituidas e historial de publicaciones societarias. |
|P2|Google con operadores |Motores de indexación pasiva de certificados (crt.sh): descartados en esta fase porque el dorking permite identificar directamente contenidos y metadatos accesibles. |site:renfe.com -www, site:renfe.com filetype:pdf, site:renfe.com inurl:login |Envía las directivas a Google. No contacta con los servidores de Renfe. |Inventario de subdominios, áreas de acceso restringido públicas y documentos expuestos. |
|P2|Wayback Machine |Archive.today: descartado por menor volumen y menor granularidad histórica en portales corporativos españoles. |[https://www.renfe.com](https://www.renfe.com) |Envía la URL consultada a Internet Archive. No genera peticiones al objetivo. |Evolución de portales antiguos, subdominios en desuso o cambios estructurales en la exposición de canales. |
|P3|Maltego Community |SpiderFoot / Recon-ng: descartados para asegurar visualización clara de entidades y grafos conformes a la rúbrica sin lanzar sondas activas. |Dominio renfe.com y nombres de filiales |Consultas DNS públicas pasivas y llamadas API a transformaciones pasivas preconfiguradas. |Grafo con entidades categorizadas (dominios, filiales, resoluciones de nombres, correos de contacto público). |
|P3|Google Lens / TinEye (Opcional) |Intelligence X: descartada en esta fase para evitar el riesgo de consultar filtraciones o credenciales restringidas por las normas de la práctica. |Favicon corporativo o logotipos de campañas específicas de Renfe |Envía la imagen a los servidores del buscador. No toca al objetivo. |Comprobación de sitios externos o campañas que reutilicen identidades visuales oficiales. |

### 3.2 Herramientas que no se usan

| Herramienta | Motivo |
|---|---|
|Intelligence X / Serus |Descartadas para garantizar el cumplimiento estricto del límite del apartado 3.1 (prohibición de buscar credenciales, filtraciones o datos de incidentes). |
|OpenSanctions |Descartada por no ajustarse a las preguntas de inteligencia formuladas: Renfe es un operador estatal regulado sin alertas en listas internacionales de sanciones de cumplimiento directo para esta auditoría. |
|Babel Street / Hunchly |Descartadas por requerir licencias comerciales de pago o no aplicar directamente a la modalidad de huella organizativa abierta requerida en la práctica. |

### 3.3 Configuración y seguridad de la operación

**Modalidad B · Fecha y hora de cierre del plan:** (Modalidad tipo A)

**Identidad de investigación:** Navegación en perfil de análisis sin sesión iniciada en cuentas personales (Google Sandbox / perfil aislado).

**Navegador y perfil:** Firefox / Brave en ventana privada, con bloqueo de telemetría y geolocalización desactivada. Extensiones de protección de cabeceras habilitadas.

**Carpeta de trabajo:** Entorno local organizado fuera del árbol de Git (workspace_a03/evidencias/), asegurando que solo los archivos anonimizados y procesados se copien a entregas/[cayetanoCastillo]/A03/evidencias/.
---

## 4. Obtención

### 4.1 Registro de obtención

| ID | Herramienta | Consulta o acción exacta | Fecha y hora | Resultado | Límite | Evidencia |
|---|---|---|---|---|---|---|
| OBT-01 |OpenCorporates y BOE (sustitución justificada) |1. OpenCorporates: "Renfe" / "Renfe Viajeros" (España). 2. BOE: "RENFE VIAJEROS" |2026-10-30 16:25 CET |En OpenCorporates se obtienen 0 resultados para la matriz y homónimos no relacionados (Renfe Corma, Renfe Iñigo). En BOE se localiza la disposición oficial BOE-A-2026-17682, acreditando la entidad formal Renfe Viajeros, S.M.E., SA. |OpenCorporates carece de cobertura actualizada sobre sociedades mercantiles estatales españolas; requiere contrastar con la fuente oficial primaria (BOE/BORME). |EV-01,EV-01a,EV-01b |
| OBT-02 |Google |site:renfe.com -www |2026-10-30 16:42 CET |Detección de subdominios operativos: grupo.renfe.com, blog.renfe.com y renfeviajes.renfe.com |Dependencia de la indexación activa del motor de búsqueda; no descubre subdominios internos no enlazados ni entornos protegidos por robots.txt. |EV-02|
| OBT-03 |Google |site:renfe.com filetype:pdf (pliego OR licitacion OR convenio OR contrato) |2026-10-30 16:50 CET |Indexación pública de documentos oficiales: condiciones generales de transporte, pliegos del Tribunal de Cuentas y resoluciones con mención a terceros (Ineco). |Muestra solo ficheros indexados en la raíz y subdominios expuestos; no accede a repositorios documentales autenticados. |EV-03 |
| OBT-04 |Google |site:renfe.com "iniciar sesión" OR "identifícate" (tras fallo de dork inicial) |2026-10-30 17:02 CET |Localización de interfaces de autenticación: portal Wifi PlayRenfe (acceso por tarjeta/billete) y convocatorias internas en empleo.renfe.com |Solo detecta portales con enlaces públicos o metadatos rastreables; no localiza accesos en VPN o intranets segmentadas. |EV-04, EV-04a |
| OBT-05 |Wayback Machine |[http://www.renfe.com](http://www.renfe.com) y [https://www.renfe.com/es/es](https://www.renfe.com/es/es) |2026-10-30 17:15 CET |Comparativa temporal: snapshot de 2016 (campaña 75 aniversario, fidelización "+renfe joven 50") vs snapshot de 2026 (nueva arquitectura web unificada con pasarela de billetes integrada).|Preservación incompleta de elementos dinámicos, scripts de sesión y llamadas API en el histórico preservado. |EV-05, EV-05a |
| OBT-06 |Maltego |Dominio renfe.com y mapeo de infraestructura/relaciones |2026-10-30 17:22 CET |Estructuración visual de relaciones: CDN/DNS en Cloudflare, perfiles oficiales en redes (YouTube, LinkedIn) y vinculación corporativa con Renfe Viajeros S.M.E., SA. |La versión Community limita transformaciones automáticas directas; requiere mapeo e integración de entidades obtenidas por fuentes previas. |EV-06 |
| OBT-07 |Google Lens |Búsqueda inversa del isotipo corporativo de Renfe |2026-10-30 17:30 CET |Identificación de perfiles de la marca en plataformas de terceros (YouTube, LinkedIn) y referencias en medios de comunicación y enciclopedias abiertas. |Cobertura sesgada hacia dominios con alta reputación; no detecta de forma inmediata dominios de suplantación recientes sin indexar. |EV-07 |

### 4.2 Resultados por herramienta

#### Google con operadores:

**Pregunta respondida:** P2 (Canales, subdominios y activos expuestos) y P3 (Documentos y relaciones).
**Resultado:** Se identificaron subdominios funcionales (blog.renfe.com, grupo.renfe.com, renfeviajes.renfe.com, empleo.renfe.com) (OBT-02, OBT-04) y una alta exposición de ficheros PDF de carácter contractual y licitatorio con referencias a entidades colaboradoras como Ineco o el Tribunal de Cuentas (OBT-03).
**Límite:** El buscador refleja solo lo que sus rastreadores han indexado; no permite confirmar la totalidad de subdominios existentes ni estados de puertos.

#### Wayback Machine:

**Pregunta respondida:** P2 (Evolución de canales y exposición histórica).
**Resultado:** Contraste directo entre febrero de 2016 y octubre de 2026 (OBT-05). Se observa una transición desde portales desglosados con esquemas de fidelización legacy ("+renfe joven 50") hacia una plataforma web responsiva, centralizada y con segmentación por producto (/es/es).
**Límite:** Muchas llamadas asíncronas y pasarelas de pago no están operativas en las copias archivadas, impidiendo auditar formularios históricos funcionales.

#### Fuente societaria (OpenCorporates / BOE):

**Pregunta respondida:** P1 (Estructura legal y filiales oficiales).
**Resultado:** OpenCorporates presentó una laguna de indexación para empresas públicas estatales españolas (OBT-01). La consulta directa en BOE confirmó la personalidad jurídica de la principal filial operadora: Renfe Viajeros, S.M.E., SA (disposición BOE-A-2026-17682) (OBT-01).
**Límite:** El BOE aporta resoluciones legales oficiales y societarias, pero no mapea dependencias informáticas ni organigramas operativos internos.

#### Maltego:

**Pregunta respondida:** P3 (Grafo de relaciones e infraestructura).
**Resultado:** Consolidación gráfica de la presencia corporativa conectando el dominio renfe.com con su capa perimetral (Cloudflare), canales externos (YouTube, LinkedIn) y la filial mercantil declarada (OBT-06).
**Límite:** Ausencia de transformaciones comerciales automáticas en la versión gratuita; el grafo debió enriquecerse con contraste documental.

#### Google Lens (Herramienta opcional):

**Pregunta respondida:** P3 (Presencia de marca y canales en terceros).
**Resultado:** Verificación de canales oficiales en plataformas externas (YouTube, LinkedIn) y presencia mediática sobre la evolución del logotipo corporativo (OBT-07).
**Límite:** Alta concentración en sitios de noticias y portales principales; limitada capacidad para detectar dominios maliciosos recién desplegados.

### 4.3 Revisión de la elección

| Pregunta | Herramienta prevista | Herramienta utilizada | Evidencia obtenida | ¿Resuelve la pregunta? | Cambio justificado |
|---|---|---|---|---|---|
|P1 |OpenCorporates |OpenCorporates -> BOE |EV-01.png |Sí |Sí; OpenCorporates carecía de datos sobre la entidad mercantil estatal, recurriendo al registro oficial primario (BOE) |
|P2 |Google dorks |Google dorks |EV-02.png, EV-03.png, EV-04.png |Sí |No hubo cambio; se ajustó la consulta de autenticación por rigidez sintáctica inicial del buscador.    |
|P2 |Wayback Machine |Wayback Machine |EV-05.png |Sí |No hubo cambio; permitió contrastar la evolución 2016 vs 2026. |
|P3 |Maltego |Maltego |EV-06.png |Sí |No hubo cambio; estructuración de entidades técnicas y societarias en grafo. |
|P3 |Google Lens |Google Lens |EV-07.png |Sí |No hubo cambio; validación de perfiles corporativos en plataformas de terceros. |

---

## 5. Análisis de la huella

### 5.1 Ficha del objetivo

| Campo | Dato | Referencia | Fecha del dato | Precaución |
|---|---|---|---|---|
|Nombre legal matriz |Entidad Pública Empresarial Renfe-Operadora |OBT-01 |2026-08-13 |Entidad de derecho público; sujeta a regulación estatal específica.|
|Filial operativa principal |Renfe Viajeros, S.M.E., SA |OBT-01 |2026-08-13 |Sociedad Mercantil Estatal encargada de transporte de viajeros. |
|Dominio principal |renfe.com |OBT-02, OBT-06 |2026-10-30 |Dominio central corporativo protegido tras proxy/CDN Cloudflare.|
|Subdominios oficiales identificados |grupo.renfe.com, blog.renfe.com, renfeviajes.renfe.com, empleo.renfe.com |OBT-02, OBT-04 |2026-10-30 |Exposición de áreas funcionales y portales de selección con sesiones independientes. |
|Canales en plataformas externas |YouTube (Renfe), LinkedIn (Renfe) |OBT-06, OBT-07 |2026-10-30 |Cuentas oficiales verificadas susceptibles de monitorización de identidad de marca. |
|Proveedores y socios observados |Cloudflare Inc. (CDN/DNS), Ineco (asistencia técnica según pliegos) |OBT-03, OBT-06  |2026-10-30 |Proveedores de infraestructura y consultoría técnica expuestos documentalmente. |

### 5.2 Huella por dimensiones


#### Corporativa o profesional

**Observado:** La denominación formal regulada es Renfe Viajeros, S.M.E., SA, vinculada a convenios con organismos ministeriales según constata el BOE (BOE-A-2026-17682) (OBT-01).   **Valoración:** Fiabilidad de la fuente máxima (fuente primaria oficial, boletín estatal); credibilidad de la información confirmada. La huella societaria está normalizada institucionalmente y no presenta incongruencias legales. 

#### De canales

**Observado:** Se constata la segmentación del dominio principal en subdominios de producto y corporativos (grupo.renfe.com, blog.renfe.com, empleo.renfe.com) (OBT-02, OBT-04). En Wayback Machine se documenta la transición estructural y de imagen de marca desde 2016 a 2026 (OBT-05).   **Valoración:** Fiabilidad de la fuente alta (índices directos de Google e Internet Archive); credibilidad confirmada. La superficie web es extensa y mantiene portales secundarios que gestionan accesos e inscripciones (empleo.renfe.com).   

#### De relaciones

**Observado:** Exposición de contratos y pliegos técnicos en PDF que detallan la participación de empresas públicas colaboradoras como Ineco (OBT-03), además de la delegación del perímetro de tráfico web y DNS en infraestructura de Cloudflare (OBT-06). Canales externos centralizados en LinkedIn y YouTube (OBT-07).   **Valoración:** Fiabilidad alta; credibilidad contrastada. La publicación de pliegos técnicos y resoluciones es obligatoria por transparencia administrativa, pero expone nombres de terceros y estructuras de proyectos.

### 5.3 Grafo de relaciones

| Relación | Tipo | Referencia |
|---|---|---|
|renfe.com -> Cloudflare (DNS/CDN) |Observada |OBT-06 |
|renfe.com $\to$ YouTube Oficial (Renfe) |Observada |OBT-06, OBT-07 |
|renfe.com $\to$ LinkedIn Corporativo (Renfe)    |Observada |OBT-06, OBT-07 |
|Renfe-Operadora $\to$ Renfe Viajeros, S.M.E., SA |Declarada|OBT-01 / BOE-A-2026-17682    |

### 5.4 Valoración de hallazgos clave

| Hallazgo | Referencias | Fiabilidad de la fuente | Credibilidad de la información | Hecho o inferencia | Contraste independiente |
|---|---|---|---|---|---|
|Razón social regulada como Sociedad Mercantil Estatal (Renfe Viajeros, S.M.E., SA) |OBT-01    |Alta (BOE) |Confirmada |Hecho |Publicación oficial en sede electrónica gubernamental. |
|Superficie web dispersa en múltiples subdominios operativos (empleo, blog, grupo) |OBT-02, OBT-04 |Alta (BOE) |Confirmada |Hecho |Resolución de DNS directa y carga de certificados TLS. |
|Utilización de servicios de protección perimetral y resolución Cloudflare |OBT-06 |Alta (Resolución DNS/Maltego) |Confirmada |Hecho |Registros NS autoritativos y trazas HTTP observables. |
|Posible debilidad por portales de login secundarios desatendidos o con sesiones caducadas indexadas |OBT-04 |Media-Alta (Caché y fragmentos indexados de Google) |Probable |Inferencia |Requiere auditoría interna de políticas de expiración y directivas noindex. |

---

## 6. Perspectiva del atacante

| Información visible | Referencia | Cómo podría aprovecharla un atacante | A qué afectaría | Medida defensiva | Prioridad |
|---|---|---|---|---|---|
|Subdominios con formularios de acceso y convocatorias (empleo.renfe.com) |OBT-04 |Diseño de campañas de ingeniería social o phishing dirigido suplantando procesos de selección o alertas de sesión caducada para captar credenciales de candidatos y personal. |Confidencialidad de credenciales e imagen corporativa. |Implementar autenticación multifactor (MFA), aplicar cabeceras noindex en endpoints de autenticación y monitorizar dominios typosquatting similares. |Alta |
|Documentos PDF indexados con pliegos, contratos y mención a socios tecnológicos (ej. Ineco) |OBT-03 |Reconocimiento de relaciones de confianza para orquestar ataques de suplantación de identidad en cadena de suministro (Business Email Compromise / fraude del CEO o facturación falsa). |Integridad financiera y confianza en comunicaciones B2B |Sanitización sistemática de metadatos en documentos antes de su publicación y verificación estricta fuera de banda de cambios de cuentas/proveedores. |Media |
|Canales oficiales y logotipos corporativos indexados en repositorios públicos |OBT-06, OBT-07 |Clonación fidedigna de la identidad visual de Renfe para montar páginas de venta de billetes falsas o señuelos fraudulentos de ofertas de empleo. |Reputación de la entidad y seguridad económica de usuarios externos. |Despliegue de servicios de Brand Protection y monitorización pasiva de certificados TLS de nueva emisión (Certificate Transparency logs). |Media |

---

## 7. Limitaciones, datos descartados e incidencias

**Preguntas no respondidas por completo:** No fue posible cartografiar la totalidad de servidores internos ni pasarelas no indexadas debido a la política defensiva de no realizar escaneos activos de puertos ni sondeos que tocasen al objetivo.
**Datos descartados:** En OBT-01 se descartaron los resultados de homónimos societarios en OpenCorporates (Renfe Corma SA, Renfe Iñigo SA) al constatar que eran personas jurídicas no vinculadas al grupo estatal.
**Límites de alcance y minimización:** Se aplicó estrictamente el apartado 3.1: no se investigaron datos personales de viajeros, tripulación ni empleados que pudieran aparecer en noticias o foros. En Maltego se evitó el despliegue de transformaciones sobre brechas o credenciales ajenas.
**Incidencias:** Ninguna incidencia de seguridad durante la obtención. No se detectaron fugas de credenciales en los canales auditados ni fue necesario reportar por el canal privado.
---

## 8. Índice de evidencias

| Evidencia | Qué muestra | Fila del registro | Qué se ha ocultado |
|---|---|---|---|
|EV-01 |Documento oficial BOE-A-2026-17682 acreditando a Renfe Viajeros S.M.E., SA |OBT-01 |Barras de herramientas, marcadores y sesión del navegador web. |
|EV-02 |Resultados del dork site:renfe.com -www mostrando subdominios |OBT-02 |Barra de usuario de Google y datos de personalización del navegador. |
|EV-03 |Resultados de indexación de PDFs corporativos y pliegos |OBT-03 |Sesión de usuario de Google. |
|EV-04 |Resultados de búsqueda de interfaces de inicio de sesión y empleo |OBT-04 |Perfil del navegador y datos de sesión de Google. |
|EV-05 |Comparativa histórica en Wayback Machine (snapshots 2016 vs 2026) |OBT-05 |Barra de tareas del sistema operativo y extensiones activas del navegador. |
|EV-06 |Grafo técnico de relaciones exportado en Maltego |OBT-06 |Paneles laterales de la interfaz de Maltego y barra de tareas. |
|EV-07 |Resultados de búsqueda inversa en Google Lens con el isotipo de la marca |OBT-07 |Interfaz externa del navegador y sesión de usuario.    |

---

## 9. Uso de inteligencia artificial

Ver [registro-ia.md](registro-ia.md).

---

## Comprobación

- [ ] El objetivo cumple los requisitos de mi modalidad y no investigo a ninguna otra persona.
- [ ] Cerré los apartados 2 y 3 antes de la obtención: *commit* en la modalidad A, fecha de cierre en la modalidad B.
- [ ] Cada afirmación lleva su referencia `OBT` y la he comprobado.
- [ ] Las capturas están recortadas y anonimizadas.
- [ ] Entrego antes del viernes 30 de octubre a las 23:59.
- [ ] Modalidad A: solo he modificado `entregas/apellidoNombre/A03/`. Modalidad B: nada está en el repositorio del curso.
