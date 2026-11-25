# Soluciones · Modelo E2 · Altamar Club de Fútbol

*Soluciones orientativas con la puntuación de cada apartado*

## Trampas del modelo

- Frase a frente a frase b del Caso 3: que alguien afirme algo es un hecho; lo que afirma, no necesariamente.
- Frase e: que la fuente sea una autoridad no hace creíble cualquier cosa que diga.
- La figura 2 está en UTC: las 6:00 p. m. son las 19:00 GMT+1.
- La insignia azul se obtiene con una suscripción de pago.
- altamar-cf.example es una peña legítima.
- El rango 198.51.100.0/24 es del proveedor y lo comparten otros clientes.
- 203.0.113.70 es la entrada de una CDN.

## Bloque 1 · Tema 2 (1,5)

**1.1 (1,0).**

| Propuesta | Decisión | Justificación y responsable |
|---|---|---|
| P1 | No | Exige criterios previos e informados y seguir un procedimiento (N-10). Responsables: RR. HH., asesoría jurídica y DPD. Además, el parte médico es un dato de salud (N-06) |
| P2 | No, tal como está planteada | Investigar a personas por cuenta de terceros está reservado a detectives (N-17). Alternativa: denuncia ante la autoridad |
| P3 | No | Engaño mediante identidad ficticia (N-19) |
| P4 | No | Suplantación de una persona real (N-16, N-15) |
| P5 | Con condiciones | La política ya está comunicada (N-10), interviene la DPD y es proporcionado. Valorar si es una violación de seguridad (N-08) |

**1.2 (0,5).**

a) Dos motivos:

- La investigación se centra en una persona, no en la amenaza.
- Se exige un nombre sin tiempo para verificarlo, con riesgo de señalar a un inocente (N-20, N-21).

b) Ejemplo: «Valorar antes del viernes qué información interna salió, por qué vías pudo hacerlo y qué medidas evitan nuevas filtraciones».

## Bloque 2 · Tema 4 (2,5)

**2.1 (0,6).**

| Dominio | Relación | Justificación |
|---|---|---|
| altamarcf-entradas | Relacionado | Creado dos días antes de ALT-S01 y enlazado desde esa publicación |
| altarmarcf | Pendiente o no relacionado | Dominio aparcado desde 2024 |
| altamar-cf | No relacionado | Peña de aficionados desde 2015 |

**2.2 (0,8).**

a) El CNAME de entradas.altamarcf.example sigue apuntando a un nombre del antiguo proveedor que ya no existe, y el contrato con ese proveedor terminó el 30/06/2026.

b) Hipótesis de riesgo: si un tercero pudiera dar de alta ese nombre en el servicio del antiguo proveedor, podría publicar contenido bajo un subdominio legítimo del club.

c) Debe actuar sistemas, eliminando o corrigiendo el registro DNS. El analista no debe intentar registrar el nombre ni hacer pruebas en el servicio del proveedor.

**2.3 (0,6).**

a) ALT-Q1 acepta que las dos condiciones se cumplan en servicios distintos del mismo host; ALT-Q2 exige que se cumplan en el mismo servicio.

b) Revisa todo el rango del proveedor, que comparten otros clientes: queda fuera del alcance.

c) Ejemplo: host.ip: "198.51.100.50".

**2.4 (0,5).**

a) No. La IP pertenece a una CDN con más de 9.000 nombres y la cabecera `Server: cloudflare` lo confirma: el servidor de origen queda oculto.

b) Fuente: el RDAP del dominio y de la IP, para identificar al registrador y a la CDN y sus contactos de abuso. Datos que se incluyen:

- la URL;
- las fechas, con su zona horaria;
- las capturas preservadas;
- el desmentido ALT-S04.

## Bloque 3 · Tema 1 (1,0)

**3.1 (1,0).**

| Frase | ¿Como hecho? | Explicación o reescritura |
|---|---|---|
| a | Sí | Consta que el ministro lo dijo |
| b | No | Afirmación contradicha por otras fuentes. Reescritura: «Según el ministro…» |
| c | Sí, atribuida | Debe citarse la fuente |
| d | Sí | Es lo que dice el informe |
| e | No | Confunde la fiabilidad de la fuente con la credibilidad de la afirmación |

## Bloque 4 · Tema 3 (3,5)

**4.1 (0,7).**

a) Elementos:

- **Cuenta:** ALT-C02.
- **Publicación:** ALT-S01.
- **Afirmaciones:** se han liberado 500 entradas; la venta es del club; el precio es de socio; la oferta es solo para hoy.

b) La insignia azul acredita una suscripción de pago, no la identidad ni la relación con el club, como en el caso de Eli Lilly. El historial de la cuenta muestra que se reutilizó.

**4.2 (0,9).**

a) El fotograma 2 se publicó el 18/05/2025. La fecha atribuida al hecho es el derbi de 2026 y la consulta se hizo el 12/11/2026. Por tanto, el material se reutilizó.

b) Indicios: el rival que aparece en el marcador no es el del derbi y la pancarta menciona la temporada 24/25.

c) Ninguna: la ausencia de coincidencias es una limitación, no una validación.

d) Ejemplo: «VID-01 reutiliza imágenes publicadas por ALT-C01 el 18/05/2025».

**4.3 (0,9).**

| Fuente | Fiabilidad | Credibilidad | Dependencia |
|---|---|---|---|
| ALT-S01 | Baja | Baja | Es el origen |
| ALT-S03 | Baja | Baja | Depende de ALT-S01 y ALT-S02 |
| ALT-S04 | Alta | Alta (para el desmentido) | Independiente |

**4.4 (1,0).**

a) Existe una sociedad irlandesa con ese nombre desde el 30/09/2026. No consta ninguna relación con el club, y la sociedad no acredita la autoría.

b) Ejemplos de consultas:

- `"Altamar Ticketing"`
- `"altamarcf-entradas.example" -site:altamarcf-entradas.example`

c) Elementos de la nota:

- **Valoración:** venta fraudulenta ajena al club.
- **Confianza:** alta.
- **Evidencias:** ALT-S04 (11/11, 10:00 GMT+1) y ALT-V01.
- **Limitación:** autoría desconocida.
- **Recomendación:** aviso oficial con el único canal de venta.
