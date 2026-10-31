# A03 · Huella pública

> **Cómo usas esta plantilla**
>
> Cópiala como `README.md` en tu carpeta `A03`: en la modalidad A, `entregas/apellidoNombre/A03/`; en la modalidad B, una carpeta `A03` en tu equipo, fuera del repositorio del curso, que entregarás comprimida en el Campus Virtual. Trabaja **sobre esa copia**. No edites este archivo ni la carpeta de nadie más.
>
> Rellena los apartados sin cambiar su orden ni su numeración. Sustituye cada bloque «Qué debe contener» por tu respuesta. Si algo no te aplica, explica por qué en lugar de borrarlo. Borra estas instrucciones antes de entregar.
>
> Completa los apartados 2 y 3 **antes** de la primera consulta: en la modalidad A, haz un *commit*; en la modalidad B, anota al final del apartado 3 la fecha y hora de cierre del plan. Cada afirmación se acompaña de la fila del registro de la que sale: `(OBT-04)`, `(OBT-07, OBT-08)`.
>
> Enunciado completo: [A03 · Huella pública](https://github.com/hector-ae21/26-27-CIBINT/blob/main/actividades/A03-huella-publica/README.md)

## Estudiante

- Nombre: Eirik Alberto Rosete León
- Carpeta personal: [/entregas/roseteEirik](/entregas/roseteEirik/)
- Modalidad: A (Organización)
- Objetivo: Health Service Executive (HSE)
- ¿Es el objetivo de tu proyecto final?: Sí
- Punto de partida (dominio principal o identificadores propios): hse.ie
- Periodo de obtención, con zona horaria: 31/10/2026 UTC+1 (Madrid)

---

## 1. Resumen ejecutivo

> **Qué debe contener.** Se escribe al final. Como máximo 250 palabras. Un párrafo que el destinatario pueda leer sin el resto del informe y una tabla que responda cada pregunta del apartado 2.3 con su nivel de confianza y sus referencias.

| Pregunta | Respuesta breve | Confianza | Referencias |
|---|---|---|---|
| | | | |

---

## 2. Encargo

### 2.1 Objetivo elegido

Modalidad A. El objetivo es el Health Service Executive (HSE), servicio público de salud de Irlanda y objetivo de mi proyecto final (ataque de ransomware Conti, 2021). Como el ataque empezó con un correo de phishing, interesa saber qué identidad, canales y relaciones del HSE podría usar un atacante para hacerse pasar por él. Esta actividad no amplía el alcance aprobado del proyecto.

Cumple los requisitos de la modalidad A. Es un organismo público con actividad en Irlanda (UE) que publica su información institucional en su propio dominio (estructura, consejo de dirección, actas e informes en hse.ie y about.hse.ie). Su base legal, la Health Act 2004, está en el Irish Statute Book.

Para comprobar que hay material para la A04, el 30/10/2026 consulté site:hse.ie filetype:pdf. Aparecen PDF alojados en www.hse.ie y assets.hse.ie e igualmente hay pdf indexados dentro de about.hse.ie, que he consultado previamente para el avance del proyecto final el 28/10/2026.

### 2.2 Requerimiento

| Componente | Contenido |
|---|---|
| Destinatario | Responsable de Seguridad de la Información (CISO) del HSE |
| Decisión | Qué información pública del HSE podría aprovechar un atacante para preparar un engaño, una suplantación o un reconocimiento, y qué conviene revisar o reducir |
| Objeto | La huella pública institucional y digital del HSE accesible por fuentes abiertas |
| Horizonte | Antes de iniciar la A04, que se entrega el 6/11/2026 |
| Alcance | Fuentes abiertas y pasivas: Google, Wayback Machine, OpenCorporates, TinEye, Irish Statute Book y web pública del HSE. Grafo manual en Maltego |
| Exclusiones | Datos de pacientes, personal y proveedores; materiales, filtraciones o foros del ataque de 2021; nombres de personas (solo cargos si hace falta); abrir sitios sospechosos de suplantación; homónimos como el Health and Safety Executive británico (hse.gov.uk); escaneos, consultas DNS y transformaciones de Maltego contra el HSE; contacto con la organización |
| Producto | Informe de huella pública con registro de obtención, evidencias, ficha del objetivo para la A04, grafo de Maltego y matriz de perspectiva del atacante. TLP:CLEAR tras revisar que solo hay datos institucionales. Es un supuesto académico por lo que el informe no se le envía |

Requerimiento en una frase: identificar, antes de la A04 y solo con fuentes abiertas pasivas, qué identidad legal, canales y relaciones del HSE están al alcance de cualquiera, qué podría aprovechar un atacante y qué conviene revisar o reducir.

### 2.3 Preguntas de inteligencia

| Prioridad | Pregunta | Huella que cubre | Te ayuda a decidir |
|---:|---|---|---|
| 1 | ¿Qué dominios, subdominios y perfiles oficiales tiene el HSE, desde cuándo, y qué otros parecidos existen sin que los declare? | Canales | Qué canales confirmar como oficiales y cuáles revisar, retirar o vigilar |
| 2 | ¿Qué entidad legal hay detrás de la marca HSE, en qué norma se apoya y qué entidades relacionadas comparten su marca o sus dominios? | Corporativa | Qué entidades y dominios forman parte del objetivo y pasan a la A04 |
| 3 | ¿Qué terceros (analítica, formación, empleo, redes sociales) aparecen vinculados a sus canales, y el vínculo lo declara el HSE o solo se observa? | Relaciones | Qué relaciones con terceros revisar o exponer menos por servir de pretexto en un engaño |

---

## 3. Plan de obtención

### 3.1 Herramientas por pregunta

| Pregunta | Herramienta | Alternativa descartada y motivo | Entrada | Qué expone y a quién | Resultado esperado |
|---|---|---|---|---|---|
| P1 | Google con operadores | Babel Street: comercial y pensada para fuentes multilingües; aquí todo está en inglés | site:hse.ie -site:www.hse.ie, "Health Service Executive" (site:x.com OR site:facebook.com OR site:linkedin.com), intitle:"HSE" "Health Service Executive" -site:hse.ie -site:gov.ie | Envía las consultas a Google, sin sesión. Solo llega al HSE al abrir una página pública suya | Subdominios indexados, perfiles oficiales y candidatos no declarados |
| P1 | TinEye (opcional) | Google Lens: requiere sesión de Google y da coincidencias aproximadas | URL del logotipo publicado en www.hse.ie | Envía la URL de la imagen a TinEye. No toca al objetivo | Dominios ajenos que reutilizan el logotipo, registrados sin abrirlos |
| P1 | Wayback Machine | archive.today: menos cobertura histórica | URL de la página de www.hse.ie donde declara sus canales oficiales (obtenida con Google) | Envía la URL a Internet Archive. No toca al objetivo | Canales añadidos o retirados entre dos capturas fechadas |
| P2 | OpenCorporates | BORME: solo recoge sociedades españolas | "Health Service Executive" (Irlanda) y "HSE" para homónimos | Envía la búsqueda a OpenCorporates. No toca al objetivo | Probable consulta vacía (organismo creado por ley) y homónimos con su número de registro |
| P2 | Google con operadores | Wikipedia: fuente secundaria | site:hse.ie ("board" OR "annual report"), site:irishstatutebook.ie "Health Act 2004", site:gov.ie "Health Service Executive" | Envía las consultas a Google; visita páginas públicas del HSE | Estructura y órganos de gobierno que declara el HSE, norma de creación, organismo del que depende y entidades relacionadas |
| P3 | Google con operadores | Revisar código fuente o cabeceras: es análisis técnico, propio de la A04 | site:hse.ie (intitle:cookies OR intitle:privacy) "third party" | Envía las consultas a Google; visita páginas públicas del HSE | Terceros declarados por el propio HSE |
| P3 | Maltego Community | draw.io: no guarda tipos de entidad ni fuentes | Entidades introducidas a mano desde las filas OBT, sin transformaciones | Solo el inicio de sesión en Maltego. No toca al objetivo | Grafo con relaciones observadas, declaradas y pendientes |

### 3.2 Herramientas que no se usan

| Herramienta | Motivo |
|---|---|
| Intelligence X / Serus | Con el dominio hse.ie pueden devolver material filtrado en 2021, prohibido por las reglas reforzadas |
| Hunchly | No responde a ninguna pregunta; las evidencias se conservan con capturas propias y su hash |
| Google Lens | Alternativa a TinEye, descartada en 3.1 |
| OpenSanctions | Ninguna pregunta requiere comprobar sanciones y llevaría a buscar personas |
| Babel X / Babel Street | Licencia comercial; las fuentes están en inglés |
| BORME | Solo recoge sociedades españolas |

### 3.3 Configuración y seguridad de la operación

Identidad de investigación: la del Tema 2, con correo dedicado, usada solo para Maltego. El resto de consultas se hacen sin cuenta.

Navegador y perfil: Brave en incógnito con perfil dedicado, sin sesiones personales ni sincronización; historial borrado al cerrar.

Interacción con el objetivo: solo páginas públicas del HSE necesarias para una pregunta, sin formularios ni áreas con acceso.

Carpeta de trabajo: carpeta local cifrada fuera del repositorio, solo accesible por mí. Capturas originales con su hash SHA-256 y copias redactadas van a entregas/roseteEirik/A03/evidencias/.

---

## 4. Obtención

### 4.1 Registro de obtención

> **Qué debe contener.** Una fila por consulta o acción, incluidos los errores, los resultados vacíos y las restricciones. Fecha y hora en formato `AAAA-MM-DD HH:MM`, con la zona horaria indicada en la cabecera.

| ID | Herramienta | Consulta o acción exacta | Fecha y hora | Resultado | Límite | Evidencia |
|---|---|---|---|---|---|---|
| OBT-01 | | | | | | |

### 4.2 Resultados por herramienta

> **Qué debe contener.** Para Google, Wayback Machine, la fuente societaria, Maltego y la herramienta opcional: qué pregunta respondía, qué obtuviste, con referencias, y qué límite tiene.

### 4.3 Revisión de la elección

| Pregunta | Herramienta prevista | Herramienta utilizada | Evidencia obtenida | ¿Resuelve la pregunta? | Cambio justificado |
|---|---|---|---|---|---|
| | | | | | |

---

## 5. Análisis de la huella

### 5.1 Ficha del objetivo

> **Qué debe contener.** Es el punto de partida de la A04. Una fila por campo:
>
> - modalidad A: nombre legal, marcas, filiales o entidades relacionadas, dominios oficiales, canales y perfiles oficiales, proveedores observados;
> - modalidad B: nombre y alias, cuentas y perfiles, correos públicos, relaciones profesionales o académicas, webs y dominios, documentos publicados.

| Campo | Dato | Referencia | Fecha del dato | Precaución |
|---|---|---|---|---|
| | | | | |

### 5.2 Huella por dimensiones

> **Qué debe contener.** Para cada huella, dos partes separadas: **Observado**, con referencias, y **Valoración**, con fiabilidad de la fuente, credibilidad de la información y lo que falta.

#### Corporativa o profesional

#### De canales

#### De relaciones

### 5.3 Grafo de relaciones

> **Qué debe contener.** La imagen del grafo exportado desde Maltego, enlazada desde `evidencias/`, y una leyenda que distinga relaciones observadas, declaradas y pendientes, cada una con su referencia.

| Relación | Tipo | Referencia |
|---|---|---|
| | | |

### 5.4 Valoración de hallazgos clave

| Hallazgo | Referencias | Fiabilidad de la fuente | Credibilidad de la información | Hecho o inferencia | Contraste independiente |
|---|---|---|---|---|---|
| | | | | | |

---

## 6. Perspectiva del atacante

> **Qué debe contener.** Al menos tres filas, cada una a partir de un hallazgo propio. Describe el riesgo sin instrucciones operativas.

| Información visible | Referencia | Cómo podría aprovecharla un atacante | A qué afectaría | Medida defensiva | Prioridad |
|---|---|---|---|---|---|
| | | | | | |

---

## 7. Limitaciones, datos descartados e incidencias

> **Qué debe contener.** Preguntas que no has podido responder y por qué. Datos que has descartado por quedar fuera del alcance, incluidos los homónimos y los datos de terceros. Incidencias, solo con su categoría y su fila `OBT`, e indicación de si avisaste por el canal privado. Si no hubo incidencias, escríbelo.

---

## 8. Índice de evidencias

| Evidencia | Qué muestra | Fila del registro | Qué se ha ocultado |
|---|---|---|---|
| | | | |

---

## 9. Uso de inteligencia artificial

Ver [registro-ia.md](registro-ia.md).

---

## Comprobación

- [ ] El objetivo cumple los requisitos de mi modalidad y no investigo a ninguna otra persona.
- [ ] Cerré los apartados 2 y 3 antes de la obtención: *commit* en la modalidad A, fecha de cierre en la modalidad B.
- [ ] Cada afirmación lleva su referencia `OBT` y la he comprobado.
- [ ] Las capturas están recortadas y anonimizadas.
- [ ] Entrego antes del viernes 30 de octubre a las 23:59.
- [ ] Modalidad A: solo he modificado `entregas/apellidoNombre/A03/`. Modalidad B: nada está en el repositorio del curso.
