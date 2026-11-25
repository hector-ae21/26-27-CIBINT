# Parte grupal de ejemplo · Operación Parquímetro

*Examen de ejemplo R3 · Clínica Arbós · actividad para cinco personas · 30 minutos*

## Instrucciones

- **Funcionamiento:** cada persona lee su ficha durante tres minutos. Después, el equipo pone en común las cinco fichas, porque ninguna basta por sí sola, y completa una única hoja de respuesta.
- **Requisito:** cada ficha debe citarse al menos una vez en la hoja (por ejemplo, F3-C1).

## Situación del ejercicio

El lunes 09/11/2026 aparecen pegatinas con un código QR sobre los parquímetros de la zona azul de Villamar (ciudad ficticia). El QR lleva a una página que pide la tarjeta bancaria para «pagar el aparcamiento». La zona azul la gestiona Aparcamientos Brisa (empresa ficticia, dominio aparcamientosbrisa.example). Su directora necesita una nota de situación antes de las 13:00 GMT+1.

**Pregunta del requerimiento:** ¿Son de Aparcamientos Brisa los códigos QR, qué riesgo suponen para los conductores y qué debe hacerse ahora?

Las fichas incluyen horas en UTC (marca Z) y en GMT+1. Pásalas todas a GMT+1 antes de ordenar los hechos.

# Fichas individuales

Cada ficha se entrega a una sola persona.

## Ficha F1 · Publicaciones

| ID | Origen | Hora mostrada | Contenido |
|---|---|---|---|
| F1-S1 | Cuenta de X de un vecino | 07:40Z | Foto de un parquímetro con una pegatina QR: «Ahora se paga con QR, mucho más cómodo». |
| F1-S2 | Grupo de Facebook «Vecinos de Villamar» | 09:10 GMT+1 | Comparte la foto de F1-S1: «Ya podéis pagar con el móvil». |
| F1-S3 | Cuenta oficial de la Policía Local de Villamar | 10:05Z | «Los QR pegados en los parquímetros son un fraude. No introduzcáis la tarjeta.» |

## Ficha F2 · Registro y DNS

| ID | Dominio | Creado (RDAP) | Titular |
|---|---|---|---|
| F2-R1 | aparcamientosbrisa.example | 2008 | Aparcamientos Brisa, S.A. |
| F2-R2 | brisa-pago.example | 08/11/2026 19:00Z | Datos ocultos |

| ID | Fuente | Dato |
|---|---|---|
| F2-D1 | DNS pasivo | brisa-pago.example apunta a la IP 203.0.113.160 |
| F2-D2 | Shodan, ficha de 203.0.113.160 | Alojamiento compartido con 900 webs de otros clientes |

## Ficha F3 · Certificado y página

| ID | Fuente | Contenido |
|---|---|---|
| F3-C1 | crt.sh | Certificado emitido el 08/11/2026 a las 19:20Z para brisa-pago.example y zonaazul-villamar.example. |
| F3-U1 | Análisis ya existente en urlscan.io de brisa-pago.example (09/11, 07:30Z) | Página con el logotipo de Aparcamientos Brisa que pide el número de la tarjeta, la fecha de caducidad y el código de seguridad. |

## Ficha F4 · Lo que sabe Aparcamientos Brisa

Todas las horas están en GMT+1.

| ID | Hora | Hecho |
|---|---|---|
| F4-1 | 08:20 | Un vigilante avisa de pegatinas QR en 30 parquímetros de la calle Mayor. |
| F4-2 | 08:30 | La empresa recuerda que solo se paga en el parquímetro o en su aplicación oficial «Brisa Pay». Nunca ha usado códigos QR. |
| F4-3 | 10:45 | Doce conductores llaman: pagaron con el QR y su banco les ha cobrado tres cargos de 49 euros. |
| F4-4 | 11:00 | El equipo de mantenimiento puede retirar las pegatinas hoy mismo. |

## Ficha F5 · Propuestas de la dirección

| ID | Propuesta |
|---|---|
| F5-A | Pagar en la página falsa con una tarjeta de prepago «para ver a dónde va el dinero». |
| F5-B | Retirar las pegatinas y fotografiar cada una con su fecha y su ubicación antes de quitarla. |
| F5-C | Enviar a la Policía Local, a INCIBE-CERT y a otras empresas de aparcamiento los dos dominios de la página falsa, para que puedan bloquearlos. |
| F5-D | Publicar en redes las matrículas de los conductores que pagaron con el QR, «para que sirva de aviso». |
| F5-E | Recomendar a los conductores afectados que llamen a su banco y denuncien. |

# Hoja de respuesta del equipo

Una sola hoja por equipo.

## Sección 1 · ¿Son de la empresa los códigos QR? (Tema 3)

**a) Valoración y grado de confianza.**

&nbsp;

&nbsp;

**b) Evidencias que la sostienen, con sus identificadores.**

&nbsp;

&nbsp;

**c) Orden de F1-S1, F1-S2 y F1-S3 en GMT+1. ¿Cuál repite a otra?**

&nbsp;

&nbsp;

**d) Algo que todavía no sabemos.**

&nbsp;

&nbsp;

## Sección 2 · La página falsa (Tema 4)

**a) Según el certificado F3-C1, ¿qué tienen en común los dos dominios?**

&nbsp;

&nbsp;

**b) ¿Debe la empresa bloquear la IP de F2-D1? ¿Por qué?**

&nbsp;

&nbsp;

**c) ¿Qué no se puede afirmar con estos datos?**

&nbsp;

&nbsp;

**d) Lo más urgente para proteger a los conductores y quién debe hacerlo.**

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

**b) Etiqueta TLP para lo que se envía en F5-C y justificación.**

&nbsp;

&nbsp;

**c) Aviso para los conductores: qué debe decir y dónde se publica.**

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
