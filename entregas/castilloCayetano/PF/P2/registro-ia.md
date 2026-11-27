# Registro de uso de inteligencia artificial · Proyecto final

**Estudiante: Cayetano Castillo Ruiz**  
**Título del proyecto: Análisis de las vulnerabilidades PHP2Shell: ciclo de vida, evasión de parches y revisión de las evidencias sobre la implicación de la IA.**  
**Hito y fecha: P2 27/11/2026**

## Declaración

- [Con uso de IA: «He utilizado inteligencia artificial únicamente para las tareas permitidas, según los usos y evidencias que se detallan a continuación».]

## Uso 01

- **Quién:** Cayetano Castillo
- **Fecha:** 27/11/2026
- **Herramienta y modelo, si consta:** Gemini Pro 3.1
- **Para qué:** Estructurar el flujo de recolección pasiva de P2 (configuración OPSEC en Opera GX y puntos de comprobación por fuente), adaptar los registros CSV (`fuentes.csv`, `bitacora.csv`, `hallazgos.csv` e `integridad.csv`) a los encabezados oficiales y generar el script local de PowerShell para calcular huellas SHA-256 y MD5.
- **Hito y apartado del trabajo:** P2 (`v0.3`) · Apartado 5 (Fuentes y método), Apartado 6 (Resultados y evidencias) y carpeta `P2/registros/`
- **Fuentes o texto propio utilizados como entrada:** Encabezados oficiales de `hallazgos.csv` e `integridad.csv` del repositorio y notas extraídas manualmente de las fuentes `F-01` (PHP Group y tres avisos `GHSA`), `F-02` (CISA), `F-03` (NVD), `F-04` (Snyk), `F-05` (Sygnia) y `F-06` (Wiz Research).
- **Prompt, copiado tal cual:**

Estoy preparando el Avance 2 (P2) de mi proyecto final de ciberinteligencia sobre las vulnerabilidades PHP2Shell (CVE-2026-109618, CVE-2026-109619 y CVE-2026-115560). Voy a consultar de forma estrictamente pasiva las fuentes abiertas (PHP Group, avisos GHSA, CISA/KEV, NVD, Snyk, Sygnia y Wiz Research) usando Opera GX y guardando copias locales en PDF dentro de `P2/recursos/`.

Necesito ayuda con tres aspectos metodológicos y técnicos:
1. Qué ajustes concretos de OPSEC debo verificar en Opera GX (ventana privada, VPN, bypass de buscadores y DoH) y qué datos clave conviene comprobar en cada fuente para responder a PI-01 (origen y evidencias sobre el uso de IA), PI-02 (explotación activa) y PI-03 (mitigaciones y límites) sin acceder nunca a repositorios de código PoC.
2. Cómo estructurar los registros nuevos respetando exactamente estos encabezados del repositorio:
   - `hallazgos.csv`: `hallazgo_id,pregunta_id,afirmacion_observada,fuentes_id,fecha_hecho_o_dato,interpretacion,explicacion_alternativa,confianza_justificada,limitacion,recomendacion_id`
   - `integridad.csv`: `archivo,evidencia_id,fecha_obtencion_zona_horaria,sha256,md5,ubicacion,observacion`
3. Un comando de PowerShell para calcular en local los hashes SHA-256 y MD5 de los 7 PDFs guardados en `entregas/castilloCayetano/PF/P2/recursos/` y generar automáticamente `P2/registros/integridad.csv`.

- **Respuesta completa:**

1. Ajustes de OPSEC en Opera GX y verificación por fuenteConfiguración previa en Opera GXAntes de abrir los enlaces, verifica estos cinco ajustes para mantener la recolección estrictamente pasiva:Ventana privada sin sesión (Ctrl + Shift + N): Navega sin iniciar sesión en Opera Sync, GitHub, Google ni en el correo universitario para separar identidades.DNS sobre HTTPS (DoH): En Configuración > Privacidad y seguridad, activa Usar DNS sobre HTTPS (selecciona Cloudflare o Quad9) para evitar fugas DNS hacia tu proveedor local.Bloqueo de rastreadores y VPN: Activa Bloquear rastreadores y enciende la VPN (si usas la VPN integrada de Opera GX, anota en bitacora.csv que opera como proxy de navegador; si GitHub devuelve error 504 Gateway Time-out en los avisos GHSA, cambia la ubicación o consulta esos avisos oficiales en ventana privada + DoH y documenta la incidencia en la bitácora).Desactivar el bypass de buscadores: Dentro de los ajustes de VPN, desactiva «Habilitar los motores de búsqueda predeterminados evitando la VPN» para que ninguna consulta salga fuera del túnel.Exclusión de PoC y condición de parada: No abras, descargues ni ejecutes repositorios con código de explotación (PoC); recoge cualquier mención a su existencia únicamente a través de los informes secundarios. Si aparece un Zero-Day, infraestructura C2 activa, datos confidenciales de víctimas o exigencia de interacción, cierra la pestaña sin guardar PDF ni capturar pantalla, anota solo la categoría en bitacora.csv y consulta al profesorado.Datos clave a comprobar en cada fuenteEn cada página, apunta la hora exacta (Europe/Madrid), guarda la copia estática con Ctrl + P → Guardar como PDF en P2/recursos/ y verifica estos puntos (anota también los silencios relevantes, como cuándo una fuente no menciona IA):FuentePreguntasDatos clave a verificar (Ctrl + F y secciones)PHP Group (php.net y 3 avisos GHSA)PI-01, PI-03Fechas exactas de parcheo, versiones corregidas, puntuación CVSS/CWE, sección Credits / Reported by (quién descubrió cada fallo y si figura alguna referencia a IA), Workarounds oficiales y la condición técnica exacta que exige CVE-2026-115560.CISA (Alerta y Catálogo KEV)PI-02, PI-03Fecha de inclusión en KEV y plazo límite (Due Date) de CVE-2026-109618 y CVE-2026-109619, confirmar si CVE-2026-115560 figura o no en KEV, confirmación de explotación activa y ausencia de atribución o menciones a IA.NIST / NVDPI-01, PI-02, PI-03Fechas oficiales de publicación y modificación de los 3 CVEs, vectores CVSS, clasificación CWE y enlaces en la tabla References para contrastar dependencias.SnykPI-01, PI-03Buscar AI, LLM, bypass, 115560, mitigation, workaround y PoC. Comprobar si afirma algo sobre IA (o si no la menciona), cómo encuadra CVE-2026-115560, qué mitigaciones temporales recoge y si cita fuentes externas.SygniaPI-01, PI-02, PI-03Buscar AI, exploit, wild, IOC, detection, WAF y PHP_SESSION_UPLOAD_PROGRESS. Verificar a quién cita respecto a la IA, qué tráfico de ataque u observaciones reporta, qué reglas WAF propone y sus límites (ofuscando cualquier indicador potencialmente malicioso como hxxps://).Wiz ResearchPI-01, PI-02Fecha de publicación, autores y cronología de divulgación. Comprobar qué modelos o herramientas de IA declara, qué evidencia aporta (narrativa autodeclarada frente a trazas reproducibles) y si su reporte cubre solo los CVEs iniciales o también CVE-2026-115560.2. Estructura de hallazgos.csv e integridad.csvP2/registros/hallazgos.csvDebe separar estrictamente la observación verificable de su interpretación y vincular cada fila a una pregunta de inteligencia (PI-01 a PI-03) y a sus fuentes (F-01 a F-06):hallazgo_id: identificador correlativo (H-01, H-02...).pregunta_id: pregunta a la que responde (PI-01, PI-02 o PI-03).afirmacion_observada: hecho o declaración atribuida a su emisor, sin adelantar conclusiones.fuentes_id: códigos de las fuentes que lo respaldan o contrastan (p. ej., F-01; F-06).fecha_hecho_o_dato: fecha real del hecho o publicación (YYYY-MM-DD).interpretacion: significado analítico para la pregunta de inteligencia.explicacion_alternativa: hipótesis rival plausible o explicación alternativa del mismo dato.confianza_justificada: nivel (Alta, Media o Baja) seguido de una justificación breve basada en la independencia y suficiencia del apoyo.limitacion: qué no demuestra ese hallazgo y qué dato falta para cerrarlo.recomendacion_id: identificador de recomendación (R-01...) o Pendiente P3 si las recomendaciones finales se cierran en el tercer avance.Ejemplo de cabecera y fila:Fragmento de códigohallazgo_id,pregunta_id,afirmacion_observada,fuentes_id,fecha_hecho_o_dato,interpretacion,explicacion_alternativa,confianza_justificada,limitacion,recomendacion_id
H-01,PI-01,"Wiz Research declara haber descubierto los fallos iniciales usando herramientas de IA y Sygnia cita ese reporte; PHP Group acredita a los investigadores pero no audita el uso de IA.","F-01; F-05; F-06",2026-10-21,"La afirmación sobre IA tiene un único origen trazable (F-06) y no cuenta con corroboración independiente en fuentes primarias.","Asistencia parcial de IA amplificada con fines comerciales durante una investigación liderada por humanos.","Media: autoría confirmada en F-01, pero el peso real de la IA es autodeclarado en F-06 sin trazas reproducibles.","No demuestra que la IA operara de forma autónoma ni cubre CVE-2026-115560.",Pendiente P3
P2/registros/integridad.csvRegistra la cadena de custodia de cada copia local conservada en P2/recursos/. sha256 actúa como huella principal y md5 como comprobación complementaria calculada sobre exactamente el mismo archivo:archivo: nombre exacto del PDF guardado.evidencia_id: identificador correlativo (EV-01 a EV-07), que luego enlazarás en fuentes.csv.fecha_obtencion_zona_horaria: fecha y hora de obtención con zona (YYYY-MM-DD HH:MM Europe/Madrid).sha256: hash SHA-256 en minúsculas (64 caracteres hexadecimales).md5: hash MD5 en minúsculas (32 caracteres hexadecimales).ubicacion: ruta relativa dentro del proyecto (P2/recursos/<archivo>).observacion: descripción breve de qué fuente corresponde a esa copia local.3. Comando de PowerShell para calcular hashes y generar integridad.csvEjecuta este bloque en PowerShell desde la raíz del repositorio. Lee automáticamente los 7 PDFs de entregas/castilloCayetano/PF/P2/recursos/, calcula sus hashes SHA-256 y MD5 en minúsculas, toma la fecha de guardado con zona Europe/Madrid y genera entregas/castilloCayetano/PF/P2/registros/integridad.csv respetando exactamente tus 7 encabezados:PowerShell$recursos = "entregas/castilloCayetano/PF/P2/recursos/"
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
Al terminar, la última línea (Get-Content $salida) mostrará en pantalla la cabecera y las 7 filas generadas (EV-01 a EV-07) para que verifiques que no haya campos vacíos y que los nombres de archivo coincidan exactamente con los de tu carpeta P2/recursos/.

- **Qué hice con la respuesta:** Utilicé las pautas de configuración en Opera GX para realizar las consultas pasivas, adapté la estructura de los cuatro CSV a los encabezados exactos del curso, ejecuté localmente el script de PowerShell sobre mis PDFs en `P2/recursos/` y corregí manualmente detalles locales como el nombre exacto de `F-06_wiz_reasearch.pdf` y erratas menores de espaciado en `integridad.csv`.
- **Qué comprobé y con qué fuentes originales u oficiales:** Comprobé directamente en navegador (Opera GX en ventana privada, VPN con bypass de buscadores desactivado y DoH) todas las fechas, puntuaciones CVSS 4.0 (`9.2`), códigos CWE, créditos oficiales de descubridores y mitigaciones en `F-01` (`php.net` y los avisos `GHSA-w8hw-w9fx-j79w`, `GHSA-6wmf-4rv5-p3rp` y `GHSA-658j-r8rw-q6mx`), `F-02` (alerta y catálogo KEV de CISA), `F-03` (NVD), `F-04` (Snyk), `F-05` (Sygnia) y `F-06` (Wiz Research), guardando copias locales en PDF (`EV-01` a `EV-07`) y verificando sus huellas SHA-256 y MD5 reales en local.
- **Evidencia:** [Exportación local `P2/ia/uso-01.md`](./ia/uso-01.md) (https://share.gemini.google/Eo8wfbrg45Dw)
- **Usos relacionados:** Uso 03 y Uso 04 (P1)

## Uso 02

- **Quién:** Cayetano Castillo
- **Fecha:** 27/11/2026
- **Herramienta y modelo, si consta:** Gemini Pro 3.1
- **Para qué:** Estructurar la ampliación de `P2/informe.md` (`v0.3`) respetando la plantilla original de P1 —en particular la cronología de cuatro fechas, el contraste de dependencias, las explicaciones alternativas (`E-01` y `E-02`) sobre `PI-01`, la revisión de sesgos/contradicciones y la primera lectura provisional del Apartado 8— y ajustar su extensión por debajo del límite de 4.500 palabras.
- **Hito y apartado del trabajo:** P2 (`v0.3`) · Apartados 4, 5, 6, 7, 8 y 11 de `P2/informe.md`, `P2/seguimiento.md` y `P2/README.md`
- **Fuentes o texto propio utilizados como entrada:** Versión anterior de `informe.md` (plantilla de P1), registros cerrados de `P2/registros/` (`F-01` a `F-06`, `H-01` a `H-06`, `EV-01` a `EV-07`) y salida oficial del script `contar-palabras.mjs`.
- **Prompt, copiado tal cual:**

Estoy ampliando mi informe de ciberinteligencia sobre PHP2Shell desde la versión de P1 (`v0.2`) al Avance 2 (`P2/informe.md`, `v0.3`). Debo mantener intactos los 11 apartados y tablas de mi plantilla original, no superar el límite de 4.500 palabras en el cuerpo (apartados 1 a 10) y dejar pendientes el Resumen ejecutivo (apartado 1) y los apartados 9 y 10 para P3.

Ya he recogido y verificado los datos reales de 6 fuentes (`F-01` a `F-06`) con 7 copias PDF locales (`EV-01` a `EV-07`):
- Wiz Research (`F-06`) es la fuente origen de la afirmación sobre IA (descubrimiento el 19/08/2026 usando Wiz Atlas, Gemini 4 Argon y GPT-5.6 Sol; RCE pre-auth en Drupal/WordPress el 20-21/08). PHP Group (`F-01`) acredita en los GHSA de CVE-2026-109618 y CVE-2026-109619 a `@sagitzadik-wiz`, `@amyb-oai`, `@lcfr-hax` y `@tomash-areion`, pero no audita el papel de la IA.
- Sygnia (`F-05`) cita a Wiz (`F-06`) sobre la IA, reporta tráfico de ataque observado (compromisos reales desconocidos) y advierte de no depender solo de reglas WAF sobre `PHP_SESSION_UPLOAD_PROGRESS`.
- Snyk (`F-04`) no menciona la IA, describe CVE-2026-115560 como evasión parcial de CVE-2026-109619 y recoge las mitigaciones temporales de PHP advirtiendo que solo actualizar es seguro.
- PHP Group (`F-01`, `GHSA-658j-r8rw-q6mx` del 19/11/2026, CVSS 4.0 9.2, CWE-20/CWE-502) aclara que CVE-2026-115560 exige cambiar `session.serialize_handler` en tiempo de ejecución con `ini_set()` antes de `session_start()` con upload progress activo, y acredita a 7 reportadores distintos de los de octubre.
- CISA (`F-02`) incluyó CVE-2026-109618 y CVE-2026-109619 en KEV el 26/10/2026 (plazo 29/10/2026), sin atribución ni IoCs de red.

¿Cómo me recomiendas estructurar la ampliación de los apartados 4 (cronología de 4 fechas), 5 (contraste de dependencias), 6 (hallazgos H-01 a H-06), 7 (análisis provisional, explicaciones alternativas E-01/E-02 sobre PI-01, apartados sin datos justificados y revisión de sesgos/contradicciones sobre `PHP_SESSION_UPLOAD_PROGRESS`) y 8 (primera lectura provisional de amenazas) manteniendo rigor analítico y sin pasarme de las 4.500 palabras?

- **Respuesta completa:**

Para ampliar P2/informe.md (v0.3) respetando intactos los 11 apartados de tu plantilla y quedándote con margen por debajo de las 4.500 palabras (objetivo seguro: 3.800–4.100 palabras), conviene evitar repetir en el Apartado 7 lo ya tabulado en los Apartados 4 y 6, y recordar que contar-palabras.mjs suele dividir fechas e identificadores con guiones (CVE-2026-109618, GHSA-...) en varias palabras. Mantén los apartados 1, 9 y 10 con una nota breve de «Pendiente para P3» y concentra la ampliación en los cinco bloques siguientes:

Apartado 4 · Contexto y cronología (4 fechas)
Mantén la separación estricta entre Hecho y Afirmación atribuida, pero amplía la tabla de P1 para distinguir las cuatro dimensiones temporales exigidas en P2 (Fecha del hecho, Publicación, Observación técnica y Consulta):

Fecha del hecho	Publicación	Observación técnica	Fecha de consulta	Hecho o afirmación atribuida	Fuente	Limitación
19–21/08/2026 (Global)	21/10/2026	19–21/08/2026 (autodeclarada)	27/11/2026 (Europe/Madrid)	Afirmación atribuida: Wiz Research declara haber descubierto el fallo inicial el 19/08 con Wiz Atlas, Gemini 4 Argon y GPT-5.6 Sol, logrando RCE pre-auth en Drupal/WordPress el 20–21/08.	F-06	Fuente parte interesada; sin trazas reproducibles ni auditoría externa sobre el peso real de la IA.
21/10/2026 (UTC)	21/10/2026	N/A	27/11/2026 (Europe/Madrid)	Hecho: PHP Group publica los parches y avisos de CVE-2026-109618 y CVE-2026-109619, acreditando a @sagitzadik-wiz, @amyb-oai, @lcfr-hax y @tomash-areion.	F-01, F-03	Confirma autoría humana/organizativa y parcheo, pero no audita el uso de IA ni documenta ataques.
22/10/2026 (Global)	22/10/2026	22/10/2026 (secundaria)	27/11/2026 (Europe/Madrid)	Afirmación atribuida: Sygnia reporta tráfico de ataque observado y RCE en laboratorio, cita a Wiz respecto a la IA y alerta sobre los límites del WAF con PHP_SESSION_UPLOAD_PROGRESS.	F-05	No aporta independencia sobre la IA (depende de F-06) y declara desconocido el alcance real de compromisos.
23/10/2026 (UTC)	23/10/2026	N/A	27/11/2026 (Europe/Madrid)	Hecho: PHP difunde aviso informativo previo para CVE-2026-115560 y CISA actualiza su alerta inicial.	F-01, F-02	Aún no existía el parche definitivo ni el aviso completo GHSA-658j-r8rw-q6mx.
26/10/2026 (UTC)	26/10/2026	≤ 26/10/2026 (telemetría CISA)	27/11/2026 (Europe/Madrid)	Hecho: CISA incluye CVE-2026-109618 y CVE-2026-109619 en el catálogo KEV (plazo límite: 29/10/2026).	F-02	Confirma explotación activa, pero no aporta fecha exacta del primer ataque, atribución ni IoCs de red.
26/10/2026 (Global)	26/10/2026	26/10/2026 (secundaria)	27/11/2026 (Europe/Madrid)	Afirmación atribuida: Snyk describe CVE-2026-115560 como evasión parcial de CVE-2026-109619 y recoge las mitigaciones temporales de PHP sin mencionar la IA.	F-04	Diverge del encuadre final de F-01 (19/11) y no incluye telemetría propia de explotación.
19/11/2026 (UTC)	19/11/2026	N/A	27/11/2026 (Europe/Madrid)	Hecho: PHP Group publica GHSA-658j-r8rw-q6mx (CVE-2026-115560, CVSS 4.0 9.2, CWE-20/CWE-502), acotándolo a cambios de session.serialize_handler con ini_set() antes de session_start() y acreditando a 7 reportadores distintos de los de octubre.	F-01, F-03	No consta inclusión en KEV ni evidencia pública de explotación masiva.
Apartado 5 · Fuentes y método (contraste de dependencias)
Conserva intacta la tabla de 4 columnas de tu plantilla (añadiendo la fila de F-06 Wiz Research y enlazando los registros P2/registros/*.csv y evidencias EV-01 a EV-07) y añade un subapartado conciso de Contraste de dependencias entre fuentes (unas 100–130 palabras) que deje explícitas tres cadenas:

Metadatos primarios: F-03 (NVD) agrega información de F-01 (PHP Group) y F-02 (CISA), por lo que no suma confirmación independiente sobre hechos de parcheo o explotación.

Base técnica secundaria: Tanto F-04 (Snyk) como F-05 (Sygnia) parten de F-01 para versiones y mitigaciones.

Dependencia crítica en PI-01: La afirmación sobre el papel de la IA tiene un único origen trazable (F-06). F-05 se limita a citar a F-06, F-04 no menciona la IA y F-01 acredita a los investigadores sin auditar las herramientas usadas. Repetir el mismo origen en varias fuentes secundarias no aumenta la confianza.

Apartado 6 · Resultados y evidencias (H-01 a H-06)
Usa la tabla exacta de 5 columnas de la plantilla (Hallazgo | Pregunta | Observación verificable | Fuente y fecha | Qué no demuestra), dejando cada fila en 2–3 líneas sin mezclar interpretaciones:

H-01 (PI-01): Wiz Research (F-06, 21/10/2026) declara el hallazgo inicial (19/08) con Wiz Atlas, Gemini 4 Argon y GPT-5.6 Sol y RCE en Drupal/WordPress (20–21/08); PHP (F-01, 21/10) acredita a @sagitzadik-wiz, @amyb-oai, @lcfr-hax y @tomash-areion. Qué no demuestra: el grado real de autonomía de la IA ni auditoría independiente de esas trazas.

H-02 (PI-01): En fuentes secundarias, Sygnia (F-05, 22/10) solo cita a F-06 respecto a la IA, mientras Snyk (F-04, 26/10) no la menciona. Qué no demuestra: consenso independiente entre analistas externos sobre la autoría de la IA.

H-03 (PI-02): CISA (F-02, 26/10) añade CVE-2026-109618 y CVE-2026-109619 al catálogo KEV (plazo 29/10) y Sygnia (F-05, 22/10) reporta tráfico de ataque observado y RCE en laboratorio. Qué no demuestra: atribución de actores, volumen real de compromisos ni IoCs de red verificables.

H-04 (PI-01, PI-03): PHP Group (F-01, GHSA-658j-r8rw-q6mx, 19/11, CVSS 4.0 9.2, CWE-20/CWE-502) precisa que CVE-2026-115560 exige cambiar session.serialize_handler en ejecución con ini_set() antes de session_start() con upload progress activo, y acredita a 7 reportadores distintos de los de octubre. Qué no demuestra: uso de IA en este tercer fallo ni explotación activa (ausente en KEV).

H-05 (PI-03): Snyk (F-04, 26/10) encuadra CVE-2026-115560 como evasión parcial de CVE-2026-109619 y recoge las mitigaciones temporales de PHP advirtiendo que solo actualizar es seguro. Qué no demuestra: que la condición de 115560 sea habitual en producción ni invalida el alcance acotado de F-01.

H-06 (PI-03): Sygnia (F-05, 22/10) advierte que el WAF es un control adicional y que no debe dependerse solo de reglas sobre PHP_SESSION_UPLOAD_PROGRESS, porque CVE-2026-109618 no lo exige. Qué no demuestra: eficacia universal de una regla WAF concreta ni cobertura frente a acceso directo al origen.

Apartado 7 · Análisis provisional
Divídelo en cuatro bloques breves y directos (unas 700–850 palabras en total para no disparar el recuento):

Análisis provisional por pregunta (PI-01 a PI-03):

PI-01: Separa explícitamente los dos tramos del ciclo: en los CVEs de octubre (109618/109619) hay autoría confirmada de Wiz y OpenAI en F-01, pero el papel de la IA procede solo de una autodeclaración (F-06) sin trazas reproducibles; en CVE-2026-115560 ninguna fuente documenta IA y los 7 reportadores distintos apuntan a un hallazgo separado.

PI-02: Explotación activa confirmada para los dos CVEs iniciales (F-02, confianza alta), pero con alcance real de compromisos desconocido (F-05) y sin IoCs de red; evita equiparar la cuota global de PHP citada por F-06 con sistemas comprometidos.

PI-03: Actualizar PHP es la única remediación completa (H-05). Resume los tres límites operativos de las mitigaciones temporales: riesgo de agotamiento con memory_limit=-1, cobertura incompleta de reglas WAF basadas solo en PHP_SESSION_UPLOAD_PROGRESS (H-06), y bypass del WAF si existe acceso directo al origen.

Organizaciones, publicaciones e infraestructura (apartados sin datos justificados): Tres viñetas breves justificando que: (a) en Organizaciones no hay víctimas ni actores atribuidos por ausencia en F-02 y alcance; (b) en Publicaciones se excluyen foros cerrados, dark web y código PoC por OPSEC; y (c) en Infraestructura no hay datos propios por exclusión de escaneos activos.

Explicaciones alternativas sobre PI-01 (tabla de 5 columnas):

E-01 (Papel determinante de la IA en todo el ciclo): A favor: fechas y modelos concretos en F-06, créditos de @sagitzadik-wiz y @amyb-oai en F-01, entrada rápida en KEV (F-02). En contra: ausencia de trazas reproducibles/auditoría externa, F-02 no vincula ataques con IA y F-01 acredita a 7 reportadores distintos en 115560 bajo configuración atípica. Pendiente: publicación de trazas o declaraciones de los 7 reportadores antes del 30/11. Valoración: plausible con reservas en el descubrimiento inicial; no sostenida para 115560 ni para la explotación.

E-02 (Asistencia parcial de IA amplificada comercialmente + patch diffing humano): A favor: interés comercial de F-06 (Wiz Atlas), silencio de F-04 sobre IA y perfil de los 7 reportadores de GHSA-658j-r8rw-q6mx compatible con revisión clásica de parches. En contra: la acreditación conjunta de @amyb-oai y Wiz en F-01 respalda colaboración técnica real en IA y no solo marketing. Pendiente: verificar comunicados de OpenAI/Google o de los 7 reportadores antes del 30/11. Valoración: plausible y prudente; explica mejor la separación de descubridores y CVE-2026-115560.

Revisión de sesgos y contradicciones:

Corrección del sesgo inicial (v0.1): Descartar la asunción previa de que la IA generó la evasión CVE-2026-115560, refutada al cruzar F-01 y F-04.

Contradicción técnica sobre PHP_SESSION_UPLOAD_PROGRESS: Documenta que F-04 vincula session.upload_progress.enabled=0 a CVE-2026-109619, F-05 advierte que CVE-2026-109618 no requiere PHP_SESSION_UPLOAD_PROGRESS, y F-06 asocia upload-progress a 109618 y fatal-error backtrace / OPcache a 109619. Deja anotado que esta discrepancia entre fuentes secundarias se contrastará contra el texto técnico íntegro de los GHSA (F-01) en P3 y refuerza por qué el SOC no debe depender de un único filtro WAF.

Apartado 8 · Amenazas, indicadores y comportamientos (primera lectura provisional)
Añade una nota inicial indicando que es una lectura provisional para P2 (a revisar con el Tema 6 y cerrar en P3) y rellena la tabla exacta de 5 columnas (Indicador o comportamiento | Fuente y fecha | Relación con el caso | Técnica, si procede | Limitación) con tres filas limpias:

Explotación remota pre-auth de servidores web PHP vulnerables (CVE-2026-109618, CVE-2026-109619): Fuentes F-01 (21/10), F-02 (26/10), F-05 (22/10). Técnica provisional MITRE ATT&CK: Exploit Public-Facing Application (T1190, a confirmar en P3). Limitación: una versión desactualizada no prueba explotación; F-02 no publica IoCs de red ni atribución.

Deserialización condicionada a cambio de session.serialize_handler en ejecución (CVE-2026-115560): Fuentes F-01 (19/11), F-04 (26/10). Técnica: pendiente de valoración en P3. Limitación: requiere configuración atípica (ini_set() antes de session_start() con upload progress activo) y no figura en KEV.

Peticiones HTTP anómalas con PHP_SESSION_UPLOAD_PROGRESS y referencias secundarias a PoC: Fuentes F-04 (26/10), F-05 (22/10). Técnica: pendiente de contraste en P3. Limitación: parámetro útil solo como señal parcial (no cubre CVE-2026-109618 según F-05); no se inspecciona código PoC por OPSEC y todo indicador futuro deberá ir neutralizado (defanged).

Comprobación rápida de presupuesto de palabras
Si tras pegar estos cambios ejecutas node proyecto-final/contar-palabras.mjs entregas/castilloCayetano/PF/P2/informe.md y te acercas a 4.500 palabras, el recorte más limpio sin perder rigor está en sintetizar el texto narrativo del Apartado 5 (dejando los detalles de cada fuente en P2/registros/fuentes.csv) y no repetir citas largas de H-01 a H-06 dentro del Apartado 7 (cita directamente el código H-01, H-04, etc.). ¿Quieres que revisemos el borrador de alguno de estos apartados concretos o el recuento una vez lo montes?

- **Qué hice con la respuesta:** Comparé la propuesta con mi archivo original de P1 para asegurar que se mantenían intactos la portada, el historial de versiones, el índice y los 11 encabezados exactos, integré los apartados 4 a 8 y 11 en `P2/informe.md` (`v0.3`) y apliqué un recorte de redacción en los apartados 5 y 7 tras comprobar que el primer borrador superaba las 4.500 palabras (4.594 → 3.923 palabras).
- **Qué comprobé y con qué fuentes originales u oficiales:** Contrasté cada fecha, atribución, lista de *reporters* y mitigación del texto final contra los siete PDFs preservados en `P2/recursos/` (`EV-01` a `EV-07`) y los cuatro CSV de `P2/registros/`. Además, verifiqué la estructura y extensión exacta ejecutando `node proyecto-final/contar-palabras.mjs entregas/castilloCayetano/PF/P2/informe.md` (3.923 palabras en el cuerpo, 39 en el resumen ejecutivo y sin avisos de plantilla).
- **Evidencia:** [Exportación local `P2/ia/uso-02.md`](./ia/uso-02.md) 
https://share.gemini.google/Eo8wfbrg45Dw
- **Usos relacionados:** Uso 01 (P2)