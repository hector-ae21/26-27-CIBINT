# Parte grupal de ejemplo · Operación Matrícula

*Examen de ejemplo R2 · Lumen Business School · actividad para cinco personas · 30 minutos*

## Instrucciones

- **Funcionamiento:** cada persona lee su ficha durante tres minutos. Después, el equipo pone en común las cinco fichas, porque ninguna basta por sí sola, y completa una única hoja de respuesta.
- **Requisito:** cada ficha debe citarse al menos una vez en la hoja (por ejemplo, F3-C1).

## Situación del ejercicio

El martes 10/11/2026, cientos de alumnos de la Universidad San Valero (ficticia, dominio usv.example) reciben un correo que les avisa de que su matrícula «quedará anulada» si no la renuevan en un enlace. Varios alumnos introducen su usuario y su contraseña del campus. El vicerrectorado necesita una nota de situación antes de las 13:00 GMT+1.

**Pregunta del requerimiento:** ¿Procede el correo de la universidad, qué riesgo supone para los alumnos y para los sistemas y qué debe hacerse ahora?

Las fichas incluyen horas en UTC (marca Z) y en GMT+1. Unifícalas antes de razonar sobre la secuencia de los hechos.

# Fichas individuales

Cada ficha se entrega a una sola persona.

## Ficha F1 · El correo y las publicaciones

| ID | Origen | Hora mostrada | Contenido |
|---|---|---|---|
| F1-S1 | Correo de «Secretaría USV» desde secretaria@usv-matricula.example | 07:55Z | «Su matrícula quedará anulada hoy a las 14:00 si no la renueva en usv-matricula.example/renovar.» |
| F1-S2 | Cuenta de X de una asociación de estudiantes | 09:20 GMT+1 | Captura del correo: «Ojo, parece oficial, renovad cuanto antes». |
| F1-S3 | Web oficial usv.example, apartado de avisos | 09:40Z | «La universidad no ha enviado ningún aviso de renovación. Nunca pedimos la contraseña por correo.» |

## Ficha F2 · Registro y DNS

| ID | Dominio | Creado (RDAP) | Titular |
|---|---|---|---|
| F2-R1 | usv.example | 1999 | Universidad San Valero |
| F2-R2 | usv-matricula.example | 09/11/2026 18:30Z | Datos suprimidos |

| ID | Fuente | Dato |
|---|---|---|
| F2-D1 | DNS pasivo | usv-matricula.example, registro A: 203.0.113.140 |
| F2-D2 | DNS pasivo | usv-matricula.example, registro MX: mx.correo-gratis.example |
| F2-D3 | Shodan, ficha de 203.0.113.140 | Alojamiento compartido con 640 nombres de host |

## Ficha F3 · Certificados y web

| ID | Fuente | Contenido |
|---|---|---|
| F3-C1 | crt.sh | Certificado emitido el 09/11/2026 a las 18:45Z con los nombres usv-matricula.example, campus-usv.example y usv-becas.example. |
| F3-U1 | Análisis ya existente en urlscan.io de usv-matricula.example (10/11, 08:10Z) | Copia de la página de acceso al campus que pide el usuario, la contraseña y el código de verificación del móvil. |

## Ficha F4 · Lo que ocurre en la universidad

Todas las horas están en GMT+1.

| ID | Hora | Hecho |
|---|---|---|
| F4-1 | 09:05 | El servicio de informática recibe las primeras consultas de alumnos. |
| F4-2 | 09:50 | 23 alumnos dicen que introdujeron su usuario, su contraseña y el código del móvil. |
| F4-3 | 10:20 | Se detectan inicios de sesión desde otro país en 4 de esas cuentas. |
| F4-4 | 10:30 | La política de seguridad de la universidad permite bloquear cuentas y cerrar sesiones si hay un incidente. |

## Ficha F5 · Propuestas del vicerrectorado

| ID | Propuesta |
|---|---|
| F5-A | Iniciar sesión con las credenciales de uno de los alumnos afectados desde el país del atacante «para ver qué hace». |
| F5-B | Cerrar las sesiones activas de las 23 cuentas y obligar a cambiar las contraseñas. |
| F5-C | Enviar a otras universidades y a INCIBE-CERT los dominios y la IP usados en el engaño, para que puedan bloquearlos. |
| F5-D | Publicar en las redes de la universidad la lista de alumnos que cayeron en el engaño, «para que sirva de ejemplo». |
| F5-E | Valorar con la delegada de protección de datos si hay una violación de seguridad que deba notificarse. |

# Hoja de respuesta del equipo

Una sola hoja por equipo.

## Sección 1 · ¿Procede el correo de la universidad? (Tema 3)

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

**a) Según el certificado F3-C1, ¿qué tienen en común los tres dominios? ¿Para qué sirve el registro MX de F2-D2?**

&nbsp;

&nbsp;

**b) ¿Qué no se puede afirmar con esas dos fuentes?**

&nbsp;

&nbsp;

**c) Dominios o direcciones que la universidad debería bloquear en su correo y en su red.**

&nbsp;

&nbsp;

**d) ¿Qué es lo más urgente que debe hacer la universidad con las cuentas de los alumnos y quién debe hacerlo?**

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

**c) Aviso para todos los alumnos: qué debe decir y por qué medio se publica.**

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
