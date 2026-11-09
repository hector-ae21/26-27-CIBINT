# Parte grupal de ejemplo · Operación Paquete

*Examen de ejemplo R1 · Diario del Ebro · actividad para cinco personas · 30 minutos*

## Instrucciones

- **Funcionamiento:** cada persona lee su ficha durante tres minutos. Después, el equipo pone en común las cinco fichas, porque ninguna basta por sí sola, y completa una única hoja de respuesta.
- **Requisito:** cada ficha debe citarse al menos una vez en la hoja (por ejemplo, F2-R2).

## Situación del ejercicio

El lunes 09/11/2026, Supermercados Moncayo, una cadena de 40 tiendas con venta en línea, recibe en su servicio de atención al cliente decenas de llamadas por un SMS. El mensaje, que aparenta venir de la empresa de reparto Envíos Rayo, pide pagar 1,99 euros para «liberar» un pedido. La directora de atención al cliente necesita una nota de situación antes de las 14:00 GMT+1.

**Pregunta del requerimiento:** ¿Proceden los SMS de Envíos Rayo o de Supermercados Moncayo, qué riesgo suponen para los clientes y qué debe hacer la empresa ahora?

Las fichas incluyen horas en UTC (marca Z) y en GMT+1. Unifícalas antes de razonar sobre la secuencia de los hechos.

# Fichas individuales

Cada ficha se entrega a una sola persona.

## Ficha F1 · Mensajes y publicaciones

| ID | Origen | Hora mostrada | Contenido |
|---|---|---|---|
| F1-S1 | SMS con remitente «ENVIOS-RAYO» | 09:12 GMT+1 | «Su pedido de Supermercados Moncayo está retenido. Pague 1,99 € de gastos de envío en enviosrayo-pago.example antes de 24 h.» |
| F1-S2 | Publicación en un grupo de Facebook de vecinos | 08:40Z | Captura del SMS: «¿A alguien más le ha llegado? Parece real». |
| F1-S3 | Web oficial de Envíos Rayo, apartado de avisos | 10:30Z | «Nunca pedimos pagos por SMS. Solo gestionamos incidencias desde nuestra aplicación oficial.» |

## Ficha F2 · Registro y DNS

| ID | Dominio | Creado (RDAP) | Titular |
|---|---|---|---|
| F2-R1 | enviosrayo.example | 2012 | Envíos Rayo, S.A. |
| F2-R2 | enviosrayo-pago.example | 08/11/2026 21:10Z | Datos suprimidos |
| F2-R3 | moncayo-pedidos.example | 08/11/2026 21:14Z | Datos suprimidos |

| ID | Fuente | Dato |
|---|---|---|
| F2-D1 | DNS pasivo | enviosrayo-pago.example, registro A: 203.0.113.80 |
| F2-D2 | DNS pasivo | moncayo-pedidos.example, registro A: 203.0.113.80 |
| F2-D3 | Shodan, ficha de 203.0.113.80 | Alojamiento compartido con 1.500 nombres de host |

## Ficha F3 · Certificados y web

| ID | Fuente | Contenido |
|---|---|---|
| F3-C1 | crt.sh | Certificado emitido el 08/11/2026 a las 21:20Z con los nombres enviosrayo-pago.example, moncayo-pedidos.example y correos-aviso-pago.example. |
| F3-U1 | Análisis ya existente en urlscan.io de enviosrayo-pago.example (09/11, 08:05Z) | Formulario con el logotipo de Envíos Rayo en el que se piden los datos completos de la tarjeta para un cargo de 1,99 €. |

## Ficha F4 · Lo que ocurre en Supermercados Moncayo

Todas las horas están en GMT+1.

| ID | Hora | Hecho |
|---|---|---|
| F4-1 | 09:30 | Primeras llamadas de clientes a atención al cliente. |
| F4-2 | 10:15 | Ya se han recibido 64 llamadas; 9 clientes dicen que pagaron. |
| F4-3 | 10:40 | Un empleado de atención al cliente comparte el enlace del SMS en el chat interno «para que lo veáis». |
| F4-4 | 11:00 | La empresa confirma que trabaja con Envíos Rayo para los pedidos en línea. |

## Ficha F5 · Propuestas de la dirección

| ID | Propuesta |
|---|---|
| F5-A | Pedir la lista de clientes que han llamado para buscar sus perfiles en redes y avisarles. |
| F5-B | Publicar en la web y en las redes de la empresa un aviso con los dominios falsos y el canal oficial. |
| F5-C | Compartir los indicadores con Envíos Rayo y con la asociación de comercio de Aragón. |
| F5-D | Rellenar el formulario falso con una tarjeta de pruebas para ver adónde envía los datos. |
| F5-E | Pedir al registrador y al proveedor de alojamiento la retirada de los dominios, con las evidencias. |

# Hoja de respuesta del equipo

Una sola hoja por equipo.

## Sección 1 · ¿De quién son los SMS? (Tema 3)

**a) Valoración y grado de confianza.**

&nbsp;

&nbsp;

**b) Evidencias que la sostienen, con sus identificadores.**

&nbsp;

&nbsp;

**c) Publicaciones que dependen de otras.**

&nbsp;

&nbsp;

**d) Una limitación.**

&nbsp;

&nbsp;

## Sección 2 · Infraestructura y riesgo (Tema 4)

**a) Qué relación entre los dominios sostiene la IP compartida y cuál sostiene el certificado.**

&nbsp;

&nbsp;

**b) Qué no permite afirmar ninguno de los dos.**

&nbsp;

&nbsp;

**c) Indicadores que proponéis bloquear o comunicar.**

&nbsp;

&nbsp;

**d) Acción más urgente para proteger a los clientes y quién debe hacerla.**

&nbsp;

&nbsp;

## Sección 3 · Decisiones y difusión (Tema 2)

a) Decisión sobre cada propuesta de F5: sí, con condiciones o no.

| Propuesta | Decisión | Motivo y referencia del anexo |
|---|---|---|
| F5-A | | |
| F5-B | | |
| F5-C | | |
| F5-D | | |
| F5-E | | |

**b) Etiqueta TLP para F5-C y justificación.**

&nbsp;

&nbsp;

**c) Qué debe hacerse con el enlace compartido en el chat interno (F4-3).**

&nbsp;

&nbsp;

## Firmas del equipo

| Ficha | Nombre y apellidos | Firma |
|---|---|---|
| F1 | | |
| F2 | | |
| F3 | | |
| F4 | | |
| F5 | | |
