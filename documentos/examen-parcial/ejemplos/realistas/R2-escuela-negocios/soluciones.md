# Soluciones orientativas · Ejemplo R2 · Lumen Business School

*Resuelve el examen antes de consultarlas.*

# Parte individual

## Trampas del ejemplo

- El PTR de 198.51.100.22 contiene «lumen», pero esa IP no está en el contrato.
- Los «me gusta» y los comentarios miden difusión, no veracidad.
- LUM-S01 y LUM-S03 están en UTC; LUM-S02, en GMT+1.
- Un registro mercantil acredita que una sociedad existe, no que esté relacionada con la escuela.
- E5 es una regla de control: es técnica, no táctica.

## Bloque 1 · Tema 4

**1.1**

| Ficha | Clasificación | Justificación |
|---|---|---|
| SH-1 | Organización | Es la IP contratada por la sede |
| SH-2 | No puede saberse | La IP no está en el contrato; que el nombre inverso (PTR) contenga «lumen» es solo una pista |
| SH-3 | Proveedor | Campus en una plataforma compartida |
| SH-4 | Proveedor (CDN) | No es de la organización; está relacionada con la campaña |

**1.2**

a) Ejemplo: «El índice de servicios observó el 06/11/2026 el escritorio remoto en 3389/TCP de 198.51.100.21».

b) El inventario indica que el escritorio remoto solo se usa a través de la VPN, pero se observó accesible desde Internet.

c) Sistemas confirma el estado actual y restringe el acceso a la VPN. No se hacen pruebas de acceso.

**1.3**

a) Ejemplos:

- `ip:198.51.100.21`
- `hostname:lumen.example port:443`

b) `%.lumen.example`

c) Quien solicitó el certificado controlaba los dos dominios. No demuestra quién está detrás.

**1.4**

| Hallazgo | Prioridad |
|---|---|
| H1 | Alta: sistemas comprueba y cierra el acceso fuera de la VPN |
| H2 | Media: preguntar a la operadora si esa IP es de la escuela |
| H3 | Baja: preguntar a la agencia web si el nombre se va a usar |
| H4 | Alta: avisar a los candidatos y pedir la retirada del dominio |

## Bloque 2 · Tema 2

**2.1**

| Propuesta | Decisión | Motivo |
|---|---|---|
| P1 | No | Engaño (N-19) |
| P2 | No | Acceso no autorizado (N-13, N-18) |
| P3 | Con condiciones | Política comunicada y proporcionalidad (N-02) |
| P4 | No | Minimización y respeto por las personas (N-02, N-21) |
| P5 | Sí | Medida proporcionada y con trazabilidad |

**2.2**

| Campo | Contenido |
|---|---|
| Fecha y hora | 05/11/2026 17:20 GMT+1 |
| Propósito | Valorar el anuncio de venta de exámenes |
| Fuente | Captura enviada por un alumno, conservada con su huella SHA-256 |
| Acción y resultado | Se observa un anuncio por 30 €. No se copian datos personales |
| Decisión siguiente | Informar a la coordinación y a la DPD; no entrar en el grupo |

## Bloque 3 · Tema 3

**3.1**

| Perfil | Relación |
|---|---|
| LUM-P01 | Confirmada |
| LUM-P02 | Suplantación probable |
| LUM-P03 | Confirmada |
| LUM-P04 | No determinable |

**3.2**

a) Orden en GMT+1: LUM-S01 (02/11, 18:00), LUM-S02 (03/11, 09:30), LUM-S03 (04/11, 09:00).

b) No. Miden difusión, no veracidad.

c) La imagen procede de un banco de imágenes de 2020: no es el campus de Lumen.

d) Ninguna fuente independiente. LUM-S02 solo pregunta, y LUM-F01 y LUM-S03 lo contradicen.

**3.3**

a) La sociedad maltesa existe desde el 20/10/2026, pero no consta como parte de Lumen (LUM-R03). No se puede afirmar la autoría.

b)

| Fuente | Fiabilidad | Credibilidad |
|---|---|---|
| LUM-S01 | Baja | Baja |
| LUM-F01 | Alta | La niega |
| LUM-R02 | Alta, sobre la existencia de la sociedad | No dice nada sobre la relación con Lumen |

**3.4**

a) Ejemplos:

- `"Beca Excelencia 100%" "Lumen"`
- `"becas-lumen.example" OR "becas-lumenbs.example"`

b) Elementos de la nota:

- **Valoración:** beca falsa ajena a Lumen.
- **Confianza:** alta.
- **Evidencias:** LUM-F01 y LUM-S03.
- **Limitación:** autoría desconocida.
- **Recomendación:** aviso a los candidatos («nunca cobramos por solicitar una beca»).

c) Información aprovechada: la marca y el logotipo, el nombre de la directora de admisiones y el calendario de convocatorias.

## Bloque 4 · Tema 1

| Elemento | Nivel |
|---|---|
| E1 | Técnico |
| E2 | Táctico |
| E3 | Estratégico |
| E4 | Operacional |
| E5 | Técnico |

# Parte grupal

## Cronología en GMT+1

| Hora | Hecho |
|---|---|
| 19:30 (09/11) | Registro de usv-matricula.example (F2-R2) |
| 19:45 (09/11) | Emisión del certificado F3-C1 |
| 08:55 | Envío del correo (F1-S1) |
| 09:05 | Primeras consultas de alumnos (F4-1) |
| 09:10 | Análisis de urlscan.io (F3-U1) |
| 09:20 | Publicación de la asociación de estudiantes (F1-S2) |
| 09:50 | 23 alumnos introducen sus datos (F4-2) |
| 10:20 | Inicios de sesión desde otro país (F4-3) |
| 10:40 | Aviso oficial de la universidad (F1-S3) |

Trampa: sin convertir las horas, parece que el aviso oficial (09:40) llegó antes de que los 23 alumnos introdujeran sus datos. En realidad llegó a las 10:40, una hora después.

## Sección 1 · Tema 3

- **Valoración:** el correo no procede de la universidad. Confianza alta.
- **Evidencias:**
  - F1-S3: fuente primaria de la universidad.
  - F2-R2: dominio creado la víspera.
  - F3-U1: página que copia el acceso al campus.
- **Dependencias:** F1-S2 depende de F1-S1.
- **Limitación:** se desconocen la autoría y el número total de alumnos afectados.

## Sección 2 · Tema 4

- **Certificado:** quien lo solicitó controlaba los tres nombres. campus-usv.example y usv-becas.example probablemente forman parte de la misma campaña.
- **Registro MX:** el dominio recibe correo en un proveedor gratuito. No prueba desde dónde se envió el mensaje.
- **Lo que no puede afirmarse:** la autoría.
- **Qué se bloquea:** los tres dominios del certificado (usv-matricula, campus-usv y usv-becas). La IP no, porque es un alojamiento compartido con 640 nombres (F2-D3).
- **Acción interna más urgente:** cerrar las sesiones y cambiar las credenciales de las 23 cuentas, empezando por las 4 con accesos desde otro país, y revisar qué se hizo con ellas. Responsable: el servicio de informática.

## Sección 3 · Tema 2

| Propuesta | Decisión | Motivo |
|---|---|---|
| F5-A | No | Acceso no autorizado con credenciales ajenas (N-13, N-18) |
| F5-B | Sí | Lo prevé la política de seguridad (F4-4) |
| F5-C | Sí | Compartir con quien lo necesita (N-23) |
| F5-D | No | Minimización y respeto por las personas (N-02, N-21) |
| F5-E | Sí | Posible violación de seguridad (N-08) |

- **TLP para F5-C:** TLP:GREEN.
- **Aviso a los alumnos:** que la universidad no ha enviado ese correo, que nunca pide la contraseña, que quien la haya introducido debe cambiarla y avisar al servicio de informática. Se difunde por el campus y por los canales oficiales.
