# Soluciones · Modelo E4 · Pagora

*Soluciones orientativas con la puntuación de cada apartado*

## Trampas del modelo

- Las reacciones, las insignias y las republicaciones miden difusión, no veracidad.
- En el caso Arup, la videollamada procedía del mismo origen que el correo, así que no era una verificación independiente.
- El TTL no indica antigüedad, y «primera vez visto» no es la fecha de creación.
- Los dos índices tienen fechas y cobertura distintas: que uno no muestre el 8080 no prueba que esté cerrado.
- Que un nombre contenga «admin» o «test» no basta para darle prioridad alta.
- Las horas en Z deben convertirse a GMT+1.

## Bloque 1 · Tema 1 (1,0)

**1.1.**

| Elemento | Nivel | Por qué |
|---|---|---|
| E1 | Técnico | Indicadores concretos |
| E2 | Táctico | Forma de actuar |
| E3 | Estratégico | Tendencia e impacto |
| E4 | Operacional | Campaña y objetivo |
| E5 | Técnico | Regla de detección |

## Bloque 2 · Tema 3 (3,5)

**2.1 (0,8).**

| Perfil | Relación | Evidencia |
|---|---|---|
| PAG-P01 | Confirmada | Enlazada desde PAG-F01 |
| PAG-P02 | Confirmada | Figura en PAG-F01 |
| PAG-P03 | Suplantación probable | Usa la fotografía de PAG-P02 |
| PAG-P04 | No determinable | Solo es lo que declara la propia cuenta |

**2.2 (0,9).**

a) Orden en GMT+1:

1. PAG-S01: 03/11, 10:00.
2. PAG-S02: 04/11, 12:00.
3. PAG-S04: 05/11, 08:30.

b) PAG-S02 depende de PAG-S01.

c) Hay una sola fuente de origen y PAG-S04 y PAG-F01 la contradicen. La difusión no es una confirmación.

d) La imagen está reutilizada desde un coworking de Lisboa: no es una oficina de Pagora.

**2.3 (0,9).**

a) Existe una LLP británica desde el 01/10/2026, con domicilio en una empresa de domiciliación y fuera del grupo, según PAG-R03. Su existencia no demuestra autoría ni relación con Pagora.

b)

| Fuente | Fiabilidad de la fuente | Credibilidad de la afirmación |
|---|---|---|
| PAG-S01 | Baja | Baja |
| PAG-F01 | Alta | La niega |
| PAG-R02 | Alta sobre la existencia de la LLP | No aporta nada sobre la relación |

**2.4 (0,9).**

a) Un segundo canal controlado por el mismo origen no es una verificación independiente. La verificación válida se hace por un canal propio y ya conocido.

b) Elementos de la nota:

- **Valoración:** suplantación ajena a Pagora.
- **Confianza:** alta.
- **Evidencias:** PAG-F01 y PAG-S04.
- **Limitación:** autoría desconocida.
- **Recomendación:** aviso a los candidatos y un canal para verificar ofertas.

## Bloque 3 · Tema 2 (1,5)

**3.1 a) (0,5).** Problemas que pueden señalarse:

- B-01: usa una cuenta personal (OPSEC).
- Ninguna entrada indica la zona horaria.
- B-02: le faltan el propósito y la decisión.
- B-03: se reconstruyó después de los hechos.
- B-04: copia datos personales (N-02); además, debería detenerse la obtención y consultar.
- B-05: no consta la URL ni la huella, y la ubicación no está restringida.
- La decisión negativa (no escribir al contacto) no está registrada.

**3.1 b) (0,5).**

| Campo | Contenido |
|---|---|
| Fecha y hora | 11/11/2026 10:40 GMT+1 |
| Propósito | Comprobar la difusión de la oferta |
| Fuente | Canal público, consultado sin sesión |
| Acción y resultado | Se observa un listado con datos identificativos. No se copia |
| Decisión siguiente | Detener la obtención y consultar con la DPD |

**3.2 (0,5).**

a) Prácticas de preservación:

- registrar la URL, la fecha y la zona horaria;
- calcular la huella SHA-256;
- conservar el original y trabajar sobre copias;
- registrar los accesos;
- guardar en un lugar con acceso restringido.

b) La bitácora no ofrece garantías forenses. Si se prevé un procedimiento judicial, hay que contar con la asesoría jurídica y con un perito.

## Bloque 4 · Tema 4 (2,5)

**4.1 (0,6).**

a) admin-test, status y el dominio externo pagora-talent.example.

b) Que un nombre aparezca en CT no prueba que el servicio esté activo. admin-test queda pendiente. status corresponde a un proveedor externo.

c) Hecho: el certificado se emitió el 02/10. Inferencia: el dominio se preparó para la campaña al mismo tiempo que se creó la LLP.

**4.2 (0,6).**

a) El inventario solo recoge la IPv4 de portal, así que es posible que los controles no cubran la IPv6.

b) No puede saberse: ni el TTL ni la «primera vez visto» indican desde cuándo está activo.

c) Ejemplos: `ip:198.51.100.33` y `hostname:sandbox.pagora.example`.

**4.3 (1,3).**

a) No se contradicen: sus fechas y su cobertura son distintas.

b) Ejemplo: «El índice A observó el 02/04/2026 un servicio HTTP en 8080/TCP titulado "Panel de pruebas"».

c) No puede concluirse ni la versión real ni la existencia de una vulnerabilidad.

d)

| Hallazgo | Prioridad |
|---|---|
| H1 | Alta para validación |
| H2 | Pendiente |
| H3 | Alta o media para validación |
| H4 | Acción defensiva externa |

e) Va primero H1, porque contradice el inventario («solo 443/TCP»). También se acepta H4, si se justifica.
