# Parte grupal de ejemplo · Operación Donaciones

*Examen de ejemplo R5 · Autobuses Ribera · actividad para cinco personas · 30 minutos*

## Instrucciones

- **Funcionamiento:** cada persona lee su ficha durante tres minutos. Después, el equipo pone en común las cinco fichas, porque ninguna basta por sí sola, y completa una única hoja de respuesta.
- **Requisito:** cada ficha debe citarse al menos una vez en la hoja (por ejemplo, F1-S2).

## Situación del ejercicio

Tras las inundaciones del fin de semana en Riolobos (pueblo ficticio), la Fundación Abrazo (ONG ficticia, dominio fundacionabrazo.example) organiza una recogida de donativos. El jueves 12/11/2026 empiezan a circular mensajes que piden donar en otra web «de la fundación». Su directora necesita una nota de situación antes de las 14:00 GMT+1.

**Pregunta del requerimiento:** ¿Es de la Fundación Abrazo la web de donativos que circula, qué riesgo supone para los donantes y qué debe hacer la fundación ahora?

Las fichas incluyen horas en UTC (marca Z) y en GMT+1. Pásalas todas a GMT+1 antes de ordenar los hechos.

# Fichas individuales

Cada ficha se entrega a una sola persona.

## Ficha F1 · Publicaciones

| ID | Origen | Hora mostrada | Contenido |
|---|---|---|---|
| F1-S1 | Cuenta de Instagram @abrazo_ayuda, creada el 10/11/2026 | 08:00Z | «Ayuda a Riolobos. Dona en abrazo-donaciones.example. Cada euro cuenta.» Usa el logotipo de la fundación. |
| F1-S2 | Cuenta de X de un cantante conocido | 10:30 GMT+1 | Comparte F1-S1: «Yo ya he donado, ¡ayudad!». 20.000 republicaciones. |
| F1-S3 | Web oficial fundacionabrazo.example | 10:15Z | «Solo recogemos donativos en esta web y en la cuenta bancaria que aparece aquí. No tenemos ninguna otra web.» |

## Ficha F2 · Registro y DNS

| ID | Dominio | Creado (RDAP) | Titular |
|---|---|---|---|
| F2-R1 | fundacionabrazo.example | 2012 | Fundación Abrazo |
| F2-R2 | abrazo-donaciones.example | 10/11/2026 22:00Z | Datos ocultos |

| ID | Fuente | Dato |
|---|---|---|
| F2-D1 | DNS pasivo | abrazo-donaciones.example apunta a la IP 203.0.113.75 |
| F2-D2 | Shodan, ficha de 203.0.113.75 | Alojamiento compartido con 700 webs de otros clientes |

## Ficha F3 · Certificado y página

| ID | Fuente | Contenido |
|---|---|---|
| F3-C1 | crt.sh | Certificado emitido el 10/11/2026 a las 22:15Z para abrazo-donaciones.example y ayuda-riolobos.example. |
| F3-U1 | Análisis ya existente en urlscan.io de abrazo-donaciones.example (12/11, 08:20Z) | Página con fotos de la inundación y el logotipo de la fundación. Pide los datos de la tarjeta o una transferencia a una cuenta de un banco extranjero. |

## Ficha F4 · Lo que sabe la fundación

Todas las horas están en GMT+1.

| ID | Hora | Hecho |
|---|---|---|
| F4-1 | 09:30 | Un donante escribe: ha donado en abrazo-donaciones.example y no recibe el certificado para Hacienda. |
| F4-2 | 10:00 | La cuenta bancaria de F3-U1 no es de la fundación. |
| F4-3 | 11:00 | Llegan 60 correos de donantes con dudas. |
| F4-4 | 11:30 | La fundación tiene un acuerdo con una agencia que gestiona sus redes sociales. |

## Ficha F5 · Propuestas del patronato

| ID | Propuesta |
|---|---|
| F5-A | Pedir a Instagram que retire @abrazo_ayuda por suplantar a la fundación. |
| F5-B | Escribir al cantante de F1-S2 para que borre su mensaje y comparta el desmentido. |
| F5-C | Enviar a INCIBE-CERT y a otras ONG los dos dominios falsos y la cuenta bancaria, para que puedan bloquearlos y avisar. |
| F5-D | Hacer una donación de 1 euro en la web falsa «para ver qué pasa». |
| F5-E | Publicar los correos de los 60 donantes con dudas «para que vean que no son los únicos». |

# Hoja de respuesta del equipo

Una sola hoja por equipo.

## Sección 1 · ¿Es de la fundación la web de donativos? (Tema 3)

**a) Valoración y grado de confianza.**

&nbsp;

&nbsp;

**b) Evidencias que la sostienen, con sus identificadores.**

&nbsp;

&nbsp;

**c) F1-S2 tiene 20.000 republicaciones. ¿La hace eso más creíble?**

&nbsp;

&nbsp;

**d) Algo que todavía no sabemos.**

&nbsp;

&nbsp;

## Sección 2 · La web falsa (Tema 4)

**a) Según el certificado F3-C1 y el RDAP F2-R2, ¿qué se puede decir de los dos dominios?**

&nbsp;

&nbsp;

**b) ¿Debe pedirse el bloqueo de la IP de F2-D1? ¿Por qué?**

&nbsp;

&nbsp;

**c) ¿Qué no se puede afirmar con estos datos?**

&nbsp;

&nbsp;

**d) Lo más urgente para proteger a los donantes y quién debe hacerlo.**

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

**c) Aviso para los donantes: qué debe decir y dónde se publica.**

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
