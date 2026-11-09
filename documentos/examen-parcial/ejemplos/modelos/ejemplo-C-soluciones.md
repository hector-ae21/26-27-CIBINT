# Examen de práctica C · Soluciones orientativas

*CIBINT 2026-2027 · Intenta resolverlo antes de leer esto*

**C1.**

La frase 1 no tiene alcance ni decisión, y se centra en una persona («todo sobre el CEO»). Requerimiento corregido:

| Componente | Contenido |
|---|---|
| Destinatario | Dirección general |
| Decisión | Medidas de control de pagos y avisos internos |
| Objeto | El correo suplantado y su infraestructura |
| Horizonte | Hoy |
| Producto | Nota breve |

La frase 10 hace una atribución sin base: el caso FACC solo es **contexto** y comparte el patrón, no la autoría. Corrección: «El patrón coincide con el fraude de suplantación de directivos. No hay elementos para atribuirlo.»

**C2.**

- **Frase 3.** Trata datos personales de un tercero, sin relación demostrada y de su familia. Incumple la minimización (N-02) y puede suponer un seguimiento (N-17). Además, apunta a una persona y no a la amenaza. Alternativa: no recoger esos datos y borrar lo recogido.
- **Frase 5.** Es un engaño (N-22), suplanta a una persona real (N-18) y alerta al adversario. Alternativa: no interactuar y trasladar el teléfono a la denuncia.
- **Frase 9.** Rompe la necesidad de conocer y difunde por un canal informal un documento con datos sensibles. Lo correcto es **TLP:RED** o **AMBER+STRICT** para la dirección. Para compartir indicadores con el sector, se prepara una versión reducida con **TLP:GREEN**, y se notifica a INCIBE-CERT.

**C3.**

a) Hay una sola fuente de origen, el post de LinkedIn. La repetición no es confirmación. Además, la adquisición la afirma el atacante: puede ser un pretexto o haberla sacado de información pública. La fiabilidad se refiere a la fuente; la credibilidad, a la afirmación concreta.

b) Es un homónimo o un candidato **sin relación demostrada**. No debió investigarse.

c) El atacante aprovechó el nombre del CEO, información pública sobre operaciones, la estructura de la empresa y la presión de la confidencialidad. Medidas:

- doble autorización de los pagos;
- verificación por un canal conocido;
- formación de tesorería;
- vigilancia de dominios parecidos;
- aviso de que la dirección nunca pide transferencias por correo.

d) La nota debe recoger:

- **Valoración:** intento de fraude de suplantación del CEO desde un dominio que imita al legítimo, con confianza alta.
- **Evidencias:** el dominio no es el oficial, el pretexto de urgencia y confidencialidad, y la petición de pago fuera de procedimiento.
- **Limitaciones:** autoría desconocida.
- **Recomendaciones:** denunciar, bloquear el dominio, avisar a tesorería y solicitar la retirada del dominio.

**C4.**

- **Frase 2.** Que el titular esté oculto no indica nada. Lo relevante es la **fecha de creación**, que habría que consultar.
- **Frase 6.** Es una IP compartida: no se puede bloquear ni atribuir todo lo que hay en ella.
- **Frase 7.** El MX indica dónde se **reciben** correos para ese dominio. No prueba desde dónde se envió el mensaje: eso se ve en las cabeceras.
- **Frase 8.** El certificado de hoy es coherente con una preparación reciente. La entrada `vpn` de 2020 solo muestra que hubo un certificado: no prueba que el servicio esté expuesto ni que haya habido un ataque. Queda pendiente de revisar en el inventario.
- **Retirada.** Fuentes: el RDAP del dominio (registrador y contacto de abuso) y el del proveedor de alojamiento. Información: URL, fechas con zona horaria, el correo con sus cabeceras preservado con su huella y la marca suplantada.
