# Soluciones · Modelo E3 · Bodegas Cierzo

*Soluciones orientativas con la puntuación de cada apartado*

## Trampas del modelo

- CAT-P01 no tiene coincidencias en la búsqueda inversa: eso es una limitación, no una prueba de autenticidad.
- El «Me gusta» de un comercial no supone que la bodega respalde la publicación.
- La primera captura de la Wayback Machine no es la fecha de creación de la web.
- Figurar como expositor en una feria no equivale a estar autorizado como distribuidor.
- En los metadatos, el productor del PDF es el conversor, y el autor puede proceder de la plantilla.
- La extensión de detección infiere con confianza baja; hay tres señales independientes de WooCommerce.
- El PTR de 192.0.2.78 es una pista sobre una IP distinta de la del ERP (192.0.2.80).

## Bloque 1 · Tema 4 (2,5)

**1.1 (0,8).**

a) Qué revelan los metadatos:

- el formato de usuario nombre.apellido, útil para preparar correos dirigidos;
- una ruta local y el servidor interno SRV-ARCHIVO01;
- la versión del software;
- en DOC-3, un comentario comercial sensible.

b) Lecturas incorrectas:

- dar por hecho que el autor redactó cada documento, cuando puede ser el de la plantilla;
- tratar al productor del PDF como si fuera el equipo de origen, cuando es el conversor;
- deducir el software que se usa hoy a partir de fechas antiguas.

c) Presentación: agregar los datos y seudonimizarlos, describir el patrón y no investigar a las personas. Medidas: limpiar los metadatos antes de publicar y retirar DOC-3.

**1.2 (0,6).**

a) Servicios revelados: correo en la nube, la plataforma de la tienda, un servicio de ofimática en la nube y un servicio de firma electrónica.

b) Uso por un atacante: pretextos como «documento pendiente de firma». Medida: formación específica y filtros de correo.

c) Los registros TXT no demuestran el uso actual de esos servicios ni qué datos contienen.

**1.3 (0,4).**

a) WooCommerce sobre WordPress, apoyado en la cookie, la cabecera Link y las rutas de recursos.

b) La extensión infiere con confianza baja. La cabecera Server: cloudflare indica que hay una CDN que oculta el servidor de origen.

**1.4 (0,7).**

| Hallazgo | Prioridad |
|---|---|
| H1 | Alta para validación: el ERP es accesible pese a que el inventario dice «solo por VPN» |
| H2 | Alta: el dominio expira en tres semanas; hay que comprobar la renovación |
| H3 | Alta o media: retirar el documento |
| H4 | Baja: es una pista sobre otra IP |

Los dos primeros son H1 y H2, o H1 y H3.

## Bloque 2 · Tema 3 (3,5)

**2.1 (0,5).**

| Elemento | Tipo de huella |
|---|---|
| CAT-W01 | De canales o corporativa |
| CAT-R01 | Corporativa |
| CAT-D02 | Documental |
| CAT-P01 | Profesional |
| CAT-B01 | Documental |

**2.2 (0,8).**

a) La foto de CAT-P02 procede de un banco de imágenes, así que no representa al titular. La ausencia de coincidencias en CAT-P01 es una limitación y no prueba nada.

b) CAT-P03 reutiliza la fotografía de una persona real (CAT-P04 y CAT-D01), lo que apunta a una probable suplantación. Lo proporcionado es avisarle por un canal profesional y denunciar el perfil, sin investigarle (N-02, N-21).

c) Solo que esa cuenta interactuó con la publicación.

**2.3 (1,0).**

a) Contradicciones (basta con tres):

- «1998» frente a la constitución el 14/07/2026;
- el texto está copiado de una web de 2017;
- dice ser exclusivo, pero el contrato con Lion Gate está vigente hasta 2029;
- la marca pertenece a Bodegas Cierzo.

b) Indica cuándo se archivó la web, no cuándo se creó.

c) La fiabilidad de la fuente es baja: es interesada y presenta contradicciones. La credibilidad de la afirmación también es baja frente a CAT-R02 y CAT-R03.

d) Demuestra que la empresa está inscrita como expositora. No demuestra que esté autorizada como distribuidor.

**2.4 (1,2).**

a) `"Fundada en 1998, somos líderes en importación de vinos europeos"`: la frase exacta entre comillas localiza las copias literales.

b) Ejemplo: `"Cierzo Asia Trading" after:2026-07-01`.

c) Se recomiendan O1, O2, O3 y O5. No se recomienda O4, porque es un engaño (N-19) y alerta al objetivo.

d) Información aprovechada: el nombre y la foto del director de exportación, la marca y la presencia en ferias. Medida: publicar la lista de distribuidores autorizados.

## Bloque 3 · Tema 2 (1,5)

**3.1 (1,0).**

| Acción | Amenaza o vulnerabilidad | Contramedida |
|---|---|---|
| 1 | El objetivo ve visitas desde la red corporativa | Usar fuentes pasivas o el entorno de investigación previsto |
| 2 | La plataforma informa de quién visita los perfiles | No usar cuentas personales |
| 3 | Se entrega material del caso a un tercero | No subirlo; consultar por huella o recurrir al equipo autorizado |
| 4 | Filtración por romper la necesidad de conocer | Usar canales oficiales |
| 5 | Ingeniería social dirigida al analista | Responder por el canal oficial y verificar la identidad del interlocutor |

**3.2 (0,5).**

a) Riesgo de exposición del analista, facilitado por las acciones 2, 4 y 5.

b) Medidas: apoyo institucional al analista, conservación de evidencias, denuncia ante la plataforma y vía legal (N-15).

c) Responder confirmaría la investigación, podría escalar el conflicto y expondría más datos personales.

## Bloque 4 · Tema 1 (1,0)

**4.1 (1,0).**

| Acción | a | b | c | d | e | f | g | h | i | j |
|---|---|---|---|---|---|---|---|---|---|---|
| Fase | PR | DP | OB | AP | DI | RE | OB | OB | AP | DP |
