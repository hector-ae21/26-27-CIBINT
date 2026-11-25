# Soluciones orientativas · Ejemplo R4 · Cerámicas Alba

*Resuelve el examen antes de consultarlas.*

# Parte individual

## Trampas del ejemplo

- La empresa del registro británico se llama igual, pero vende pescado, tiene otra web y otros directivos: es otra empresa.
- El FTP figura como apagado en el inventario, pero sigue visible: el inventario no está al día.
- vpn.ceramicasalba.example aparece en CT, pero no responde: un certificado antiguo no prueba que el servicio exista hoy.
- Los metadatos «Usuario» y un programa gratuito no prueban un fraude: muchas empresas reales los tienen.
- A3 parece análisis, pero traducir y ordenar es procesamiento.

## Bloque 1 · Tema 4

**1.1**

| Ficha | ¿De quién? | Justificación |
|---|---|---|
| SH-1 | Empresa | 192.0.2.80 es una IP contratada |
| SH-2 | Proveedor | Plataforma compartida con 12.000 tiendas |
| SH-3 | Empresa | 192.0.2.81 es una IP contratada |

**1.2**

a) Ejemplo: «Shodan observó el 04/11/2026 un servidor FTP con acceso anónimo en 192.0.2.80».

b) Cualquiera podría descargar ficheros de la empresa sin contraseña, y el inventario lo da por apagado.

c) Sistemas comprueba si sigue activo y lo apaga o lo protege. No se entra a mirar los ficheros.

**1.3**

a) Alguien registró la víspera dominios parecidos al de la empresa y los controla a la vez: probablemente para engañar a clientes con facturas o cambios de cuenta.

b) Quién está detrás.

c) Avisar a los clientes de que la empresa solo usa ceramicasalba.example y de que confirmará por teléfono cualquier cambio de cuenta.

**1.4**

a) Ejemplos: `net:192.0.2.80/31` · `hostname:ceramicasalba.example`

b) `%.ceramicasalba.example`

c) El nombre existió en 2022, pero hoy no está en uso. Se pregunta a sistemas si se retiró y se quita del inventario.

**1.5** a) Dentro. b) Fuera: es conectarse a un equipo, no obtención pasiva. c) Dentro. d) Dentro. e) Fuera: interactúa con el adversario.

## Bloque 2 · Tema 3

**2.1**

| Elemento | Relación | Evidencia |
|---|---|---|
| NOR-P01 | No confirmada | Creada en 09/2026 y enlaza a la web del pedido |
| NOR-P02 | Identidad probablemente falsa | Foto de banco de imágenes (NOR-I01) |
| NOR-P03 | Otra empresa con el mismo nombre | Otra actividad, otra web y otros directivos |
| NOR-P04 | No confirmada | Solo dos publicaciones recientes |

**2.2**

a) La web se capturó por primera vez el 20/10/2026 (NOR-D02), la página de LinkedIn es de 09/2026 y la única empresa registrada con ese nombre es otra.

b) Que la web existía al menos desde el 20/10/2026. No demuestra que antes no existiera, porque la Wayback Machine no lo guarda todo.

c) Solo que el pedido se escribió el mismo día con un programa gratuito. No bastan: muchas empresas reales generan documentos así.

**2.3**

| Fuente | Fiabilidad | Credibilidad |
|---|---|---|
| NOR-D04 | Baja (la propia empresa, sin verificar) | Baja |
| NOR-P03 | Alta (registro oficial) | No sirve: habla de otra empresa |
| NOR-D02 | Alta sobre la fecha de captura | La contradice |

**2.4**

a) Ejemplos:

- `"Northbay Trading" -fish`: otras menciones de la empresa que excluyan a la de pescado.
- `"northbay-trading.example"`: quién más enlaza o menciona la web.

b) Elementos de la nota:

- **Valoración:** muy probablemente no es una empresa establecida.
- **Confianza:** media o alta.
- **Evidencias:** NOR-D02 (web de octubre de 2026) y NOR-I01 (foto de banco de imágenes).
- **Limitación:** no se ha confirmado quién está detrás ni si es un fraude.
- **Recomendación:** no servir el pedido a crédito; pedir pago por adelantado y referencias.

## Bloque 3 · Tema 2

**3.1**

| Propuesta | Decisión | Motivo |
|---|---|---|
| P1 | No | Pretexto engañoso (N-19) |
| P2 | Sí | Fuente pública y mínima (N-02) |
| P3 | No | Interactúa con el adversario y expone la investigación (criterios D.4 y D.5) |
| P4 | No | Faltan normas de uso informadas (N-10) |
| P5 | Sí | Medida comercial proporcionada |

**3.2**

| Campo | Contenido |
|---|---|
| Fecha y hora | 03/11/2026 10:15 GMT+1 |
| Propósito | Comprobar si Northbay Trading es una empresa real |
| Fuente | northbay-trading.example y Wayback Machine |
| Acción y resultado | La primera captura de la web es del 20/10/2026 |
| Decisión siguiente | Consultar el registro mercantil británico |

## Bloque 4 · Tema 1

| Actividad | Fase |
|---|---|
| A1 | Planificación y dirección |
| A2 | Obtención |
| A3 | Procesamiento |
| A4 | Análisis |
| A5 | Retroalimentación |

# Parte grupal

## Cronología en GMT+1

| Hora | Hecho |
|---|---|
| 17:00 (09/11) | Registro de ebronorte-empleo.example (F2-R2) |
| 17:30 (09/11) | Certificado de los dos dominios (F3-C1) |
| 08:30 | Oferta en Telegram (F1-S1) |
| 08:45 | Análisis de urlscan.io (F3-U1) |
| 09:00 | Primeras llamadas (F4-1) |
| 09:15 | Comentario en el foro (F1-S2) |
| 10:30 | 40 llamadas; siete personas han pagado (F4-2) |
| 11:20 | Desmentido oficial (F1-S3) |
| 11:30 | Reenvío al grupo de la plantilla (F4-4) |

Trampa: sin convertir las horas, parece que el desmentido (10:20) llegó antes de que siete personas hubieran pagado (10:30). En realidad llegó a las 11:20.

## Sección 1 · Tema 3

- **Valoración:** la oferta no es de la empresa. Confianza alta.
- **Evidencias:** F1-S3 (desmentido oficial), F4-3 (las ofertas solo se publican en la web), F2-R2 (dominio creado dos días antes) y F3-U1 (pide pagar).
- **Orden:** F1-S1 (08:30), F1-S2 (09:15), F1-S3 (11:20).
- **Lo que no sabemos:** quién está detrás y cuántas personas han pagado en total.

## Sección 2 · Tema 4

- **Dominios:** se crearon a la vez, dos días antes, y los controla quien pidió el certificado: son de la misma campaña. No dicen quién es.
- **IP:** no, porque la comparten 1.200 webs (F2-D2). Se piden el bloqueo y la retirada de los dos dominios.
- **Datos en riesgo:** foto del DNI, número de la Seguridad Social y datos de la tarjeta.
- **Lo más urgente:** publicar un aviso en la web y en LinkedIn y atender a los siete afectados. Lo hacen la dirección de personas y comunicación.

## Sección 3 · Tema 2

| Propuesta | Decisión | Motivo |
|---|---|---|
| F5-A | No | Interactúa con el adversario y usa datos falsos (N-19, criterio D.5) |
| F5-B | Sí | Medida proporcionada por el canal previsto |
| F5-C | Sí | Compartir con quien puede actuar (N-23) |
| F5-D | No | Datos innecesarios de terceros (N-02) |
| F5-E | Sí | Protege a los afectados (N-21) |

- **TLP para F5-C:** TLP:GREEN.
- **Plantilla:** la oferta es falsa; no deben reenviarla ni abrir el enlace, y las dudas se consultan con el departamento de personas.
