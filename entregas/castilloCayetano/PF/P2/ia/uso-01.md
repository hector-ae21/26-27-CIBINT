# Exportación de uso de IA · Uso 01 (P2)

- **Fecha y hora:** 27/11/2026 21:09 (`Europe/Madrid`)
- **Herramienta y modelo:** Gemini Pro 3.1
- **Hito:** P2 (`v0.3`) · Configuración OPSEC en Opera GX, registros CSV y cálculo de hashes

## Prompt

Estoy preparando el Avance 2 (P2) de mi proyecto final de ciberinteligencia sobre las vulnerabilidades PHP2Shell (CVE-2026-109618, CVE-2026-109619 y CVE-2026-115560). Voy a consultar de forma estrictamente pasiva las fuentes abiertas (PHP Group, avisos GHSA, CISA/KEV, NVD, Snyk, Sygnia y Wiz Research) usando Opera GX y guardando copias locales en PDF dentro de `P2/recursos/`.

Necesito ayuda con tres aspectos metodológicos y técnicos:
1. Qué ajustes concretos de OPSEC debo verificar en Opera GX (ventana privada, VPN, bypass de buscadores y DoH) y qué datos clave conviene comprobar en cada fuente para responder a PI-01 (origen y evidencias sobre el uso de IA), PI-02 (explotación activa) y PI-03 (mitigaciones y límites) sin acceder nunca a repositorios de código PoC.
2. Cómo estructurar los registros nuevos respetando exactamente estos encabezados del repositorio:
   - `hallazgos.csv`: `hallazgo_id,pregunta_id,afirmacion_observada,fuentes_id,fecha_hecho_o_dato,interpretacion,explicacion_alternativa,confianza_justificada,limitacion,recomendacion_id`
   - `integridad.csv`: `archivo,evidencia_id,fecha_obtencion_zona_horaria,sha256,md5,ubicacion,observacion`
3. Un comando de PowerShell para calcular en local los hashes SHA-256 y MD5 de los 7 PDFs guardados en `entregas/castilloCayetano/PF/P2/recursos/` y generar automáticamente `P2/registros/integridad.csv`.

## Respuesta completa

### 1. Ajustes de OPSEC en Opera GX y verificación por fuente

#### Configuración previa en Opera GX
Antes de abrir los enlaces, verifica estos cinco ajustes para mantener la recolección estrictamente pasiva:
- **Ventana privada sin sesión (`Ctrl + Shift + N`):** Navega sin iniciar sesión en Opera Sync, GitHub, Google ni en el correo universitario para separar identidades.
- **DNS sobre HTTPS (DoH):** En *Configuración > Privacidad y seguridad*, activa **Usar DNS sobre HTTPS** (selecciona Cloudflare o Quad9) para evitar fugas DNS hacia tu proveedor local.
- **Bloqueo de rastreadores y VPN:** Activa **Bloquear rastreadores** y enciende la VPN (si usas la VPN integrada de Opera GX, anota en `bitacora.csv` que opera como proxy de navegador; si GitHub devuelve error `504 Gateway Time-out` en los avisos GHSA, cambia la ubicación o consulta esos avisos oficiales en ventana privada + DoH y documenta la incidencia en la bitácora).
- **Desactivar el bypass de buscadores:** Dentro de los ajustes de VPN, desactiva **«Habilitar los motores de búsqueda predeterminados evitando la VPN»** para que ninguna consulta salga fuera del túnel.
- **Exclusión de PoC y condición de parada:** No abras, descargues ni ejecutes repositorios con código de explotación (PoC); recoge cualquier mención a su existencia únicamente a través de los informes secundarios. Si aparece un *Zero-Day*, infraestructura C2 activa, datos confidenciales de víctimas o exigencia de interacción, cierra la pestaña **sin guardar PDF ni capturar pantalla**, anota solo la categoría en `bitacora.csv` y consulta al profesorado.

#### Datos clave a comprobar en cada fuente
En cada página, apunta la hora exacta (`Europe/Madrid`), guarda la copia estática con **`Ctrl + P` → Guardar como PDF** en `P2/recursos/` y verifica estos puntos (anota también los silencios relevantes, como cuándo una fuente **no** menciona IA):

| Fuente | Preguntas | Datos clave a verificar (`Ctrl + F` y secciones) |
|---|---|---|
| **PHP Group** (`php.net` y 3 avisos GHSA) | PI-01, PI-03 | Fechas exactas de parcheo, versiones corregidas, puntuación CVSS/CWE, sección **Credits / Reported by** (quién descubrió cada fallo y si figura alguna referencia a IA), **Workarounds** oficiales y la condición técnica exacta que exige CVE-2026-115560. |
| **CISA** (Alerta y Catálogo KEV) | PI-02, PI-03 | Fecha de inclusión en KEV y plazo límite (*Due Date*) de CVE-2026-109618 y CVE-2026-109619, confirmar si CVE-2026-115560 figura o **no** en KEV, confirmación de explotación activa y ausencia de atribución o menciones a IA. |
| **NIST / NVD** | PI-01, PI-02, PI-03 | Fechas oficiales de publicación y modificación de los 3 CVEs, vectores CVSS, clasificación CWE y enlaces en la tabla **References** para contrastar dependencias. |
| **Snyk** | PI-01, PI-03 | Buscar `AI`, `LLM`, `bypass`, `115560`, `mitigation`, `workaround` y `PoC`. Comprobar si afirma algo sobre IA (o si no la menciona), cómo encuadra CVE-2026-115560, qué mitigaciones temporales recoge y si cita fuentes externas. |
| **Sygnia** | PI-01, PI-02, PI-03 | Buscar `AI`, `exploit`, `wild`, `IOC`, `detection`, `WAF` y `PHP_SESSION_UPLOAD_PROGRESS`. Verificar a quién cita respecto a la IA, qué tráfico de ataque u observaciones reporta, qué reglas WAF propone y sus límites (ofuscando cualquier indicador potencialmente malicioso como `hxxps://`). |
| **Wiz Research** | PI-01, PI-02 | Fecha de publicación, autores y cronología de divulgación. Comprobar qué modelos o herramientas de IA declara, qué evidencia aporta (narrativa autodeclarada frente a trazas reproducibles) y si su reporte cubre solo los CVEs iniciales o también CVE-2026-115560. |

---

### 2. Estructura de `hallazgos.csv` e `integridad.csv`

#### `P2/registros/hallazgos.csv`
Debe separar estrictamente la observación verificable de su interpretación y vincular cada fila a una pregunta de inteligencia (`PI-01` a `PI-03`) y a sus fuentes (`F-01` a `F-06`):
- `hallazgo_id`: identificador correlativo (`H-01`, `H-02`...).
- `pregunta_id`: pregunta a la que responde (`PI-01`, `PI-02` o `PI-03`).
- `afirmacion_observada`: hecho o declaración atribuida a su emisor, sin adelantar conclusiones.
- `fuentes_id`: códigos de las fuentes que lo respaldan o contrastan (p. ej., `F-01; F-06`).
- `fecha_hecho_o_dato`: fecha real del hecho o publicación (`YYYY-MM-DD`).
- `interpretacion`: significado analítico para la pregunta de inteligencia.
- `explicacion_alternativa`: hipótesis rival plausible o explicación alternativa del mismo dato.
- `confianza_justificada`: nivel (`Alta`, `Media` o `Baja`) seguido de una justificación breve basada en la independencia y suficiencia del apoyo.
- `limitacion`: qué **no** demuestra ese hallazgo y qué dato falta para cerrarlo.
- `recomendacion_id`: identificador de recomendación (`R-01`...) o `Pendiente P3` si las recomendaciones finales se cierran en el tercer avance.

**Ejemplo de cabecera y fila:**

```csv
hallazgo_id,pregunta_id,afirmacion_observada,fuentes_id,fecha_hecho_o_dato,interpretacion,explicacion_alternativa,confianza_justificada,limitacion,recomendacion_id
H-01,PI-01,"Wiz Research declara haber descubierto los fallos iniciales usando herramientas de IA y Sygnia cita ese reporte; PHP Group acredita a los investigadores pero no audita el uso de IA.","F-01; F-05; F-06",2026-10-21,"La afirmación sobre IA tiene un único origen trazable (F-06) y no cuenta con corroboración independiente en fuentes primarias.","Asistencia parcial de IA amplificada con fines comerciales durante una investigación liderada por humanos.","Media: autoría confirmada en F-01, pero el peso real de la IA es autodeclarado en F-06 sin trazas reproducibles.","No demuestra que la IA operara de forma autónoma ni cubre CVE-2026-115560.",Pendiente P3
```

#### `P2/registros/integridad.csv`
Registra la cadena de custodia de cada copia local conservada en `P2/recursos/`. `sha256` actúa como huella principal y `md5` como comprobación complementaria calculada sobre exactamente el mismo archivo:
- `archivo`: nombre exacto del PDF guardado.
- `evidencia_id`: identificador correlativo (`EV-01` a `EV-07`), que luego enlazarás en `fuentes.csv`.
- `fecha_obtencion_zona_horaria`: fecha y hora de obtención con zona (`YYYY-MM-DD HH:MM Europe/Madrid`).
- `sha256`: hash SHA-256 en minúsculas (64 caracteres hexadecimales).
- `md5`: hash MD5 en minúsculas (32 caracteres hexadecimales).
- `ubicacion`: ruta relativa dentro del proyecto (`P2/recursos/<archivo>`).
- `observacion`: descripción breve de qué fuente corresponde a esa copia local.

---

### 3. Comando de PowerShell para calcular hashes y generar `integridad.csv`

Ejecuta este bloque en PowerShell desde la **raíz del repositorio**. Lee automáticamente los 7 PDFs de `entregas/castilloCayetano/PF/P2/recursos/`, calcula sus hashes SHA-256 y MD5 en minúsculas, toma la fecha de guardado con zona `Europe/Madrid` y genera `entregas/castilloCayetano/PF/P2/registros/integridad.csv` respetando exactamente tus 7 encabezados:

```powershell
$recursos = "entregas/castilloCayetano/PF/P2/recursos/"
$salida   = "entregas/castilloCayetano/PF/P2/registros/integridad.csv"

$obs = @{
  "F-01_php_announcement.pdf" = "Copia local en PDF del aviso oficial de PHP Group (F-01)"
  "F-02_cisa_alert.pdf"       = "Copia local en PDF de la alerta oficial de CISA (F-02)"
  "F-02_cisa_kev.pdf"         = "Copia local en PDF del catalogo KEV de CISA para CVE-2026-109618 y CVE-2026-109619 (F-02)"
  "F-03_nvd_cves.pdf"         = "Copia local en PDF de las fichas oficiales en NVD (F-03)"
  "F-04_snyk_php2shell.pdf"   = "Copia local en PDF del analisis tecnico de Snyk (F-04)"
  "F-05_sygnia_php2shell.pdf" = "Copia local en PDF del informe de amenazas de Sygnia (F-05)"
  "F-06_wiz_reasearch.pdf"    = "Copia local en PDF del informe original de Wiz Research (F-06)"
}

$lines = @("archivo,evidencia_id,fecha_obtencion_zona_horaria,sha256,md5,ubicacion,observacion")
$i = 1

Get-ChildItem $recursos -File | Sort-Object Name | ForEach-Object {
  $id    = "EV-{0:D2}" -f $i++
  $fecha = $_.LastWriteTime.ToString("yyyy-MM-dd HH:mm") + " Europe/Madrid"
  $sha   = (Get-FileHash $_.FullName -Algorithm SHA256).Hash.ToLower()
  $md5   = (Get-FileHash $_.FullName -Algorithm MD5).Hash.ToLower()
  $nota  = if ($obs.ContainsKey($_.Name)) { $obs[$_.Name] } else { "Copia local en PDF de evidencia documental ($id)" }
  $lines += "$($_.Name),$id,$fecha,$sha,$md5,P2/recursos/$($_.Name),`"$nota`""
}

$lines | Set-Content $salida -Encoding UTF8
Get-Content $salida
```

Al terminar, la última línea (`Get-Content $salida`) mostrará en pantalla la cabecera y las 7 filas generadas (`EV-01` a `EV-07`) para que verifiques que no haya campos vacíos y que los nombres de archivo coincidan exactamente con los de tu carpeta `P2/recursos/`.