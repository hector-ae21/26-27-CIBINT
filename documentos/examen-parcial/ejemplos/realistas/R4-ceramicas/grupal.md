# Parte grupal de ejemplo · Operación Empleo

*Examen de ejemplo R4 · Cerámicas Alba · actividad para cinco personas · 30 minutos*

## Instrucciones

- **Funcionamiento:** cada persona lee su ficha durante tres minutos. Después, el equipo pone en común las cinco fichas, porque ninguna basta por sí sola, y completa una única hoja de respuesta.
- **Requisito:** cada ficha debe citarse al menos una vez en la hoja (por ejemplo, F2-R2).

## Situación del ejercicio

El miércoles 11/11/2026, el departamento de personas de Logística Ebro Norte (empresa ficticia de transporte, dominio ebronorte.example) recibe muchas llamadas. Circula una oferta de empleo de «mozo de almacén» en su nombre que pide pagar 120 euros por un «curso de formación obligatorio» antes de la entrevista. La directora de personas necesita una nota de situación antes de las 14:00 GMT+1.

**Pregunta del requerimiento:** ¿Es de Logística Ebro Norte la oferta, qué riesgo supone para los candidatos y qué debe hacer la empresa ahora?

Las fichas incluyen horas en UTC (marca Z) y en GMT+1. Pásalas todas a GMT+1 antes de ordenar los hechos.

# Fichas individuales

Cada ficha se entrega a una sola persona.

## Ficha F1 · Publicaciones

| ID | Origen | Hora mostrada | Contenido |
|---|---|---|---|
| F1-S1 | Canal de Telegram «Empleo Zaragoza Hoy» (12.000 suscriptores) | 07:30Z | Oferta de Logística Ebro Norte: «1.800 €/mes, sin experiencia. Inscríbete en ebronorte-empleo.example». |
| F1-S2 | Foro de una web de empleo | 09:15 GMT+1 | «¿Alguien ha hecho el curso de 120 € de Ebro Norte? Yo ya he pagado.» |
| F1-S3 | Página de LinkedIn oficial de Logística Ebro Norte, enlazada desde su web | 10:20Z | «No tenemos ninguna oferta abierta de mozo de almacén. Nunca cobramos por un proceso de selección.» |

## Ficha F2 · Registro y DNS

| ID | Dominio | Creado (RDAP) | Titular |
|---|---|---|---|
| F2-R1 | ebronorte.example | 2005 | Logística Ebro Norte, S.L. |
| F2-R2 | ebronorte-empleo.example | 09/11/2026 16:00Z | Datos ocultos |

| ID | Fuente | Dato |
|---|---|---|
| F2-D1 | DNS pasivo | ebronorte-empleo.example apunta a la IP 203.0.113.210 |
| F2-D2 | Shodan, ficha de 203.0.113.210 | Alojamiento compartido con 1.200 webs de otros clientes |

## Ficha F3 · Certificado y página

| ID | Fuente | Contenido |
|---|---|---|
| F3-C1 | crt.sh | Certificado emitido el 09/11/2026 a las 16:30Z para ebronorte-empleo.example y ebronorte-rrhh.example. |
| F3-U1 | Análisis ya existente en urlscan.io de ebronorte-empleo.example (11/11, 07:45Z) | Formulario con el logotipo de la empresa que pide una foto del DNI, el número de la Seguridad Social y el pago de 120 euros con tarjeta. |

## Ficha F4 · Lo que sabe la empresa

Todas las horas están en GMT+1.

| ID | Hora | Hecho |
|---|---|---|
| F4-1 | 09:00 | Llegan las primeras llamadas de candidatos preguntando por el curso. |
| F4-2 | 10:30 | Ya son 40 llamadas. Siete personas dicen haber pagado y enviado la foto de su DNI. |
| F4-3 | 10:45 | La empresa publica sus ofertas solo en su web, en el apartado «Trabaja con nosotros». |
| F4-4 | 11:30 | Un empleado ha reenviado la oferta falsa a un grupo de WhatsApp de la plantilla preguntando si es real. |

## Ficha F5 · Propuestas de la dirección

| ID | Propuesta |
|---|---|
| F5-A | Inscribirse en la oferta con un DNI inventado para ver qué piden después. |
| F5-B | Pedir a Telegram que retire la publicación de F1-S1 por suplantar a la empresa. |
| F5-C | Enviar a INCIBE-CERT y a la asociación de empresas de transporte los dos dominios falsos, para que puedan bloquearlos. |
| F5-D | Pedir al foro de F1-S2 los datos de todas las personas que han comentado la oferta. |
| F5-E | Informar a los siete candidatos que han enviado su DNI de los riesgos y de que pueden denunciar. |

# Hoja de respuesta del equipo

Una sola hoja por equipo.

## Sección 1 · ¿Es de la empresa la oferta? (Tema 3)

**a) Valoración y grado de confianza.**

&nbsp;

&nbsp;

**b) Evidencias que la sostienen, con sus identificadores.**

&nbsp;

&nbsp;

**c) Orden de F1-S1, F1-S2 y F1-S3 en GMT+1.**

&nbsp;

&nbsp;

**d) Algo que todavía no sabemos.**

&nbsp;

&nbsp;

## Sección 2 · La web de la oferta (Tema 4)

**a) Según el certificado F3-C1 y el RDAP F2-R2, ¿qué se puede decir de los dos dominios?**

&nbsp;

&nbsp;

**b) ¿Debe la empresa pedir que se bloquee la IP de F2-D1? ¿Por qué?**

&nbsp;

&nbsp;

**c) ¿Qué datos de los candidatos están en riesgo según F3-U1?**

&nbsp;

&nbsp;

**d) Lo más urgente para proteger a los candidatos y quién debe hacerlo.**

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

**c) Qué decir a la plantilla sobre el mensaje reenviado en F4-4.**

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
