# F01 · Exploración guiada de la dark web y canal ético

| | |
|---|---|
| **Tema** | 5 · Fuentes cerradas y dark web |
| **Tipo** | Actividad formativa · no calificada |
| **Modalidad** | Individual o en parejas, durante la sesión presencial |
| **Producto** | Ficha de trabajo completada y aviso de prueba en el canal privado |
| **Entrega** | En clase · aviso por el [canal privado](../../SECURITY.md) y puesta en común |

---

## 1. Objeto

En esta sesión vas a poner en práctica el [Tema 5](https://github.com/hector-ae21/CIBINT/tree/main/contenidos/05-fuentes-cerradas-y-dark-web) trabajando directamente con **Tor Browser**, una lista de direcciones `.onion` para verificar qué hay detrás de cada una y material controlado sobre entornos delictivos.

La idea no es «navegar por la dark web» sin rumbo, sino entrenar cuatro cosas concretas:

1. configurar Tor Browser con criterios mínimos de seguridad operacional;
2. comprobar qué tipo de servicios reales existen en Tor y verificar si una dirección `.onion` es auténtica o una suplantación;
3. reconocer cómo operan los sitios delictivos más frecuentes en ciberinteligencia (mercados de credenciales y logs, sitios de extorsión de ransomware y directorios sin moderar) sin exponerte ni cruzar límites legales;
4. practicar el protocolo de parada y el envío de un aviso real a través del [canal privado de la asignatura](../../SECURITY.md).

## 2. Contexto

En ciberinteligencia conviene quitar cuanto antes el misterio alrededor de la dark web. Quien entra por primera vez suele esperar un catálogo abierto de delitos y se encuentra, en realidad, con algo bastante distinto: servicios legítimos muy lentos, enlaces que dejan de funcionar de un día para otro, clones preparados para robar cuentas y entornos delictivos que funcionan por reputación, invitación o extorsión.

Un analista necesita moverse con cabeza fría: saber qué comprueba, verificar siempre las direcciones, no tocar muestras sospechosas y saber exactamente en qué momento tiene que cerrar la pestaña y avisar por el canal adecuado.

## 3. Preparación

Trabajarás sobre la [ficha de trabajo](plantilla-respuesta.md) (puedes guardarla en local para ir rellenándola durante la clase) y el expediente de [hallazgos de clase](datos/hallazgos-clase.md).

Necesitas:

- **Tor Browser** descargado desde su web oficial ([torproject.org](https://www.torproject.org/download/)) o ya disponible en la máquina virtual del aula;
- un navegador normal aparte para contrastar direcciones oficiales en la web abierta;
- tu cuenta de GitHub con acceso a este repositorio para enviar el aviso del Bloque 4.

| Bloque | Qué haces |
|---|---|
| **Bloque 1** | Configuración de Tor Browser y comprobación de circuito |
| **Bloque 2** | Verificación paso a paso de los seis enlaces `.onion` |
| **Bloque 3** | Análisis de entornos delictivos y puntos de parada |
| **Bloque 4** | Envío de aviso por el canal privado (`SECURITY.md`) |
| **Cierre** | Puesta en común en el aula |

---

## 4. Paso a paso

### Bloque 1 · Prepara el entorno y comprueba el circuito

Antes de abrir ningún enlace `.onion`, deja listo el navegador y comprueba cómo sale tu tráfico:

1. Abre **Tor Browser** y pulsa **Connect**. No inicies sesión en ninguna cuenta personal ni instales extensiones.
2. Pulsa el icono del **escudo** (junto a la barra de direcciones) y entra en *Settings*. Cambia el nivel de seguridad de *Standard* a **Safer**. Anota en la ficha qué desactiva este nivel frente a *Standard* y qué añade **Safest**.
3. Abre `https://check.torproject.org/`. Comprueba que aparece el mensaje de confirmación de que estás usando Tor.
4. Pulsa el icono de información de la barra de direcciones (a la izquierda de la URL) para ver el **circuito de Tor**. Anota los países de los tres saltos (nodo de entrada, nodo intermedio y nodo de salida). **No apuntes ni captures tu IP real.**
5. Abre otra web normal en una pestaña distinta (por ejemplo, `https://www.uneatlantico.es`) y vuelve a mirar el circuito. Comprueba qué nodos cambian y cuál suele mantenerse.

### Bloque 2 · Verifica los seis enlaces `.onion`

Aquí tienes seis direcciones `.onion` sin indicar a quién pertenece cada una. **No des por hecho que todas son legítimas ni que todas cargan.**

| Código | Dirección `.onion` |
|---|---|
| `ENL-01` | `http://2gzyxa5ihm7nsggfxnu52rck2vv4rvmdlkiu3zzui5du4xyclen53wid.onion` |
| `ENL-02` | `https://duckduckgogg42xjoc72x3sjasowoarfbgcmvfimaftt6twagswzczad.onion` |
| `ENL-03` | `https://www.bbcnewsd73hkzno2ini43t4gblxvycyac5aw4gnv7t2rccijh7745uqd.onion` |
| `ENL-04` | `https://protonmailrmez3lotccipshtkleegetolb73fuirgj7r4o4vfu7ozyd.onion` |
| `ENL-05` | `http://juhanurmihxlp77nkq76byazcldy2hlmovfu2epvl5ankdibsot4csyd.onion` |
| `ENL-06` | `http://bbcnewsd73hkzno2ini43t4gblxvycyac5aw4gnv7t2rccijh7745uqe.onion` |

Para cada enlace, sigue exactamente estos cuatro pasos y rellena la tabla de la ficha:

1. **Abre el enlace en Tor Browser** con el nivel de seguridad en **Safer** (puedes probar **Safest** en uno de ellos para ver qué cambia). Anota si carga, qué servicio parece ser, en qué idioma está y si pide registro.
2. **Revisa el circuito de Tor** en cualquiera de los enlaces que carguen. Compáralo con el del Bloque 1: ¿sigue apareciendo un nodo de salida hacia Internet normal o el recorrido cambia? Apunta por qué ocurre esto.
3. **Verifica la dirección en la web abierta.** Abre tu navegador normal, busca la página oficial de la organización correspondiente (por ejemplo, su página de acceso por Tor o la cabecera `Onion-Location` en Tor Browser) y compara **carácter por carácter** los 56 caracteres de la dirección. Marca si la dirección está verificada o si detectas alguna anomalía.
4. **Clasifica su función** en la dark web: privacidad, elusión de censura, documentación, indexación o dirección manipulada/no verificable.

**Comprobación extra sobre `ENL-05`:** cuando llegues a `ENL-05`, haz **una única búsqueda neutra** (por ejemplo, `cybersecurity` o `whistleblower`) y observa solo la página de resultados, **sin hacer clic en ningún resultado desconocido**. Anota:

- qué tipo de títulos aparecen mezclados en los primeros resultados;
- por qué un buscador de Tor solo cubre una parte pequeña de la red y no sirve como garantía de seguridad.

> Si la red del aula va lenta y algún enlace tarda demasiado en resolver, espera un minuto, prueba *New Circuit for this Site* y, si sigue sin responder, anótalo como no disponible en ese momento sin perder el ritmo de la clase.

### Bloque 3 · Cómo opera el ecosistema delictivo sin exponerte

#### Parte 3.1 · Observación en abierto

1. Entra desde tu navegador normal en **[Ransomware.live](https://www.ransomware.live/)**. Elige un grupo activo cualquiera y mira dos o tres entradas recientes. Anota qué elementos repiten estos sitios de extorsión (*Data Leak Sites*): nombre de víctima, fechas, cuentas atrás, volumen de datos anunciado o enlaces caídos. Explica en dos líneas por qué un analista prefiere usar un rastreador público así antes que entrar directamente al `.onion` del grupo.
2. Abre el comunicado oficial de la operación contra **Genesis Market** ([Policía de Países Bajos](https://www.politie.nl/en/news/2023/april/5/operation-cookiemonster.html)). Anota en dos líneas qué vendía ese mercado más allá de contraseñas y cómo se accedía a él.

#### Parte 3.2 · Análisis de los hallazgos de clase

Abre el archivo **[datos/hallazgos-clase.md](datos/hallazgos-clase.md)**. Contiene tres casos preparados para clase que reproducen de forma controlada escenarios reales habituales en la dark web:

- **Caso A:** anuncio en un mercado clandestino de logs de *infostealers* y accesos VPN con *escrow* y muestra descargable.
- **Caso B:** publicación de un sitio de extorsión de ransomware con cuenta atrás y supuesta muestra de documentos sanitarios.
- **Caso C:** directorio anónimo de enlaces `.onion` que mezcla servicios conocidos con categorías de contenido delictivo grave.

Para cada uno de los tres casos, completa en tu ficha:

1. **Modelo delictivo:** cómo operan y de qué forma buscan dinero o presión.
2. **Señales de riesgo o engaño:** qué elementos hacen peligroso o poco fiable lo que aparece (archivos `.zip`, pago en criptomonedas, cifras sin prueba, enlaces sin verificar).
3. **Punto de parada:** qué NO harías bajo ningún concepto y en qué momento exacto cierras la pestaña.

### Bloque 4 · Denuncia el hallazgo por el canal ético

Vas a realizar ahora un aviso real de práctica usando el **[canal privado de la asignatura](../../SECURITY.md)**:

1. Elige uno de los casos del Bloque 3 (según te indique el docente en el aula o, si no hay reparto, el que prefieras entre **Caso A**, **Caso B** o **Caso C**).
2. Entra en la pestaña **Security** de este repositorio en GitHub y pulsa **Report a vulnerability**.
3. En **Title**, escribe exactamente:
   `[F01] Apellido Nombre · Aviso de práctica · Caso X`
   *(sustituye `Apellido Nombre` por tu nombre y `Caso X` por el caso elegido)*.
4. En **Description**, copia la plantilla de [SECURITY.md](../../SECURITY.md#plantilla) y rellénala para tu caso.
5. Revisa antes de pulsar enviar:
   - describe **qué tipo de actividad delictiva o dato sensible apareció**, pero **no pegues credenciales, datos personales, fragmentos robados ni enlaces peligrosos**;
   - indica claramente qué has hecho (detener la navegación, no descargar archivos, no interactuar);
   - especifica qué confirmación u orientación necesitas para continuar.
6. Envía el aviso y anota en tu ficha la hora de envío y un resumen en dos líneas.

> Aunque sea un ejercicio de clase, el aviso debe quedar redactado como si fuera real: breve, factual y sin reproducir material sensible. En clase comentaremos qué hace que un aviso sea útil para quien lo recibe.

---

## 5. Límites y protocolo de parada

Se aplican las [normas de la asignatura](../../NORMAS.md). Durante esta sesión:

| Puedes | No puedes |
|---|---|
| Usar Tor Browser en nivel **Safer** o **Safest** con los seis enlaces de la tabla | Navegar libremente por directorios anónimos, wikis de enlaces o resultados desconocidos de Ahmia |
| Verificar direcciones `.onion` en las webs oficiales de cada organización | Introducir credenciales personales, correos reales o datos tuyos en servicios `.onion` |
| Consultar `ransomware.live` y comunicados oficiales en navegador normal | Buscar o entrar a sitios delictivos reales, mercados clandestinos o sitios de extorsión en vivo |
| Enviar un aviso de práctica por **Security → Report a vulnerability** | Descargar muestras, probar contraseñas o subir contenido sensible a *issues*, *pull requests* o debates públicos |

**Si durante la práctica aparece de forma accidental cualquier página sospechosa, enlace redirigido o contenido ilegal:** cierra la pestaña al momento, no hagas capturas del contenido y avisa por el [canal privado](../../SECURITY.md).

