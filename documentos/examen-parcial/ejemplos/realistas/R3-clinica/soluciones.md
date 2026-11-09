# Soluciones orientativas · Ejemplo R3 · Clínica Arbós

*Resuelve el examen antes de consultarlas.*

# Parte individual

## Trampas del ejemplo

- ARB-S01 y ARB-S04 están en UTC; ARB-S02 y ARB-S03, en GMT+1.
- La foto de la oferta es real y de la clínica: eso no hace oficial la oferta.
- ARB-P04 tiene el mismo nombre que la gerente, pero nada la relaciona con la clínica.
- Que una oferta se comparta 3.000 veces mide su difusión, no su veracidad.
- La IP de la campaña es un alojamiento compartido: bloquearla afectaría a cientos de webs.
- SH-2 (la VPN) figura en el inventario: es lo esperado, no un problema.

## Bloque 1 · Tema 3

**1.1**

| Perfil | Relación | Evidencia |
|---|---|---|
| ARB-P01 | Oficial | Enlazada desde la web oficial |
| ARB-P02 | Suplantación probable | Creada en 10/2026, no enlazada, la desmiente ARB-S04 |
| ARB-P03 | Oficial | Figura en la web oficial |
| ARB-P04 | No se puede saber | Mismo nombre, pero ningún dato la relaciona; no se investiga más |

**1.2**

a) ARB-S01 (10:00), ARB-S02 (11:15), ARB-S04 (12:30), ARB-S03 (13:00).

b) La original es ARB-S01. ARB-S02 la repite. ARB-S03 depende de ARB-S04.

c) Es una foto de la propia clínica, copiada de su web. No demuestra quién creó la oferta.

d) No. Las veces que se comparte algo miden su difusión, no su veracidad.

**1.3**

| Fuente | Fiabilidad | Credibilidad |
|---|---|---|
| ARB-S01 | Baja (perfil que suplanta a la clínica) | Baja |
| ARB-S03 | Media o alta (medio que cita a la clínica) | La niega |
| ARB-S04 | Alta (cuenta oficial) | La niega |

**1.4**

a) Ejemplos:

- `"Clínica Arbós" "revisión gratuita"`: otras copias de la oferta.
- `"citas-arbos.example" OR "arbos-salud.example"`: otras páginas que enlacen a los dominios.

b) Elementos de la nota:

- **Valoración:** la oferta no es de la clínica.
- **Confianza:** alta.
- **Evidencias:** ARB-S04 y ARB-P02 (perfil reciente y no enlazado).
- **Limitación:** no se sabe quién está detrás ni cuántos pacientes enviaron sus datos.
- **Recomendaciones:** publicar el aviso T1 y denunciar ARB-P02 a Facebook.

## Bloque 2 · Tema 1

**2.1 a)**

| Componente | Respuesta |
|---|---|
| Destinatario | Director médico y comité de dirección |
| Decisión | Prioridades de inversión en 2027 |
| Objeto | Capacidad de seguir atendiendo ante un ransomware como el del Clínic |
| Horizonte | Antes del comité de diciembre; mira a 2027 |
| Alcance | Incluye sistemas clínicos y copias de seguridad; excluye detalles técnicos y quién atacó al Clínic |
| Producto | Informe breve, no técnico, que se lea en diez minutos |

**2.1 b)** X1, dato; X2, información; X3, inteligencia; X4, dato.

## Bloque 3 · Tema 4

**3.1** a) Dentro. b) Dentro. c) Fuera: acceso no autorizado (N-13). d) Fuera: interactúa con el adversario y expone la investigación. e) Dentro.

**3.2**

| Ficha | ¿De quién? | Justificación |
|---|---|---|
| SH-1 | Clínica | 192.0.2.41 está en el rango contratado |
| SH-2 | Clínica | Es la VPN del inventario |
| SH-3 | Proveedor | Plataforma compartida de la agencia |
| SH-4 | Campaña | Aloja citas-arbos.example |

**3.3**

a) Quien pidió el certificado controlaba los dos dominios: probablemente son de la misma campaña. No demuestra quién está detrás.

b) No: es un alojamiento compartido con 800 webs. Se bloquean los dos dominios.

c) `%.clinicaarbos.example` en crt.sh y `net:192.0.2.40/29` en Shodan.

**3.4**

| Hallazgo | Prioridad | Qué hacer y quién |
|---|---|---|
| H1 | Alta | Sistemas comprueba la cámara y la deja solo en la red interna |
| H2 | Baja | Ninguna acción: está en el inventario |
| H3 | Baja | Preguntar a la agencia si ese nombre se usa |
| H4 | Alta | Avisar a los pacientes y pedir la retirada del dominio |

Prioritario: H1, porque puede mostrar imágenes de pacientes y no debería verse desde Internet.

## Bloque 4 · Tema 2

**4.1**

| Propuesta | Decisión | Motivo |
|---|---|---|
| P1 | No | Engaño mediante identidad falsa (N-19) |
| P2 | Sí | Medida proporcionada y por el canal previsto |
| P3 | No | Minimización y respeto por las personas (N-02, N-21); además son datos de salud (N-06) |
| P4 | No | Faltan normas de uso fijadas e informadas (N-10) |
| P5 | Sí | INCIBE-CERT es el equipo de referencia (N-23) |

**4.2**

a) T1, TLP:CLEAR; T2, TLP:RED; T3, TLP:GREEN.

b) Ejemplos: usar un equipo y un navegador separados de la red de la clínica, no interactuar con la página ni con el número de WhatsApp y registrar cada consulta en la bitácora.

# Parte grupal

## Cronología en GMT+1

| Hora | Hecho |
|---|---|
| 20:00 (08/11) | Registro de brisa-pago.example (F2-R2) |
| 20:20 (08/11) | Certificado de los dos dominios (F3-C1) |
| 08:20 | Aviso del vigilante (F4-1) |
| 08:30 | Análisis de urlscan.io (F3-U1) y recordatorio de la empresa (F4-2) |
| 08:40 | Publicación del vecino (F1-S1) |
| 09:10 | El grupo vecinal la comparte (F1-S2) |
| 10:45 | Doce conductores con cargos (F4-3) |
| 11:05 | Aviso de la Policía Local (F1-S3) |

Trampa: sin convertir las horas, parece que la Policía avisó (10:05) antes de que llamaran los conductores (10:45). En realidad avisó a las 11:05.

## Sección 1 · Tema 3

- **Valoración:** los QR no son de Aparcamientos Brisa. Confianza alta.
- **Evidencias:** F4-2 (la empresa nunca usa QR), F2-R2 (dominio creado la víspera), F3-U1 (la página pide los datos de la tarjeta) y F1-S3.
- **Orden y dependencia:** F1-S1, F1-S2 y F1-S3. F1-S2 repite F1-S1.
- **Lo que no sabemos:** quién está detrás y cuántos conductores han pagado.

## Sección 2 · Tema 4

- **Certificado:** quien lo pidió controlaba los dos dominios; probablemente son de la misma campaña.
- **IP:** no se bloquea, porque la comparten 900 webs (F2-D2). Se bloquean los dominios.
- **Lo que no puede afirmarse:** quién es el autor.
- **Lo más urgente:** retirar las pegatinas (F4-4) y avisar a los conductores. Lo hacen mantenimiento y la dirección.

## Sección 3 · Tema 2

| Propuesta | Decisión | Motivo |
|---|---|---|
| F5-A | No | Interactúa con el adversario y expone la investigación (criterios D.3 y D.5) |
| F5-B | Sí | Medida proporcionada que conserva la evidencia |
| F5-C | Sí | Compartir con quien puede actuar (N-23) |
| F5-D | No | Minimización y respeto por las personas (N-02, N-21) |
| F5-E | Sí | Protege a los afectados |

- **TLP para F5-C:** TLP:GREEN, porque se comparte con una comunidad concreta y no en canales públicos.
- **Aviso:** «Aparcamientos Brisa nunca usa códigos QR. Solo se paga en el parquímetro o en Brisa Pay. Si has pagado con un QR, llama a tu banco y denuncia.» Se publica en la web, en las redes oficiales y en carteles en los parquímetros.
