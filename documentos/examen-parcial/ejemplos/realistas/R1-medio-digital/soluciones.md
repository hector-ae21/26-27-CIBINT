# Soluciones orientativas · Ejemplo R1 · Diario del Ebro

*Resuelve el examen antes de consultarlas.*

# Parte individual

## Trampas del ejemplo

- DEB-S01 y DEB-S03 están en UTC; DEB-S02 y DEB-S04, en GMT+1.
- DEB-P02 tiene el mismo nombre y la misma foto que la cuenta oficial, pero se creó tres días antes de la noticia.
- DEB-S02 dice que el diario confirma la noticia, pero solo reenvía DEB-S01.
- La IP de SH-2 la comparten 900 nombres de host: no es un activo del diario.
- Que el titular esté suprimido en el RDAP no indica malicia; el dominio legítimo también lo tiene suprimido.

## Bloque 1 · Tema 1

**1.1 a)**

| Componente | Respuesta |
|---|---|
| Destinatario | Comité de dirección |
| Decisión | Avisar a los lectores, pedir la retirada de las cuentas y revisar los accesos |
| Objeto | Las cuentas que suplantan a la periodista y la noticia falsa |
| Horizonte | Antes de las 12:00 |
| Alcance | Incluido: publicaciones abiertas y datos técnicos pasivos. Excluido: contactar con las cuentas o identificar a personas |
| Producto | Nota de situación |

**1.1 b)** Ejemplos de preguntas de inteligencia:

- ¿Hay indicios de que alguien haya accedido a las cuentas oficiales del diario?
- ¿Se está usando el nombre del diario en otras cuentas o canales?

En el caso de Twitter, el ataque se dirigió a las personas con acceso a las cuentas, no a la tecnología.

## Bloque 2 · Tema 3

**2.1**

| Perfil | Relación | Evidencia |
|---|---|---|
| DEB-P01 | Confirmada | Enlazada desde DEB-F01 |
| DEB-P02 | No confirmada, probable suplantación | Creada el 05/11 y desmentida en DEB-S03 |
| DEB-P03 | No relacionada | Homónima |
| DEB-P04 | No determinable | No está enlazada desde ninguna fuente oficial |

**2.2**

a) DEB-S01, DEB-S03 y DEB-S04 son originales. DEB-S02 depende de DEB-S01.

b) Orden en GMT+1: DEB-S04 (08:30), DEB-S01 (08:40), DEB-S02 (08:55), DEB-S03 (10:15).

c) La fotografía es de 2015 y corresponde a otra crecida. No demuestra quién controla DEB-P02.

d) DEB-S04 es una fuente primaria oficial e independiente que contradice la afirmación de DEB-S01.

**2.3**

| Fuente | Fiabilidad | Credibilidad |
|---|---|---|
| DEB-S01 | Baja | Baja |
| DEB-S02 | Baja | Baja, porque depende de DEB-S01 |
| DEB-S04 | Alta | Alta (para la negación) |

**2.4**

a) Ejemplos de consultas:

- `"martagil_ebro_"`
- `"Almozara" "desalojo" after:2026-11-05`
- `"diariodelebro-noticias.example"`

b) Elementos de la nota:

- **Valoración:** suplantación y noticia falsa.
- **Confianza:** alta.
- **Evidencias:** DEB-S03 y DEB-S04.
- **Limitación:** autoría desconocida.
- **Recomendaciones:** aviso a los lectores y solicitud de retirada a la plataforma.

## Bloque 3 · Tema 2

**3.1**

| Propuesta | Decisión | Motivo |
|---|---|---|
| A1 | No | Material no fiable que puede contener datos sensibles. Se abre solo en un entorno controlado y tras consultar |
| A2 | No | Acceso no autorizado (N-13, N-18) |
| A3 | Sí | Canal oficial y respuesta coordinada (N-23) |
| A4 | No | Minimización y datos de terceros (N-02, N-12) |
| A5 | Sí | Trazabilidad sin copiar datos (N-03) |

**3.2**

a) T1: TLP:RED (protege la identidad de quien mantiene el contacto). T2: TLP:AMBER+STRICT. T3: TLP:CLEAR.

b) Ejemplos de medidas:

- necesidad de conocer;
- canal seguro con la fuente;
- no usar cuentas personales;
- no reenviar el archivo.

## Bloque 4 · Tema 4

**4.1** a) Dentro. b) Fuera: contacta con el adversario. c) Dentro. d) Fuera: es un acceso no autorizado. e) Dentro.

**4.2**

a) No: es un alojamiento compartido del proveedor.

b) Hubo un precertificado para ese nombre, pero no consta que se desplegara. Queda pendiente de revisar con el proveedor.

c) El dominio se creó tres días antes que DEB-P02, lo que encaja con la campaña. Que el titular esté suprimido no indica nada.

d) El TXT autoriza a un servicio de boletines a enviar correo en nombre del dominio. No permite afirmar que haya un uso indebido.

**4.3**

a) Una aplicación Express detrás de una CDN.

b) La CDN oculta el servidor de origen, así que no se puede saber cuál es.

**4.4**

| Hallazgo | Prioridad |
|---|---|
| H1 | Alta para validación: es un panel de administración que no figura en el inventario |
| H2 | Pendiente |
| H3 | Revisión ordinaria |
| H4 | Acción defensiva externa |

Se acepta como prioritario H1 o H4 si se justifica.

# Parte grupal

## Cronología en GMT+1

| Hora | Hecho |
|---|---|
| 22:10 (08/11) | Registro de enviosrayo-pago.example (F2-R2) |
| 22:14 (08/11) | Registro de moncayo-pedidos.example (F2-R3) |
| 22:20 (08/11) | Emisión del certificado F3-C1 |
| 09:05 | Análisis de urlscan.io (F3-U1) |
| 09:12 | SMS recibido (F1-S1) |
| 09:30 | Primeras llamadas (F4-1) |
| 09:40 | Publicación en el grupo de vecinos (F1-S2) |
| 10:15 | 64 llamadas y 9 pagos (F4-2) |
| 10:40 | Enlace compartido en el chat interno (F4-3) |
| 11:30 | Aviso oficial de Envíos Rayo (F1-S3) |

Trampa: si no se convierte la hora de F1-S2 a GMT+1, parece que se publicó antes del SMS.

## Sección 1 · Tema 3

- **Valoración:** los SMS no proceden de Envíos Rayo ni de Moncayo. Confianza alta.
- **Evidencias:**
  - F1-S3: fuente primaria de Envíos Rayo.
  - F2-R2 y F2-R3: dominios creados la noche anterior.
  - F3-U1: formulario que pide los datos completos de la tarjeta.
- **Dependencias:** F1-S2 depende de F1-S1.
- **Limitación:** autoría desconocida.

## Sección 2 · Tema 4

- **IP compartida:** relación débil, porque la comparten 1.500 nombres.
- **Certificado:** relación más fuerte. Además, correos-aviso-pago.example probablemente forma parte de la misma campaña.
- **No permite afirmar:** la autoría.
- **Indicadores:** los tres dominios.
- **Acción urgente:** avisar a los clientes y atender a los 9 que pagaron (bloquear la tarjeta y denunciar). Responsable: atención al cliente, coordinada con seguridad.

## Sección 3 · Tema 2

| Propuesta | Decisión | Motivo |
|---|---|---|
| F5-A | No | Minimización (N-02); se avisa a los clientes con los datos de contacto que ya constan en la empresa |
| F5-B | Sí | Aviso público |
| F5-C | Sí | Compartir con quien lo necesita |
| F5-D | No | Interactúa con el adversario y puede suponer un engaño o un riesgo |
| F5-E | Sí | También se puede notificar a INCIBE-CERT (N-23) |

- **TLP de F5-C:** TLP:GREEN.
- **Enlace en el chat interno (F4-3):** retirar el mensaje, pedir que nadie lo abra y comprobar si alguien lo ha abierto.
