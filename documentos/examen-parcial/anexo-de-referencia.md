# Anexo de referencia

*Examen parcial de CIBINT · común a todos los modelos*

Este anexo resume las normas, los criterios de la asignatura y la sintaxis de las herramientas que pueden aparecer en el examen. No se evalúa que recuerdes los artículos, sino que los apliques al caso. Cuando justifiques una decisión, cita la referencia del anexo (por ejemplo, N-03).

## A. Protección de datos

| Ref. | Norma | Contenido en síntesis |
|---|---|---|
| N-01 | RGPD, art. 4.1 | Dato personal es toda información sobre una persona física identificada o identificable, sea pública o privada. |
| N-02 | RGPD, art. 5.1 | Principios: licitud, lealtad y transparencia; limitación de la finalidad; minimización; exactitud; limitación del plazo de conservación; integridad y confidencialidad. |
| N-03 | RGPD, art. 5.2 | Responsabilidad proactiva: cumplir los principios y poder demostrarlo. |
| N-04 | RGPD, art. 6.1.f | Interés legítimo: el tratamiento debe ser necesario y no deben prevalecer los derechos del interesado. |
| N-05 | RGPD, considerando 49 | La seguridad de la red y de la información es un interés legítimo «en la medida estrictamente necesaria y proporcionada». |
| N-06 | RGPD, art. 9 | Prohibición de tratar categorías especiales (salud, ideología, origen étnico, datos biométricos, etc.), salvo excepciones tasadas. |
| N-07 | RGPD, art. 14 | Si los datos no se obtienen del interesado, hay que informarle, salvo excepciones justificadas (por ejemplo, que frustre la finalidad). |
| N-08 | RGPD, art. 33 | Violación de seguridad de datos personales: notificación a la autoridad de control sin dilación y, si es posible, en 72 horas desde que se tiene constancia. Puede notificarse por fases. |
| N-09 | RGPD, art. 34 | Si la violación supone alto riesgo, se comunica también a los afectados. |
| N-10 | LOPDGDD, art. 87 | El acceso del empleador a los dispositivos digitales de la plantilla exige criterios de uso fijados previamente e informados. |

## B. Código Penal

| Ref. | Artículo | Conducta castigada, en síntesis |
|---|---|---|
| N-11 | 197.1 | Apoderarse de mensajes o documentos de otro para descubrir sus secretos. |
| N-12 | 197.2 | Apoderarse, utilizar o modificar sin autorización datos reservados registrados en ficheros. |
| N-13 | 197 bis.1 | Acceder a un sistema de información vulnerando sus medidas de seguridad y sin autorización. |
| N-14 | 197 ter | Producir, adquirir o facilitar programas o contraseñas para cometer los delitos anteriores. |
| N-15 | 172 ter | Acoso reiterado: vigilar, perseguir o contactar con una persona alterando su vida cotidiana; usar su imagen para crear perfiles falsos. |
| N-16 | 401 | Usurpar el estado civil de otro (hacerse pasar por una persona real concreta). |

## C. Investigación por encargo y referencias profesionales

| Ref. | Norma o referencia | Contenido en síntesis |
|---|---|---|
| N-17 | Ley 5/2014, art. 48 | Las averiguaciones por cuenta de terceros sobre conductas o hechos privados están reservadas a detectives privados, con interés legítimo acreditado y proporcionalidad. |
| N-18 | Protocolo de Berkeley, párr. 63 | Usar una contraseña filtrada para acceder a material restringido es acceso no autorizado. |
| N-19 | Protocolo de Berkeley, párr. 65 | Una identidad virtual puede servir para observar, no para obtener información de una persona mediante engaño (unirse a grupos cerrados, contactar con pretextos). |
| N-20 | Protocolo de Berkeley, párr. 35 | Humildad: reconocer lo que no se sabe y corregir los errores. |
| N-21 | Informe Menlo | Respeto por las personas, beneficencia, justicia y respeto por la ley y el interés público. |
| N-22 | TLP 2.0 (FIRST) | TLP:RED: solo destinatarios concretos. TLP:AMBER+STRICT: solo su organización. TLP:AMBER: su organización y clientes que lo necesiten. TLP:GREEN: su comunidad, sin canales públicos. TLP:CLEAR: sin restricción. |
| N-23 | RD-ley 12/2018, art. 11 | INCIBE-CERT es el equipo de respuesta de referencia para el sector privado. |

## D. Criterios de la asignatura antes de cada obtención

1. ¿Responde a una pregunta del requerimiento?
2. Si implica datos personales, ¿hay base legal y se limita a lo necesario?
3. ¿Evita acceder a sistemas o contenidos protegidos?
4. ¿Es la forma menos intrusiva?
5. ¿Se realiza sin exponer la investigación, al analista ni a terceros?
6. ¿Queda registrada en la bitácora?

## E. Referencia de operadores y sintaxis de búsqueda

**Google (buscador web)**

| Operador | Uso | Ejemplo |
|---|---|---|
| "frase" | Frase exacta | "Empresa Ejemplo" |
| site: | Limitar a un dominio | site:ejemplo.example "aviso" |
| -término | Excluir un término | "Nombre Apellido" -homónimo |
| OR | Alternativas (en mayúsculas) | "aviso" OR "comunicado" |
| filetype: | Tipo de documento | site:ejemplo.example filetype:pdf |
| intitle: / inurl: | Término en el título o en la URL | intitle:"aviso" |
| after: / before: | Fecha que el buscador atribuye | "Empresa Ejemplo" after:2026-01-01 |

**Otras fuentes y herramientas**

| Herramienta | Qué consulta | Forma de búsqueda |
|---|---|---|
| Wayback Machine | Capturas históricas de páginas web | web.archive.org/web/*/dominio.example/ruta |
| Google Lens, TinEye | Búsqueda inversa de imágenes | Subir la imagen o un fotograma, o indicar su URL |
| BORME | Actos inscritos de sociedades españolas | Búsqueda por denominación social |
| OpenCorporates | Registros mercantiles de varios países | Búsqueda por nombre y jurisdicción |
| ICANN Lookup (RDAP) | Datos de registro de dominios e IP | Nombre de dominio o dirección IP |
| crt.sh | Registros de transparencia de certificados (CT) | %.dominio.example (todos los nombres bajo el dominio) |
| Shodan | Índice de servicios expuestos | hostname:dominio.example · ip:192.0.2.1 · net:192.0.2.0/24 · port:443 · org:"Nombre" · ssl.cert.subject.cn:dominio.example |
| Censys (CenQL) | Índice de servicios expuestos | host.ip: "192.0.2.1" · host.services.port=443 · host.services: (port=443 and protocol=HTTP), que exige que ambas condiciones se cumplan en el mismo servicio |
| urlscan.io | Análisis ya realizados de páginas web | domain:dominio.example · page.domain:dominio.example |
