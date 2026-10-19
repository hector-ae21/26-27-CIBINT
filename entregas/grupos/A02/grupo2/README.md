# Plan de investigación · Grupo 2 · Naturgy

## Ficha del plan

| Campo | Contenido |
| --- | --- |
| Grupo | 2 |
| Caso | Filtración de datos de clientes de Naturgy a través de un proveedor y posterior oferta de venta, mayo y septiembre de 2026 |
| Material de partida | `casos/naturgy`: `N01`–`N12` y `F01`–`F06` |
| Portavoz | Sergio Rodríguez (propuesto por el equipo) |
| Miembros del equipo | José Luis de la Asunción, Sergio Rodríguez y Alejandro Ateca |

---

## 1. Resumen del plan

El presente plan de investigación tiene como objetivo esclarecer el alcance, la verosimilitud y el impacto de la filtración de datos notificada por Naturgy en mayo de 2026, evaluando su posible relación con la oferta de una base de datos de 74 GB en septiembre del mismo año atribuida al alias «spain». La finalidad es determinar los posibles riesgos de fraude derivados para poder emitir recomendaciones de protección informadas a los usuarios afectados. Para ello, se empleará exclusivamente la recopilación de información en fuentes abiertas (OSINT) pasivas en la web superficial, consultando boletines oficiales (AEPD, INCIBE-CERT), web corporativa y prensa tecnológica especializada. Se excluye categóricamente interactuar con los cibercriminales, descargar volcados ilícitos o acceder a foros de la dark web. La investigación se extenderá durante el periodo asignado para la actividad académica, garantizando siempre el principio de mínima intrusión y no injerencia.

## 2. Situación

### 2.1 Afirmaciones sobre el caso

| ID | Qué se afirma | Quién lo afirma | ¿Lo confirma alguien independiente? | Valoración |
| --- | --- | --- | --- | --- |
| N01 | Naturgy comunica en X un acceso no autorizado a una base de datos de un proveedor externo y afirma que el incidente no procede de sus sistemas propios | Naturgy, en X, recogido por Euronews (F01) | No. Euronews solo publica el mensaje en redes sociales proveniente de naturgy | Establecida en cuanto al mensaje comunicado por la empresa. Afirmada sin confirmar en cuanto a que no haya afectado a sistemas propios |
| N02 | Según la compañía, el incidente afecta aproximadamente al 3% de sus clientes en España | Naturgy, según Euronews (F01) e Infobae (F02) | No. Ninguna autoridad reguladora (como la AEPD) ni auditor externo independiente ha evaluado el porcentaje | Afirmada sin confirmar por la propia organización, es una estimación de la propia compañía |
| N03 | Los datos afectados son identificativos, contractuales y bancarios | Naturgy, en texto de agencia recogido por Infobae (F02) | No. Sale de la propia empresa | Afirmada sin confirmar por la entidad afectada |
| N04 | La compañía afirma que no se incluyen contraseñas ni credenciales de acceso al Área Cliente | Naturgy, según Euronews (F01) | No. Informacion comunicada de la empresa a traves de Euronews | Afirmada sin confirmar por la entidad afectada |
| N05 | La compañía afirma haber informado a la AEPD, a las fuerzas de seguridad y a los clientes afectados | Naturgy, en texto de agencia recogido por Infobae (F02) | No. Ni la AEPD ni las Fuerzas y Cuerpos de Seguridad confirman públicamente en esa fecha haber recibido dicha notificación | Afirmada sin confirmar por la entidad afectada, aun no hay comunicado por la AEPD ni fuerzas de seguridad |
| N06 | Medidas comunicadas: renovación de credenciales, bloqueo de accesos y auditorías de seguridad, también sobre los sistemas del proveedor | Naturgy, en texto de agencia recogido por Infobae (F02) | No. Informado por empresa afectada | Afirmada sin confirmar por la entidad afectada. |
| N07 | El titular visible del medio cifra los afectados en 200.000 clientes; la dirección web y los metadatos de la misma noticia indican «medio millón» | Escudo Digital (F03) | No procede, es una contradicción interna del propio medio | Cálculo o interpretación de un tercero con discrepancia interna |
| N08a | El sitio atribuye a las cifras oficiales de la compañía unos 200.000 afectados, equiparándolos a aproximadamente el 3% de su cartera | Ciberseguridad Creando Patria (F04) | No. Naturgy comunicó oficialmente el 3%, pero no la cifra absoluta de 200.000 clientes | Cálculo o interpretación de un tercero. El medio extrapola el porcentaje oficial (3%) a un número absoluto de clientes |
| N08b | El sitio recoge que un actor con el alias «Spain» alega haber accedido a 1,34 millones de contratos | El actor con el alias «Spain», según Ciberseguridad Creando Patria (F04) | No. El medio reproduce la afirmación del presunto atacante sin verificación | Afirmada sin confirmar por quien se atribuye el acceso. EL actor contradice de forma sustancial el alcance comunicado por la compañía |
| N09 | Un usuario con el alias «spain» afirma tener datos de unos 1,8 millones de clientes de Naturgy (74 GB) y los ofrece a la venta aportando capturas. El medio indica que Naturgy no ha confirmado el ataque | El usuario con el alias «spain» en un foro, recogido por ADSLZone (F05) | No. ADSLZone aclara expresamente que Naturgy no ha confirmado el ataque ni la autenticidad de los datos | Afirmada sin confirmar por el actor cibercriminal |
| N10 | El medio recoge la oferta a partir de una cuenta de X que monitoriza la web oscura y enumera como datos supuestos NIF, nombre, IBAN, correo, teléfono, dirección, identificadores de suministro y contratos. Indica que Naturgy no ha confirmado el hackeo | El Grupo Informático (F06), a partir de una cuenta de X que monitoriza la web oscura | No. Procede de intermediarios (cuenta de monitorización y medio tecnológico) | Afirmada sin confirmar de segunda/tercera mano. Detalla los campos supuestamente incluidos en la base comercializada |
| N11 | El medio recomienda a los clientes estar atentos a correos fraudulentos, SMS sospechosos y llamadas | El Grupo Informático (F06) | No procede | Recomendación preventiva del medio dirigida a usuarios para prevenir estafas derivadas del incidente |
| N12 | El sitio afirma que la compañía notificó el incidente a la AEPD dentro del plazo de 72 horas que exige el RGPD | Ciberseguridad Creando Patria (F04) | No. El medio no aporta número de expediente ni resolución de la AEPD | Afirmada sin confirmar por un medio especializado |

### 2.2 Lo que puede darse por establecido

1. **Comunicación oficial de Naturgy reconociendo una brecha de seguridad en un proveedor externo (N01, N02, N03, N04, N05, F01, F02):**
   El 1 de mayo de 2026, Naturgy hizo público a través de su cuenta oficial en X y mediante agencias de noticias que había sufrido un incidente consistente en un acceso no autorizado a una base de datos de un proveedor externo, asegurando que no afectaba a sus sistemas propios, que comprometía a un 3% aproximado de clientes en España con datos identificativos, contractuales y bancarios (sin contraseñas) y que había iniciado notificaciones a la AEPD, fuerzas de seguridad y clientes.
   - *Por qué se considera establecido:* Es un hecho objetivo y documentado que la propia organización afectada realizó estas declaraciones públicas oficiales, recogidas de forma coincidente por agencias y prensa generalista (F01, F02).

2. **Existencia material de una oferta de venta de una supuesta base de datos de Naturgy en septiembre de 2026 (N09, N10, F05, F06):**
   El 18 y 19 de septiembre de 2026, un actor bajo el alias «spain» publicó en un foro de la dark web una oferta de venta de un volcado de 74 GB con supuestos datos de 1,8 millones de clientes de Naturgy, adjuntando capturas como presunta prueba.
   - *Por qué se considera establecido:* La existencia del anuncio, el volumen de 74 GB y las capturas fueron detectados por cuentas de monitorización de ciberamenazas en la red oscura y recogidos de manera coincidente por publicaciones especializadas en tecnología (F05, F06).

3. **Incongruencia y disparidad objetiva en las cifras de afectados reportadas en las fuentes y por el vendedor (N02, N08, N09, F01, F04, F05):**
  Creando Patria tradujo el 3% a 200.000 y citó que el actor «Spain» alegaba 1,34 millones de contratos en mayo (N08). Los medios en septiembre reportaron una oferta de venta de 1,8 millones de clientes (N09).
   - *Por qué se considera establecido:* La discordancia de cifras es una evidencia documental directa y verificable en los propios textos y ofertas publicadas en las fuentes del caso (F01, F04, F05).

### 2.3 Lo que no se sabe

**Lagunas que una investigación desde fuentes abiertas (OSINT) SÍ podría ayudar a reducir:**

| ID | Laguna | ¿Se puede reducir mediante fuentes abiertas? | Motivo |
| --- | --- | --- | --- |
| L01 | Si la estructura y los campos visibles en las capturas de muestra del anuncio de septiembre corresponden a datos reales y vigentes de contratos de Naturgy, o si proceden de fuentes abiertas / filtraciones antiguas agregadas | Sí, en parte | Se pueden contrastar los formatos de campos, nomenclaturas de contratos y metadatos visibles en las capturas divulgadas lícitamente por medios especializados, sin interactuar con el actor ni descargar la base |
| L02 | El historial, reputación y nivel de credibilidad operativa del alias «spain» en foros de amenazas y repositorios de ciberinteligencia | Sí | Es posible rastrear menciones técnicas previas del alias en boletines de ciberseguridad abiertos, repositorios de Threat Intelligence y plataformas de seguimiento de actores para determinar si es un actor con trayectoria o un perfil oportunista / estafador |
| L03 | La existencia de pronunciamientos públicos, advertencias o resoluciones sancionadoras de la AEPD o de INCIBE-CERT en relación con la brecha comunicada por Naturgy en mayo (N05, N12) | Sí | Las resoluciones de la AEPD y las alertas de seguridad de INCIBE-CERT son documentos públicos accesibles en sus sedes electrónicas oficiales |
| L04 | Si existen análisis técnicos independientes que vinculen o descarten la relación entre el incidente del proveedor externo en mayo (N01) y la venta masiva de septiembre (N09) | Sí, en parte | Se pueden consultar informes de análisis forense publicados en abierto por firmas especializadas de seguridad que hayan monitorizado ambas alertas |

**Lagunas que una investigación desde fuentes abiertas (OSINT) NO podría reducir:**

| ID | Laguna | Motivo por el que no se puede reducir mediante fuentes abiertas |
| --- | --- | --- |
| L05 | La identidad mercantil del proveedor externo de Naturgy donde ocurrió el acceso no autorizado de mayo (N01) | No ha sido revelada públicamente. Conocerla exigiría acceder a contratos mercantiles privados, auditorías internas reservadas o comunicaciones confidenciales, lo que vulneraría el secreto empresarial y supondría una intromisión ilícita |
| L06 | La autenticidad íntegra y el volumen exacto de los supuestos 1,8 millones de clientes incluidos en el archivo de 74 GB (N09, N10) | Verificar la totalidad del fichero exigiría adquirirlo o descargarlo desde la red oscura, conducta ilícita que financiaría al cibercrimen y violaría la ética profesional |
| L07 | La causa técnica, vulnerabilidad o fallo de configuración exacto que permitió el acceso inicial en los sistemas del proveedor | Reside en registros de actividad (logs) internos, análisis forenses y configuraciones de red privados de la empresa proveedora y de Naturgy, inaccesibles desde fuentes abiertas |
| L08 | La identidad de la persona física detrás del alias «spain» | La atribución individual de ciberdelincuentes compete exclusivamente a las Fuerzas y Cuerpos de Seguridad del Estado mediante investigación judicializada. El perfilado de personas por analistas en fuentes abiertas está prohibido |

## 3. Necesidad de inteligencia

| Pregunta | Laguna de la que procede (2.3) | Quién usaría la respuesta | Para qué decisión o protección |
| --- | --- | --- | --- |
| 1. ¿Existen análisis técnicos públicos o comunicados que comparen los campos y muestras de septiembre con el incidente del proveedor de mayo (N03) o con brechas históricas conocidas? | L01, L04 | Responsables de seguridad defensiva del sector y analistas de ciberinteligencia | Para evaluar si la venta de septiembre es una amenaza activa nueva o un refrito de datos ya conocidos, decidiendo si amerita elevar el nivel de alerta operativo del sector |
| 2. ¿Qué nivel de fiabilidad y reputación atribuyen los informes abiertos de ciberinteligencia al alias «spain» (actor con capacidad técnica real o estafador oportunista)? | L02 | Equipos de respuesta a incidentes (CSIRT/SOC) de entidades financieras y de telecomunicaciones | Para calibrar la verosimilitud de la oferta y decidir si emitir avisos preventivos de fraude ante posibles ataques derivados o tratar el caso como un probable engaño comercial |
| 3. ¿Ha publicado la AEPD resoluciones, directrices o medidas provisionales en relación con la notificación de la brecha de Naturgy de mayo (N05, N12)? | L03 | Delegados de Protección de Datos (DPD), asociaciones de consumidores (OCU) y usuarios | Para conocer el criterio oficial de la autoridad de control sobre las garantías exigibles en la custodia de datos por proveedores y orientar a los afectados sobre sus derechos |
| 4. ¿Qué medidas preventivas específicas han recomendado los organismos públicos (INCIBE-CERT) para clientes ante el riesgo de fraudes derivados de la filtración de datos bancarios (N03, N11)? | L01 | Clientes de Naturgy y ciudadanos en general | Para adoptar pautas rigurosas de autoprotección frente a campañas dirigidas de smishing, phishing bancario y llamadas fraudulentas (vishing) que utilicen datos contractuales legítimos |

### Preguntas que no se intentarán responder

| Pregunta que NO se intentará responder | Por qué |
| --- | --- |
| ¿Cuál es la identidad de la persona física detrás del alias «spain»? | La atribución y persecución penal de personas físicas corresponde con exclusividad a las Fuerzas y Cuerpos de Seguridad del Estado. El Protocolo de Berkeley prohíbe el perfilado individual por analistas no autorizados |
| ¿Qué empresa concreta es el proveedor externo de Naturgy donde ocurrió la brecha de mayo? | Es información confidencial de carácter comercial y contractual. Indagarla supondría una intromisión en el secreto empresarial y el riesgo de dañar la reputación de terceros sin base legítima |
| ¿Contiene el volcado de 74 GB los datos reales de 1,8 millones de clientes de Naturgy? | Para responderla sería obligatorio descargar, comprar o manipular la base de datos robada en mercados clandestinos, lo que constituiría un delito y financiaría actividades ilícitas |
| ¿Qué fallos de seguridad o puertos vulnerables tenían los sistemas del proveedor o de Naturgy? | Probar o rastrear activamente vulnerabilidades en infraestructuras ajenas es ilícito y contrario al principio de observación pasiva de la ciberinteligencia en fuentes abiertas |

## 4. Legitimación y no interferencia

**Quién investiga y desde qué posición**
Investiga el Grupo 2, compuesto por estudiantes universitarios en la asignatura de Ciberinteligencia. Su posición es estrictamente académica, formativa y no operativa. El grupo no actúa como representante de Naturgy ni de su proveedor externo, no forma parte de las Fuerzas y Cuerpos de Seguridad del Estado (FCSE), no ostenta facultades de inspección regulatoria (como la AEPD) ni periciales judiciales, ni ha recibido ningún encargo profesional por parte de las entidades afectadas. Por tanto, el grupo actúa únicamente como un observador externo que analiza información que ya ha sido publicada lícitamente en el dominio público.

**Marco normativo aplicable en esa posición**

- *Reglamento General de Protección de Datos (RGPD, UE 2016/679)* y *Ley Orgánica 3/2018 (LOPDGDD)*: marco regulador de obligado cumplimiento para cualquier tratamiento incidental de información relativa a personas físicas identificadas o identificables.
- *Código Penal español (Ley Orgánica 10/1995)*: en particular los artículos 197 (delitos contra la intimidad, descubrimiento y revelación de secretos e interceptación) y 197 bis (acceso no autorizado a sistemas informáticos y vulneración de medidas de seguridad), que prohíben la adquisición, descarga o retención de volcados de datos ilícitos y el escaneo activo de infraestructuras ajenas.
- *Protocolo de Berkeley sobre investigaciones digitales en fuentes abiertas*: directrices internacionales que imponen los principios de necesidad, proporcionalidad, legalidad, evaluación previa de riesgos (párr. 108) y planificación previa (párr. 115).
- *Normativa de la Universidad y de la asignatura CIBINT*: compromiso explícito de uso responsable, ético y de no ejecución de acciones que comprometan sistemas de terceros.

**Responsable de los datos y base de licitud**

- *Responsable del tratamiento:* Los propios estudiantes miembros del equipo de investigación actúan como responsables del tratamiento respecto de cualquier tratamiento técnico de datos que se produzca durante la actividad.
- *Base de licitud:* El tratamiento se ampara en el **interés legítimo (artículo 6.1.f del RGPD)** para fines formativos y de investigación académica universitaria, superando el triple juicio de ponderación:
  - *Idoneidad:* El análisis de casos reales de filtraciones es un medio adecuado e imprescindible para la capacitación en metodología analítica de ciberinteligencia.
  - *Necesidad:* El análisis se limita estrictamente a la documentación, declaraciones oficiales y análisis periodísticos ya publicados, sin recopilar datos personales directos de clientes.
  - *Proporcionalidad y salvaguardas:* Los derechos de los afectados prevalecen en todo momento mediante la regla de **minimización absoluta (art. 5.1.c RGPD)**: no se busca ningún dato personal; si algún dato identificativo apareciera de forma involuntaria (ej. en capturas censuradas en prensa), será ofuscado de inmediato, no se indexará ni almacenará y será borrado al finalizar la práctica. Queda completamente excluido el tratamiento de datos de categorías especiales (art. 9 RGPD).

**Qué no corresponde al grupo y a quién sí**

- *Auditar la infraestructura técnica de Naturgy o del proveedor y determinar el vector de intrusión:* Corresponde exclusivamente a los equipos de seguridad de Naturgy, del proveedor y al Centro Criptológico Nacional (CCN-CERT / INCIBE-CERT).
- *Investigar, contactar o atribuir la autoría del alias «spain»:* Corresponde con exclusividad a las Fuerzas y Cuerpos de Seguridad del Estado (Brigada Central de Investigación Tecnológica de la Policía Nacional y Grupo de Delitos Telemáticos de la Guardia Civil).
- *Determinar infracciones legales o exigir responsabilidades a Naturgy por la gestión de la brecha:* Corresponde a la Agencia Española de Protección de Datos (AEPD).
- *Adquirir, verificar o custodiar el lote completo de datos de 74 GB:* Corresponde a las unidades policiales especializadas bajo autorización judicial. Adquirirlo o descargarlo por parte de estudiantes constituiría un delito de descubrimiento y revelación de secretos (art. 197.2 CP).

**Otras investigaciones y deber de no interferencia**

- *Investigaciones existentes o previsibles:*
  - Investigación técnica y auditoría forense interna de Naturgy y sus proveedores de seguridad (N06).
  - Procedimiento de investigación y supervisión de la AEPD a raíz de la notificación formal de la brecha (N05, N12).
  - Diligencias de investigación tecnológica de la Policía Nacional o Guardia Civil tras la puesta en conocimiento del incidente (N05).
- *Cómo se evita entorpecerlas (Principio de No Interferencia y Observación Pasiva):*
  - **No interacción con el adversario:** El grupo no establecerá ningún tipo de comunicación con el alias «spain» ni con terceros en foros clandestinos (no solicitar muestras, no pedir pruebas de vida de los datos, no regatear precios).
  - **No entrada a foros clandestinos:** No registrar cuentas ni acceder a la plataforma de la dark web donde se publicó la oferta, evitando alertar al actor, alterar registros forenses o promover artificialmente la cotización de los datos.
  - **Inexistencia de sondeos técnicos:** No realizar escaneos de puertos, peticiones automatizadas ni pruebas de estrés contra infraestructuras de Naturgy ni de su proveedor.
  - **No contacto con las víctimas:** No contactar de forma directa con presuntos clientes afectados para verificar la validez de los datos, evitando generar alarma social o interferir con los canales de atención al cliente oficiales de Naturgy.

## 5. Plan de obtención

### 5.1 Fuentes y técnicas previstas

| ID | Fuente o técnica | Pregunta a la que responde (3) | Por qué es lícita | Por qué es la menos intrusiva disponible | Qué expondría y a quién |
| --- | --- | --- | --- | --- | --- |
| OB1 | Lectura y análisis crítico del material de partida facilitado (N01–N12, F01–F06) | 1, 2, 3 y 4 | Es el repositorio documental cerrado proporcionado para la actividad académica | No genera tráfico de red ni interacción con sistemas externos; es puramente local | Nada a nadie; trabajo en entorno local cerrado |
| OB2 | Consulta pasiva de los comunicados y publicaciones oficiales de Naturgy en su web corporativa y canal oficial de X, sin inicio de sesión | 1 | Son declaraciones públicas corporativas emitidas en abierto para la ciudadanía | Es la vía directa para conocer la postura de la entidad afectada sin intermediarios y sin superar controles de acceso | Una visita ordinaria (dirección IP) en los servidores web de Naturgy o de X. Si se consulta X, las respuestas públicas de terceros podrían mostrar comentarios o datos personales de clientes |
| OB3 | Consulta de notas públicas, resoluciones sancionadoras o avisos en la sede electrónica de la AEPD y portales oficiales de INCIBE-CERT | 3 y 4 | Son registros y boletines oficiales accesibles en cumplimiento del principio de transparencia y publicidad de las Administraciones Públicas | Es la vía legal ordinaria para conocer la postura de los reguladores sin acceder a expedientes reservados en instrucción | Una solicitud HTTP ordinaria en los servidores del organismo público |
| OB4 | Búsqueda limitada en motores de búsqueda web generales (Google/DuckDuckGo) con términos contextuales del incidente, acotando a medios de comunicación, blogs de ciberseguridad y firmas de análisis, sin abrir foros ni descargas | 1, 2 y 4 (en parte) | Acceso a contenidos públicos indexados en la web abierta (surface web) sin eludir controles de acceso ni descargar datos robados | Permite recopilar el análisis de expertos sin interactuar con el actor ni acceder a la dark web ni descargar volcados ilícitos | Las cadenas de búsqueda quedan registradas en el buscador vinculadas a la IP. Los resultados podrían devolver enlaces a foros o capturas con datos personales que deben descartarse |
| OB5 | Consulta en repositorios abiertos de ciberinteligencia y alertas de Threat Intelligence público sobre menciones al alias «spain» en relación con incidentes de 2026 | 2 | Consulta de metadatos e investigaciones abiertas ya publicadas por la comunidad de seguridad | Permite conocer antecedentes agregados sin seguir ni rastrear al actor directamente en mercados clandestinos | Deja constancia de consulta en las plataformas de ciberinteligencia consultadas |

*Alcance parcial de las preguntas:*

- *Pregunta 2:* OB5 y OB4 solo recogen menciones públicas de firmas de seguridad sobre la trayectoria del alias «spain». No se prevé ninguna técnica para averiguar la identidad real de la persona física tras el alias, pues el perfilado de personas está expresamente descartado (Tema 2) y compete a las FCSE.
- *Pregunta 4 (en parte):* OB1 y OB4 analizan descripciones y capturas publicadas en prensa técnica; no se prevé ninguna técnica para verificar el archivo de 74 GB ni para buscar fallos en la infraestructura del proveedor, por ser ilícito o desproporcionado.

### 5.2 Evaluaciones de licitud

Se elige **OB4** porque es la técnica que plantea un mayor riesgo de exposición accidental a datos personales de clientes (capturas no censuradas, datos de contratos) o de redirección involuntaria hacia repositorios ilícitos. Se elige **OB2** porque plantea riesgos operativos en redes sociales: X puede exigir inicio de sesión (lo que expondría cuentas personales) y las respuestas a publicaciones de Naturgy suelen incluir quejas de clientes reales con información personal expuesta.

| Campo de la plantilla | OB4 · búsqueda limitada en buscadores web | OB2 · consulta de canales oficiales y X |
| --- | --- | --- |
| Pregunta (3) | 1, 2 y 4 (en parte) | 1 |
| Quién investiga y fecha | El Grupo 2, en la práctica académica de CIBINT (18/10/2026) | El Grupo 2, en la práctica académica de CIBINT (18/10/2026) |
| Datos de personas identificables | No se buscan; podrían aparecer incidentalmente nombres o correos en capturas reproducidas por medios | No se buscan; podrían aparecer cuentas de usuarios, nombres o quejas de clientes en respuestas públicas en X |
| Categorías especiales o datos penales (art. 9 y 10 RGPD) | No. Si se detectasen, se detendría la consulta inmediatamente y se descartaría el enlace | No. Si aparecieran en comentarios, no se registran ni se almacenan |
| Base de licitud | Interés legítimo académico (art. 6.1.f RGPD, apartado 4) | Interés legítimo académico (art. 6.1.f RGPD, apartado 4) |
| Por qué es necesario | Es el único medio para conocer análisis técnicos de fuentes secundarias sin entrar a la dark web | Es la vía directa para conocer los comunicados y la postura oficial de la organización afectada |
| Qué se descarta | Resultados que enlacen a foros clandestinos, pastes, canales de mensajería o descargas directas de datos | Respuestas de usuarios, comentarios con datos de facturas y solicitudes de inicio de sesión que exijan cuenta |
| Informar a los afectados | No: no se tratan ni almacenan sus datos personales | No: no se tratan ni almacenan sus datos personales |
| Conservación | Hasta la revisión final de la evaluación académica de la práctica | Hasta la revisión final de la evaluación académica de la práctica |
| Supera medidas de seguridad | No; se descartan inmediatamente resultados que requieran registro, autenticación o pago | No; si la plataforma exige inicio de sesión o salta un muro de autenticación, se interrumpe la consulta |
| Credenciales, contacto o suplantación | No | No; no se interactúa, no se responde ni se envía mensaje a Naturgy ni a usuarios |
| Investigar a una persona por encargo | No: los términos son exclusivamente técnicos y contextuales del incidente | No: se consulta la cuenta institucional de la empresa |
| Condiciones de uso | Uso estándar y lícito del motor de búsqueda conforme a sus términos | Visualización web en abierto conforme a los términos de la plataforma, sin evadir restricciones |
| Forma menos intrusiva | OB1, que se analiza en primer lugar; OB4 solo complementa con medios fiables | OB1, complementada con la consulta directa de las notas de prensa institucionales |
| Quién podría resultar perjudicado | Clientes de Naturgy, si se expusieran datos inadvertidamente | Clientes que hayan publicado quejas con datos en comentarios |
| Explicable a un tercero imparcial | Sí, porque está rigurosamente acotada a prensa especializada y firmas de seguridad | Sí, porque se limita a consultar declaraciones públicas oficiales de la propia compañía |
| Rastro en sistemas del objetivo | No en sistemas de Naturgy ni del actor; solo en los registros de consulta del buscador | No en el adversario; solo en los logs de acceso de Naturgy o de los servidores de X |
| Medios de trabajo y envío a terceros | Navegador actualizado en entorno aislado; no se envían datos a terceros | Navegador actualizado en entorno aislado; no se envían datos a terceros |
| Quién conoce el resultado | El equipo de trabajo y el docente de la asignatura | El equipo de trabajo y el docente de la asignatura |
| Decisión | Adecuada con condiciones | Adecuada con condiciones |
| Condiciones | Consulta estricta de medios y blogs de seguridad reconocidos; no abrir enlaces a foros, pastes ni descargas; ofuscar inmediatamente cualquier dato personal incidental | Consulta estrictamente pasiva sin sesión iniciada; no interactuar; no leer comentarios de usuarios; si X bloquea la vista pública, recurrir exclusivamente a la web corporativa |
| Consultas | Al docente de la asignatura por el canal privado establecido | Al docente de la asignatura por el canal privado establecido |
| Validación | Cumple los principios de legalidad, proporcionalidad y no intrusión | Cumple los principios de legalidad, proporcionalidad y no intrusión |

## 6. Reglas de actuación

### 6.1 Lo que se haría solo con condiciones

| Actuación | Condición que debería cumplirse | Quién comprobaría que se cumple |
| --- | --- | --- |
| Búsqueda y lectura de noticias o reportes (OSINT) que incluyan capturas de pantalla de la filtración | Que los datos personales presentes en las imágenes (si existen) estén completamente ofuscados o censurados por el medio de comunicación; en caso contrario, se descartan | El analista que realiza la búsqueda y el portavoz del equipo |
| Consulta pasiva de las redes sociales para analizar menciones al actor «spain» | Que se realice estrictamente sin cuenta personal iniciada (modo visitante) y absteniéndose de interactuar con publicaciones, usuarios o comentarios | El responsable del equipo y el docente (mediante revisión) |

### 6.2 Lo que no se haría

| Exclusión propia de este caso | Por qué |
| --- | -- |
| Registrarse y acceder al foro de la Dark Web donde se oferta el volcado de datos | Supone un riesgo de seguridad informático, es contrario al principio de recolección pasiva en fuentes abiertas y nos expone legal y moralmente ante los actores cibercriminales. |
| Descargar, comprar o solicitar pruebas de vida de los 74 GB de datos robados | Implica participar activamente en la cadena delictiva, financiar actividades ilícitas y cometer presuntos delitos tipificados en el Código Penal (art. 197). |
| Realizar escaneos de red, de vulnerabilidades o tests de estrés a los sistemas de Naturgy o su proveedor | Es un delito de acceso ilícito a infraestructuras IT (art. 197 bis CP) al carecer de autorización explícita o acuerdo comercial como auditores. |

### 6.3 Condiciones de parada

| Si ocurriera… | El equipo… | Y consultaría a… |
| --- | --- | --- |
| El acceso accidental a un repositorio tipo Pastebin que contenga en texto claro la base de datos robada de los clientes | Cerraría la ventana del navegador inmediatamente de forma segura sin copiar, guardar o indexar ningún dato personal | El docente de la asignatura para informar del suceso |
| El descubrimiento de que algún miembro del equipo, o un familiar directo, forma parte de los clientes filtrados | Apartaría temporalmente a esa persona de la búsqueda de exposición, previniendo posibles conflictos de interés o daños psicológicos | El docente de la asignatura |

## 7. Tratamiento de datos personales

| Datos que podrían aparecer aunque no se buscasen | De quién | Cómo se minimizarían | Dónde se guardarían y quién accedería | Cuándo y cómo se borrarían |
| --- | --- | --- | --- | --- |
| Correos electrónicos, NIF, nombres completos, teléfonos o IBAN, al revisar recortes de prensa tecnológica o capturas en foros | Clientes de Naturgy en España (y víctimas del incidente) | Aplicando censura visual automática (barras negras o desenfoque) en la captura, sin transcribirlos nunca a texto | En almacenamiento local cifrado de cada estudiante. Acceso limitado únicamente a los miembros del grupo | Mediante borrado lógico seguro, justo después de completada y evaluada la práctica por el docente |

## 8. Seguridad de la operación

### 8.1 OPSEC de la investigación

| Paso | En este caso |
| --- | --- |
| Información crítica | Identidad real de los investigadores universitarios, IP de la conexión personal, intereses específicos de búsqueda y los resultados extraídos. |
| Amenazas | Perfilado, huella digital o rastreo por rastreadores web (trackers) de foros tecnológicos. Posible exposición accidental a URLs infectadas o phishing al buscar información sobre el cibercrimen. |
| Vulnerabilidades | Navegar usando conexiones residenciales comunes sin ofuscar, uso de navegadores que mantienen sesiones iniciadas (Google/X) o con historial cruzado. |
| Riesgo | Bajo, dado que el cerco del análisis está establecido únicamente en la Surface Web institucional y periodística. |
| Contramedidas | Utilización de navegador dedicado (aislado y configurado en modo incógnito severo sin extensiones que filtren datos), purga de caché recurrente, enrutamiento a través de un servicio VPN o proxy y cierre de cualquier sesión personal. |

### 8.2 Identidad de investigación

Se empleará una **identidad pasiva, no atribuible y no autenticada**. Esto significa que las búsquedas se realizarán como un visitante genérico y anónimo de internet, sin crear perfiles falsos ("sock puppets") ni iniciar sesión en cuentas. Esta metodología es la adecuada porque nuestra obtención de datos se ciñe a medios de comunicación, foros públicos en abierto y sedes electrónicas públicas (AEPD, INCIBE), los cuales no exigen acreditación. Se descartan identidades encubiertas (infiltración) porque exceden el objetivo académico de la práctica, contravienen el Protocolo de Berkeley y generarían riesgos operativos graves si llegaran a interactuar con el actor "spain".

### 8.3 Riesgos para las personas y conflictos de intereses

- **Para las víctimas (clientes de Naturgy):** Riesgo de fraude o estafa secundaria si sus datos fuesen mal manipulados. Para mitigarlo, la investigación blinda el acceso directo a los datos, evitando recabarlos o contactar con los usuarios bajo cualquier concepto.
- **Para el equipo de investigadores (psicológicos y jurídicos):** Riesgo de estrés al lidiar con material procedente de crímenes (hacking). Se aborda evitando la Dark Web y el contacto con los delincuentes, eliminando el riesgo jurídico (art. 197 CP).
- **Conflictos de interés:** Dado que la filtración afectaría presuntamente al 3% de los clientes en España, es altamente probable que algún miembro del equipo de investigación o sus familiares sean clientes de Naturgy. Para prevenir sesgos u obrar en beneficio personal, el grupo asume que, en caso de hallarse información sobre este familiar, dicho investigador detendría el proceso de extracción para ese dato y se lo comunicaría al responsable.

## 9. Trazabilidad y custodia

Para asegurar la veracidad de los hechos y garantizar que no se ha modificado la información recopilada:
- **Qué se registraría y cuándo:** Un registro manual (diario de inteligencia) documentando fecha, hora (timestamp) y la URL exacta visitada, de forma simultánea a la consulta.
- **Cómo se conservarían las evidencias:** Se obtendrán capturas de pantalla de página completa o exportaciones en PDF (sin interactuar o modificar elementos HTML).
- **Demostración de integridad:** Se acompañará cada documento PDF de su código hash criptográfico (algoritmo SHA-256) generado en el momento de la captura, descartando cualquier posible alteración futura.
- **Quién las custodiaría:** El portavoz del equipo (Sergio Rodríguez), encargado de mantenerlas en un directorio cifrado durante toda la extensión de la práctica formativa.

## 10. Manejo y difusión

| Producto | Destinatario | Canal | Etiqueta TLP | ¿Podría publicarse en este repositorio? ¿Por qué? |
| --- | --- | --- | --- | --- |
| Documento del Plan de Investigación y Evidencias OSINT asociadas | Docente evaluador de la asignatura de Ciberinteligencia | Repositorio GitHub de la asignatura o Campus Virtual cerrado | TLP:CLEAR | Sí. El documento se nutre de información 100 % recabada en fuentes abiertas al público, no detalla vulnerabilidades, ni difunde los datos personales expuestos por el delincuente. |

No procedería compartir este informe con organismos gubernamentales (como AEPD, INCIBE-CERT o Fuerzas de Seguridad) debido a que Naturgy ya comunicó públicamente la brecha oficializando las diligencias e investigaciones previas (afirmaciones N05, N12). El equipo académico interviene meses después (octubre) a nivel formativo pasivo sin aportar una visibilidad inicial (zero-day) del incidente.

## 11. Alcance de la investigación

| Campo | Definición |
| --- | --- |
| Objetivo | Aclarar las discrepancias formales sobre el alcance del ataque notificado y establecer una valoración de los riesgos para los ciudadanos. |
| Finalidad | Exclusivamente formativa y académica, ejercitando competencias de analítica OSINT, de modo observacional. |
| Fuentes permitidas | Medios de comunicación de la Surface Web, sedes electrónicas públicas (AEPD, INCIBE), comunicados de Naturgy. |
| Técnicas permitidas | Dorking (búsqueda avanzada en motores indexados), análisis documental periodístico, lecturas de avisos públicos en redes sociales (sin autenticación). |
| Exclusiones específicas | Navegación por la Deep / Dark Web, adquisición o decarga de volcados de datos filtrados, técnicas de pentesting, comunicación con el adversario. |
| Canal de entrega del resultado | Repositorio / Plataforma oficial de la asignatura. |
| Vigencia | Única y exclusivamente durante el periodo lectivo estipulado de la asignatura. |

---

## Fuentes

| ID | Organización | Título | Fecha de consulta |
| --- | --- | --- | --- |
| F01 | Euronews | Naturgy sufre una filtración de datos en España, incluidos posibles datos bancarios de clientes | 2026-10-18 |
| F02 | Infobae | Naturgy comunica una filtración de datos que afecta a un 3% de sus clientes en España | 2026-10-18 |
| F03 | Escudo Digital | Naturgy reconoce una brecha de datos que afecta a 200.000 de sus clientes en España | 2026-10-18 |
| F04 | Ciberseguridad Creando Patria | Naturgy confirma brecha de datos en proveedor externo: datos personales y bancarios de 200.000 clientes expuestos | 2026-10-18 |
| F05 | ADSLZone | Un grupo de hackers afirma tener los datos personales y bancarios de los clientes de Naturgy, y acaba de ponerlos en venta | 2026-10-18 |
| F06 | El Grupo Informático | Ponen a la venta una base de datos con 74 GB que expondría a más de 1,8 millones de clientes de Naturgy | 2026-10-18 |

## Equipo

### Organización del trabajo

El equipo ha dividido las matrices del documento para asegurar una doble revisión de calidad. Un subgrupo se enfocó en el análisis de las lagunas, hipótesis y el marco regulatorio, mientras que el otro delineó los escenarios de riesgo de OPSEC, contramedidas y los estándares de preservación de evidencias según la normativa de la asignatura y del Protocolo de Berkeley.

### Aportación individual

**José Luis de la Asunción**
Me encargué del análisis inicial de la licitud y los apartados de reglas de actuación y OPSEC (Apartados 4, 6, 7 y 8). Defendí ante el grupo la prohibición estricta de iniciar sesión en X, ya que rompía con nuestra regla de pasividad total, y elaboré los filtros de descarte. Lo que me resultó más complejo fue ajustar la exclusión del riesgo psicológico en un entorno formativo manteniendo la perspectiva real del analista.

**Sergio Rodríguez**
Asumí el rol de portavoz y elaboré las matrices correspondientes a la trazabilidad, difusión, alcance y necesidades de inteligencia (Apartados 3, 9, 10 y 11). Discutí la inclusión de firmas criptográficas (hashes) para los recortes periodísticos frente al almacenamiento común, optando por lo primero para mantener la integridad de la prueba en OSINT. La mayor dificultad fue lograr el equilibrio para redactar necesidades operativas sin violar la no injerencia.

**Alejandro Ateca**
Me enfoqué en la fase inicial recabando la situación del problema, analizando los hechos consolidados del CSV aportado, las lagunas del conocimiento y redacté el resumen del plan (Apartados 1 y 2). Apoyé activamente evitar a toda costa la deep web. Lo más difícil fue sintetizar la discrepancia entre las afirmaciones de Naturgy (3%) y las que aseguraban 1,8 millones de cuentas, tratándolas sin sesgos como valoraciones y sin darlas por ciertas.

## Uso de inteligencia artificial

La declaración está en [registro-ia.md](registro-ia.md). Se ha empleado IA generativa bajo modalidad consultiva de formato y corrección ortotipográfica para unificar la coherencia del documento y garantizar el rigor académico del texto, sin delegar las evaluaciones de licitud, toma de decisiones ni el cruce de evidencias.

## Comprobación antes de entregar

- [x] Todos los bloques «Qué debe contener» están sustituidos.
- [x] Ninguna afirmación no confirmada se presenta como establecida.
- [x] No se ha realizado ninguna búsqueda ni obtención de información fuera del material de partida.
- [x] El repositorio no recibe archivos de noticias, capturas con datos personales ni material no publicable.
- [x] `registro-ia.md` está completo, con los prompts, o declara que no se ha usado IA.
- [x] El *pull request* solo modifica archivos de la carpeta del grupo.
