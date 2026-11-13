# A04 · Exposición técnica y documental

## Estudiante

- Nombre: Eirik Alberto Rosete León
- Carpeta personal: [/entregas/roseteEirik](/entregas/roseteEirik/)
- Modalidad: A (Organización)
- Objetivo: Health Service Executive (HSE)
- Entrega de la A03 (enlace al *pull request* o «entregada en el Campus Virtual»): 
- Periodo de obtención, con zona horaria: 13/11/2026, UTC+1 (Madrid)

---

## 1. Resumen ejecutivo

> **Qué debe contener.** Se escribe al final. Como máximo 300 palabras. Un párrafo que el destinatario pueda leer sin el resto del informe, con las conclusiones de la A03 que cambian, y una tabla que responda cada pregunta del apartado 2.3 con su nivel de confianza y sus referencias.

| Pregunta | Respuesta breve | Confianza | Referencias |
|---|---|---|---|
| | | | |

---

## 2. Punto de partida

### 2.1 Ficha del objetivo de la A03

| Campo | Dato | Referencia | Entrada para |
|---|---|---|---|
| Nombre legal | Health Service Executive (Feidhmeannacht na Seirbhíse Sláinte), creado por la Health Act 2004 | A03 OBT-12 | Atribución de certificados y documentos |
| Marcas | HSE, HSE Live y National Screening Service | A03 OBT-05, A03 OBT-06 | Lectura de certificados y metadatos |
| Entidades relacionadas | HSE Board, ministerios, gov.ie y data.gov.ie | A03 OBT-11, A03 OBT-13 | Separación de documentos del Gobierno |
| Dominios oficiales | hse.ie y siete subdominios: about, careerhub, healthservice, www2.healthservice, hepctest, service-manual y www2 | A03 OBT-01, A03 OBT-02, A03 OBT-09, A03 OBT-14 | Shodan, crt.sh y Maltego |
| Canales y perfiles | LinkedIn, X, Facebook, Instagram, TikTok, YouTube y línea HSE Live | A03 OBT-03, A03 OBT-06, A03 OBT-08 | Solo el grafo |
| Proveedores observados | Redes sociales y proveedores sin nombre | A03 OBT-06, A03 OBT-14 | Separación de servicios de proveedor |

### 2.2 Requerimiento

| Componente | Contenido |
|---|---|
| Destinatario | Responsable de Seguridad de la Información (CISO) del HSE |
| Decisión | Qué servicios visibles desde Internet y qué metadatos de sus documentos podría aprovechar un atacante, y qué conviene corregir |
| Objeto | Servicios web y de correo con nombres de hse.ie y metadatos de los documentos publicados en hse.ie |
| Horizonte | Antes de la entrega de la A04, el 13/11/2026 |
| Alcance | Shodan con hostname:, ssl: y ssl.cert.subject.cn: sobre hse.ie; crt.sh como contraste; Maltego para documentos y grafo |
| Exclusiones | Las de la A03; org:, net:, búsquedas por producto y fichas que no sean web o correo; abrir IP o puertos; escaneos y consultas DNS; vulnerabilidades de servicios concretos; personas de los metadatos |
| Producto | Informe con registro, evidencias con IP y nombres ocultos, metadatos seudonimizados, grafo final y recomendaciones. Supuesto académico |

### 2.3 Preguntas de inteligencia

| Prioridad | Pregunta | Huella que cubre | Te ayuda a decidir |
|---:|---|---|---|
| 1 | ¿Qué servicios web y de correo con nombres de hse.ie se observan desde Internet, desde cuándo, y cuáles están en rangos de un proveedor y no del HSE? | Técnica | Qué servicios entran en el inventario propio y cuáles revisar con su proveedor |
| 2 | ¿Qué nombres de sistemas o subdominios aparecen en los certificados de hse.ie que no salían en la A03? | Técnica | Qué nombres revisar porque los certificados los hacen públicos |
| 3 | ¿Qué revelan los metadatos de los documentos publicados en hse.ie (autores, software, fechas y correos) y qué parte procede de terceros? | Documental | Si conviene limpiar los metadatos antes de publicar y en qué tipos de documento |

---

## 3. Plan de obtención

### 3.1 Consultas y documentos previstos

| Pregunta | Herramienta | Consulta, filtro o criterio | Fuente de contraste | Qué expone y a quién | Resultado esperado |
|---|---|---|---|---|---|
| P1 | Shodan | hostname:hse.ie y dos fichas de servicios web o de correo | crt.sh | Envía hse.ie a Shodan. No llega al HSE | Servicios y facetas; en cada ficha, puerto, producto, fecha y titular del rango |
| P1 | Shodan | ssl:"hse.ie" | crt.sh | Envía hse.ie a Shodan. No llega al HSE | Servicios con certificados que mencionan hse.ie, también en proveedores |
| P2 | Shodan | ssl.cert.subject.cn:hse.ie | crt.sh | Envía hse.ie a Shodan. No llega al HSE | Certificados emitidos para hse.ie |
| P2 | crt.sh | %.hse.ie | Shodan y ficha de la A03 | Envía hse.ie a crt.sh. No llega al HSE | Nombres de los certificados y sus fechas |
| P3 | Maltego | To Files (Office) sobre hse.ie | Propiedades de un documento en el navegador | Envía hse.ie a un buscador. No llega al HSE | Documentos indexados, por tipo |
| P3 | Maltego | Parse meta information sobre documentos variados | Propiedades de un documento en el navegador | El servidor de Maltego descarga cada documento: la descarga llega al HSE | Autores, software, fechas y correos |

### 3.2 Configuración y seguridad de la operación

Cuenta de Shodan: gratuita. Sin API, descargas, escaneos ni Shodan Images.

Sustitución de FOCA: por indicación del docente, los metadatos se obtienen con dos transforms de Maltego, que buscan los documentos y leen sus metadatos sin descargarlos en mi equipo. Son los únicos transforms que se ejecutan; ninguno de DNS, IP, correo ni personas.

Selección de documentos de tipos, subdominios y años distintos.

Navegador y carpeta de trabajo: Brave en incógnito con el perfil de la A03. Capturas originales fuera del repositorio; en evidencias/ solo copias con IP, usuario y nombres tapados. Nombres y correos de los metadatos como USR-01.

Al terminar: se borran los grafos de esta actividad y no se entregan exportaciones.

---

## 4. Obtención

### 4.1 Registro de obtención

> **Qué debe contener.** Una fila por consulta o acción, incluidos los errores, los resultados vacíos y las restricciones. Fecha y hora en formato `AAAA-MM-DD HH:MM`, con la zona horaria indicada en la cabecera.

| ID | Herramienta | Consulta o acción exacta | Fecha y hora | Resultado | Límite | Evidencia |
|---|---|---|---|---|---|---|
| OBT-01 | | | | | | |

### 4.2 Shodan

> **Qué debe contener.** Las consultas con su número de resultados y lo que muestran sus facetas. Las fichas abiertas. Una tabla agregada de servicios clasificados en los tres grupos, con la fuente de contraste de cada atribución. Sin vulnerabilidades asociadas a servicios concretos.

| Consulta | Resultados | Facetas relevantes | Referencia |
|---|---:|---|---|
| | | | |

| Grupo | Servicios o puertos observados | Fechas de observación | Cómo se ha contrastado | Referencias |
|---|---|---|---|---|
| Del objetivo | | | | |
| De un proveedor | | | | |
| Relación no demostrada | | | | |

### 4.3 FOCA

> **Qué debe contener.** Proyecto y configuración. Documentos localizados y analizados, por tipo. Criterio de selección. Resumen por categorías con recuentos, patrones e interpretación. En la modalidad A, nunca con valores personales: por ejemplo, «formato nombre.apellido (USR-01 a USR-06)». Si usaste el procedimiento alternativo, por qué.

| Tipo de documento | Localizados | Analizados | Intervalo de fechas |
|---|---:|---:|---|
| | | | |

| Categoría | Elementos | Patrón observado | Interpretación y límite | Referencia |
|---|---:|---|---|---|
| Usuarios | | | | |
| Carpetas y rutas | | | | |
| Impresoras | | | | |
| Software | | | | |
| Correos | | | | |
| Sistemas operativos | | | | |
| Servidores | | | | |

### 4.4 Revisión de la elección

| Pregunta | Prevista | Utilizada | Evidencia obtenida | ¿Resuelve la pregunta? | Cambio justificado |
|---|---|---|---|---|---|
| | | | | | |

---

## 5. Análisis e integración con la A03

### 5.1 Huella técnica

> **Qué debe contener.** Dos partes separadas: **Observado**, con referencias, y **Valoración**, con fiabilidad de la fuente, credibilidad de la información y lo que falta.

### 5.2 Huella documental

> **Qué debe contener.** Igual que el apartado anterior, para los metadatos.

### 5.3 Ficha del objetivo actualizada

> **Qué debe contener.** Qué datos de la A03 confirman, añaden o contradicen Shodan y FOCA.

| Campo | Dato en la A03 | Cambio en la A04 | Referencia |
|---|---|---|---|
| | | | |

### 5.4 Grafo final

> **Qué debe contener.** La imagen del grafo de Maltego ampliado, enlazada desde `evidencias/`, y una leyenda de las relaciones nuevas, observadas, declaradas o pendientes, cada una con su referencia.

| Relación | Tipo | Referencia |
|---|---|---|
| | | |

### 5.5 Valoración de hallazgos clave

| Hallazgo | Referencias | Fiabilidad de la fuente | Credibilidad de la información | Hecho o inferencia | Contraste independiente |
|---|---|---|---|---|---|
| | | | | | |

---

## 6. Perspectiva del atacante y recomendaciones

> **Qué debe contener.** Al menos cinco filas, cada una a partir de un hallazgo propio; al menos tres salen de Shodan o FOCA. Describe el riesgo sin instrucciones operativas. Termina con lo que estas recomendaciones **no** cubren.

| Información visible | Referencia | Cómo podría aprovecharla un atacante | A qué afectaría | Medida defensiva | Prioridad |
|---|---|---|---|---|---|
| | | | | | |

**Qué no cubren estas recomendaciones:**

---

## 7. Limitaciones, datos descartados e incidencias

> **Qué debe contener.** Preguntas que no has podido responder y por qué. Datos que has descartado por quedar fuera del alcance. Restricciones de la cuenta de Shodan o problemas de FOCA. Incidencias, solo con su categoría y su fila `OBT`, e indicación de si avisaste por el canal privado. Si no hubo incidencias, escríbelo.

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

- [ ] Trabajo sobre el mismo objetivo y la misma modalidad que en la A03.
- [ ] Cerré los apartados 2 y 3 antes de la obtención: *commit* en la modalidad A, fecha de cierre en la modalidad B.
- [ ] Cada afirmación lleva su referencia `OBT` y la he comprobado.
- [ ] Las capturas están recortadas y anonimizadas, con las IP ocultas.
- [ ] Entrego antes del viernes 6 de noviembre a las 23:59.
- [ ] Modalidad A: solo he modificado `entregas/apellidoNombre/A04/`. Modalidad B: nada está en el repositorio del curso.
