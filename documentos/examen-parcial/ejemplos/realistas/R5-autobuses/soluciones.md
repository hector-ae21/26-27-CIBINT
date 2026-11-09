# Soluciones orientativas · Ejemplo R5 · Autobuses Ribera

*Resuelve el examen antes de consultarlas.*

# Parte individual

## Trampas del ejemplo

- RIB-S01 y RIB-S03 están en UTC; RIB-S02 y RIB-S04, en GMT+1.
- La imagen del vídeo es auténtica: lo manipulado es el sonido. Que la imagen sea real no hace real el vídeo.
- RIB-P04 se llama casi igual que la directora, pero nada la relaciona con la empresa.
- dev-clientes.autobusesribera.example aparece en CT pero no responde: no prueba que el servicio exista hoy.
- La IP de los bonos falsos es una plataforma compartida: bloquearla no frena la campaña y afecta a otros.

## Bloque 1 · Tema 2

**1.1**

| Propuesta | Decisión | Motivo |
|---|---|---|
| P1 | Sí | Medida proporcionada por el canal previsto |
| P2 | No | Engaño mediante identidad falsa (N-19) |
| P3 | No | Datos personales sin base y sin verificar (N-02, N-21) |
| P4 | No | Acceso no autorizado con credenciales ajenas (N-13, N-18) |
| P5 | Sí | Conserva la evidencia y deja registro (criterio D.6) |

**1.2**

a) T1, TLP:CLEAR; T2, TLP:RED; T3, TLP:GREEN.

b) Respeto por las personas: expone a alguien por un rumor sin verificar y puede causarle daño.

## Bloque 2 · Tema 4

**2.1** a) Dentro. b) Fuera: es conectarse al equipo y podría ser acceso no autorizado (N-13). c) Dentro. d) Dentro. e) Fuera: interactúa con el adversario.

**2.2**

| Ficha | ¿De quién? | Justificación |
|---|---|---|
| SH-1 | Empresa | 192.0.2.100 está en el rango contratado |
| SH-2 | Venta falsa de bonos | Aloja ribera-bonobus.example en un alojamiento compartido |
| SH-3 | Empresa | 192.0.2.101 está en el rango contratado |

**2.3**

a) Ejemplo: «Shodan observó el 06/11/2026 una base de datos MySQL accesible desde Internet en 192.0.2.100».

b) El inventario dice que solo debe ser accesible desde el servidor web de la empresa.

c) Sistemas comprueba si sigue expuesta y la deja accesible solo desde el servidor web. No se intenta entrar.

**2.4**

a) Quien pidió el certificado controlaba los dos dominios: probablemente son de la misma campaña de bonos falsos.

b) Quién está detrás.

c) Preguntar a sistemas si el entorno se retiró y, si es así, quitarlo del inventario.

**2.5**

a) Ejemplos: `net:192.0.2.100/30` · `hostname:autobusesribera.example`

b) `domain:ribera-bonobus.example`

c) Porque es una plataforma compartida: el bloqueo afectaría a otras webs y la campaña puede cambiar de IP. Hay que actuar sobre los dominios y avisar a los viajeros.

## Bloque 3 · Tema 1

**3.1 a)** Problemas: no dice qué decisión apoya; el objeto es demasiado amplio («todo»); no tiene plazo; no dice qué producto espera ni para quién.

**3.1 b)**

| Componente | Respuesta |
|---|---|
| Destinatario | Consejero delegado y consejo de administración |
| Decisión | Qué controles de pago incluir en el presupuesto de 2027 |
| Objeto | Riesgo de fraude con deepfakes en los pagos de la empresa (proveedores) |
| Horizonte | Antes del consejo del 15/12/2026; mira a 2027 |
| Alcance | Incluye pagos y videollamadas; excluye la tecnología de los deepfakes en detalle |
| Producto | Informe breve con riesgos y controles recomendados |

## Bloque 4 · Tema 3

**4.1**

| Perfil | Relación | Evidencia |
|---|---|---|
| RIB-P01 | Oficial | Enlazada desde la web de la empresa |
| RIB-P02 | Cuenta anónima | Sin nombre real, creada en 10/2026 |
| RIB-P03 | Oficial | Enlazada desde la web de la empresa |
| RIB-P04 | No se puede saber | Nombre parecido, nada la relaciona |

**4.2**

a) RIB-S01 (22:10 del 07/11), RIB-S02 (23:00), RIB-S03 (10:00 del 08/11), RIB-S04 (11:30).

b) Original: RIB-S01. RIB-S02 depende de RIB-S01. RIB-S04 depende de RIB-S03 y del vídeo original, que compara.

c) La imagen sale de la rueda de prensa del 12/03/2025. No demuestra quién manipuló el sonido.

d) Es una fuente secundaria. Aporta una comprobación independiente: compara los dos vídeos.

**4.3**

| Fuente | Fiabilidad | Credibilidad |
|---|---|---|
| RIB-S01 | Baja (cuenta anónima) | Baja |
| RIB-S03 | Alta (cuenta oficial), pero es parte interesada | La niega |
| RIB-S04 | Media o alta (medio que comprueba) | La niega |

**4.4**

a) Ejemplos:

- `"Laura Ortega" "rueda de prensa" before:2025-03-31`: el vídeo original.
- `"ribera_filtraciones"`: otras copias o menciones del vídeo.

b) Elementos de la nota:

- **Valoración:** el vídeo está manipulado; la directora no dijo eso.
- **Confianza:** alta.
- **Evidencias:** RIB-I01 y RIB-S04.
- **Limitación:** no se sabe quién lo manipuló.
- **Recomendaciones:** publicar el comunicado T1 con el vídeo original y denunciar RIB-S01 a TikTok.

# Parte grupal

## Cronología en GMT+1

| Hora | Hecho |
|---|---|
| 23:00 (10/11) | Registro de abrazo-donaciones.example (F2-R2) |
| 23:15 (10/11) | Certificado de los dos dominios (F3-C1) |
| 09:00 | Publicación de @abrazo_ayuda (F1-S1) |
| 09:20 | Análisis de urlscan.io (F3-U1) |
| 09:30 | Primer donante sin certificado (F4-1) |
| 10:00 | La cuenta no es de la fundación (F4-2) |
| 10:30 | El cantante comparte la publicación (F1-S2) |
| 11:00 | 60 correos de donantes (F4-3) |
| 11:15 | Desmentido en la web oficial (F1-S3) |

Trampa: sin convertir las horas, parece que la fundación desmintió (10:15) antes de que el cantante compartiera la publicación (10:30). En realidad desmintió a las 11:15.

## Sección 1 · Tema 3

- **Valoración:** la web no es de la fundación. Confianza alta.
- **Evidencias:** F1-S3 (desmentido oficial), F4-2 (la cuenta no es de la fundación), F2-R2 (dominio creado dos días antes) y F1-S1 (cuenta creada el 10/11).
- **Republicaciones:** no. Miden difusión, no veracidad; además F1-S2 solo repite F1-S1.
- **Lo que no sabemos:** quién está detrás y cuánto dinero se ha desviado.

## Sección 2 · Tema 4

- **Dominios:** se registraron a la vez la noche del 10/11 y los controla quien pidió el certificado: son de la misma campaña. No dicen quién es.
- **IP:** no, porque la comparten 700 webs (F2-D2). Se pide la retirada de los dos dominios.
- **Lo que no puede afirmarse:** la autoría.
- **Lo más urgente:** publicar el aviso y pedir al banco y a la plataforma que actúen sobre la cuenta y los dominios. Lo hacen la dirección y la agencia de redes (F4-4).

## Sección 3 · Tema 2

| Propuesta | Decisión | Motivo |
|---|---|---|
| F5-A | Sí | Medida proporcionada por el canal previsto |
| F5-B | Sí | Contacto transparente, sin engaño, que ayuda a frenar la difusión |
| F5-C | Sí | Compartir con quien puede actuar (N-23) |
| F5-D | No | Interactúa con el adversario (criterio D.5) |
| F5-E | No | Minimización y respeto por las personas (N-02, N-21) |

- **TLP para F5-C:** TLP:GREEN.
- **Aviso:** «La Fundación Abrazo solo recoge donativos en fundacionabrazo.example. Si has donado en otra web, avisa a tu banco.» Se publica en la web oficial, en las redes de la fundación y se pide a quien difundió el bulo que lo comparta.
