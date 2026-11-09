# Examen de práctica A · Soluciones orientativas

*CIBINT 2026-2027 · Intenta resolverlo antes de leer esto*

**A1.**

| Componente | Respuesta |
|---|---|
| Destinatario | El pleno, a través de la alcaldesa |
| Decisión | Publicar un aviso oficial y reforzar la atención telefónica |
| Objeto | Los SMS que suplantan al Ayuntamiento |
| Horizonte | Antes de las 13:00 |
| Alcance | Mensajes reenviados, fuentes abiertas y obtención pasiva. **Excluido:** interactuar con la web falsa o identificar personas |
| Producto | Nota breve |

«Todo lo que haya» no delimita nada.

**A2.** Preguntas de inteligencia:

- ¿Hay alguna devolución real?
- ¿Desde cuándo circula el mensaje y a cuántos vecinos ha llegado?
- ¿Qué medidas reducen el daño hoy?

Consulta concreta: `"valdeloma-tasas.example"`. La pregunta de inteligencia dice qué hay que poder afirmar al final; la consulta es una búsqueda concreta en una fuente.

**A3.**

- Fuentes independientes: **ninguna**, porque S2 depende de S1, y S1 es solo una pregunta de un vecino.
- VAL-S3 es una fuente primaria oficial y contradice el mensaje.
- Rasgos del engaño (tres de estos): urgencia («HOY antes de las 23:59»), un dominio distinto del oficial, pedir la tarjeta para un abono y un remitente alfanumérico genérico.

**A4.** Ejemplos:

- `"valdeloma-tasas.example"`
- `site:valdeloma.example "devolución"`
- `"tasa de basuras" "devolución" SMS after:2026-10-15`

Límites: el buscador no indexa todo y no encontrar algo no prueba que no exista.

**A5.**

| Propuesta | Decisión |
|---|---|
| P1 | **No.** Interactúa con la infraestructura del adversario y lo alerta. Además, no es una obtención pasiva |
| P2 | **Sí** |
| P3 | **No.** Es desproporcionado: el aviso se hace público, sin tratar más datos (N-02) |
| P4 | **Sí** |
| P5 | **Sí** (N-26) |

**A6.**

- Aviso público: **TLP:CLEAR**.
- Red de municipios: **TLP:GREEN**.
- Nota interna con nombres: **TLP:RED** o **AMBER+STRICT**.
- A la periodista no se le dan detalles: se la deriva a comunicación por el canal oficial (posible ingeniería social).

**A7.**

- El certificado indica que quien lo solicitó controlaba los tres nombres: probablemente es una misma campaña contra varios municipios.
- La IP es compartida con 1.700 nombres, así que por sí sola no relaciona nada.
- A los otros dos municipios se les avisa, por ejemplo a través de la red provincial.
- Que el titular esté suprimido es lo normal y no indica malicia.

**A8.** Indica que en 2019 se pidió un certificado para ese nombre. No demuestra que el servicio exista hoy ni que esté expuesto. Debe comprobarlo Sistemas, revisando el inventario.

**A9.** La nota debe recoger:

- **Valoración:** campaña de suplantación ajena al Ayuntamiento, con confianza alta.
- **Evidencias:** S3, la fecha de creación del dominio y el certificado compartido con otros municipios.
- **Limitación:** no se conoce el número de afectados.
- **Recomendaciones:** aviso a los vecinos con el canal oficial; interna, revisar a los dos funcionarios que pincharon el enlace; externa, INCIBE-CERT y retirada del dominio.
- **Lado del atacante:** el atacante aprovechó el nombre del Ayuntamiento, un tributo real con su calendario y la costumbre de recibir avisos por SMS.
