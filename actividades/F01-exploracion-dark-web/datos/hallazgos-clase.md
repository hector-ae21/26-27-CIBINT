# Hallazgos de clase · Material controlado para F01

> **Nota importante.** Los tres casos de este archivo son **ficticios y están preparados para docencia**. Reproducen de forma fiel cómo se presentan anuncios y páginas delictivas habituales en la dark web, pero las organizaciones, direcciones `.onion`, correos y referencias están inventados y no conducen a ningún sitio real. **No busques ni intentes abrir direcciones externas relacionadas.**

---

## Caso A · Mercado clandestino de logs y accesos corporativos

**Contexto del hallazgo:** durante una búsqueda de referencias sobre exposición de credenciales, una nota de un canal remite a un mercado clandestino accesible por Tor (`mercado-ficticio-logs-2026.example.onion`). En portada aparece esta oferta sin necesidad de comprar todavía:

```text
[NUEVO LOTE · NOVIEMBRE 2026] — Logs frescos de infostealer (Europa / España)
Vendedor: k0r_access (reputación: 94 % · 38 ventas verificadas · Escrow obligatorio)

Incluye:
- 420 perfiles completos de navegador (contraseñas guardadas + cookies activas + huella de equipo)
- 14 accesos a portales VPN y paneles de administración de empresas del sector logístico
- Fecha de extracción declarada: última semana

Precio: 0,85 XMR (Monero) por lote completo · sin reembolsos tras la entrega
Contacto: solo mensajería interna del mercado o Jabber cifrado

>>> MUESTRA GRATUITA (5 registros para verificar calidad): descargar muestra_eu_nov26.zip (2,4 MB) <<<
```

**Observaciones adicionales en la página:**
- El sitio pide desactivar el bloqueo de JavaScript para cargar el botón de registro y el sistema de *captcha*.
- Dos comentarios bajo el anuncio dicen que el lote contiene carpetas que ya circularon en junio en otro foro.

---

## Caso B · Sitio de extorsión de ransomware (*Data Leak Site*)

**Contexto del hallazgo:** al revisar alertas sobre un grupo de ransomware ficticio llamado **ValkyrieLock**, aparece esta ficha pública en su blog de extorsión (`valkyrielock-leak-ficticio.example.onion`):

```text
OBJETIVO: Clínica Costa Norte S.L. (clinica-costa-norte.example)
SECTOR: Sanitario · España
VOLUMEN ANUNCIADO: 185 GB de documentación interna

ESTADO: CUENTA ATRÁS ACTIVA — 41 horas 18 minutos para publicación total

"La dirección ha ignorado nuestras comunicaciones. Si no se cierra acuerdo antes del contador,
se publicará el archivo completo con historiales de pacientes, nóminas, DNI escaneados,
contratos con proveedores y copias de correo directivo."

PRUEBAS DISPONIBLES AHORA:
- [captura_directorio_pacientes.png] (muestra nombres completos y códigos clínicos)
- [muestra_contratos_2025.pdf] (descarga directa)
- [ENLACE TORRENT COMPLETO — disponible al finalizar el contador]
```

**Observaciones adicionales:**
- La entidad afectada todavía no ha publicado ningún comunicado oficial en su web.
- El texto incluye un correo de negociación para que la empresa contacte con el grupo.

---

## Caso C · Directorio anónimo con desvío a contenido delictivo grave

**Contexto del hallazgo:** al comprobar un directorio anónimo tipo «wiki» encontrado desde una lista sin verificar (`directorio-oculto-ficticio.example.onion`), la página mezcla en la misma portada enlaces a servicios conocidos con bloques claramente ilícitos:

```text
=== ÍNDICE DE ENLACES ONION VERIFICADOS (ACTUALIZADO 2026) ===

[Buscadores y correo]
- DuckDuckGo (enlace con dos caracteres cambiados respecto al oficial)
- Proton Mail

[Servicios financieros y documentos]
- Tarjetas clonadas con PIN y envío exprés (pago en BTC)
- Pasaportes y permisos de conducir europeos falsificados
- Cuentas bancarias robadas con saldo verificado

[Comunidades privadas y archivos sin censura]
- Enlaces marcados como "acceso restringido / material ilegal sin moderación"
- Foros de intercambio de bases de datos robadas de menores y ciudadanos
```

**Observaciones adicionales:**
- Varios enlaces de la sección «Buscadores y correo» redirigen a copias distintas a las oficiales (posible *phishing*).
- Al pasar el ratón por las secciones inferiores aparecen descripciones explícitas de actividades delictivas graves.
