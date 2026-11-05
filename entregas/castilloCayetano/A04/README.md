# A04 · Exposición técnica y documental

## Estudiante

- Nombre: Cayetano Castillo Ruiz
- Carpeta personal: entregas/castilloCayetano/A04/
- Modalidad: A
- Objetivo: Entidad Publica (Renfe)
- Entrega de la A03 (enlace al *pull request* o «entregada en el Campus Virtual»): https://github.com/hector-ae21/26-27-CIBINT/pull/27
- Periodo de obtención, con zona horaria: 04/11/2026 - 13:30 - UTC+1 (Madrid)

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
|Nombre legal matriz |Entidad Pública Empresarial Renfe-Operadora |A03 OBT-01 |Contexto corporativo e identificación de titularidad de activos. |
|Filial operativa principal |Renfe Viajeros, S.M.E., SA |A03 OBT-01 |Búsqueda en metadatos documentales de autoría jurídica. |
|Dominio principal |renfe.com |A03 OBT-02, A03 OBT-06 |Filtro base en Shodan (hostname:renfe.com, ssl:renfe.com) y proyecto FOCA. |
|Subdominios oficiales identificados |grupo.renfe.com, blog.renfe.com, renfeviajes.renfe.com, empleo.renfe.com |A03 OBT-02, A03 OBT-04 |Dorking documental en FOCA y consultas específicas hostname: en Shodan. |
|Infraestructura de terceros observada |Cloudflare Inc. (CDN/DNS) |A03 OBT-06 |Identificación de proveedores en resultados de Shodan para discernir activos directos vs proxies. |


### 2.2 Requerimiento

| Componente | Contenido |
|---|---|
| Destinatario |Responsable de Seguridad de la Información (CISO / Dirección de Ciberseguridad) de Renfe. |
| Decisión |Evaluar la superficie técnica expuesta hacia Internet (servicios de red y certificados) y la fuga de información involuntaria en documentos públicos para definir directivas de endurecimiento (hardening), políticas de borrado de metadatos y mitigación de vectores de reconocimiento. |
| Objeto |La exposición técnica de servicios perimetrales y los metadatos de ficheros publicados por Renfe accesibles pasivamente desde fuentes abiertas. |
| Horizonte |Estado técnico actual en índices pasivos y recopilación histórica de documentos publicados disponibles. |
| Alcance |Dominios corporativos del grupo (renfe.com y subdominios asociados) y ficheros ofimáticos/PDFs alojados públicamente en sus portales. |
| Exclusiones |Escaneos de puertos directos o activos sobre la red de Renfe; uso de filtros invasivos o búsqueda de sistemas industriales/internos; análisis de vulnerabilidades sobre IPs concretas; investigación o difusión de nombres personales hallados en metadatos. |
| Producto |Informe técnico A04 de exposición técnica y documental con registro de consultas, categorización de metadatos anonimizada, grafo de relaciones integrado en Maltego y medidas preventivas. |

### 2.3 Preguntas de inteligencia

| Prioridad | Pregunta | Huella que cubre | Te ayuda a decidir |
|---:|---|---|---|
|1 |¿Qué servicios y puertos asociados a los dominios de Renfe son visibles desde índices de escaneo pasivo y cuáles dependen de intermediarios/CDNs frente a infraestructura propia? |Técnica (Shodan / Censys) |Si existen activos o servicios expuestos que eluden el perímetro de protección (CDN/WAF) o si la superficie visible está adecuadamente intermediada. |
|2 |¿Qué información sobre estructura interna, software ofimático, servidores de red e impresoras revelan los metadatos de los documentos publicados por la entidad? |Documental (FOCA) |Qué políticas técnicas de ofuscación o herramientas de limpieza de metadatos (sanitization) deben imponerse en los flujos de publicación externa. |
|3 |¿Qué nombres de usuarios de red, cuentas de correo o formatos de nomenclatura interna quedan expuestos en los ficheros descargables de libre acceso? |Documental / Relaciones |Dónde reforzar las medidas contra ataques de ingeniería social dirigida, spear phishing o ataques de fuerza bruta basados en nombres de usuario reales. |

---

## 3. Plan de obtención

### 3.1 Consultas y documentos previstos

| Pregunta | Herramienta | Consulta, filtro o criterio | Fuente de contraste | Qué expone y a quién | Resultado esperado |
|---|---|---|---|---|---|
|P1 |Shodan |hostname:renfe.com |Censys / crt.sh |Envía la consulta a los servidores de Shodan. No contacta con Renfe. |Listado de servicios y puertos abiertos indexados pasivamente bajo el dominio corporativo. |
|P1 |Shodan |ssl:"renfe.com" |crt.sh |Consulta a los índices de certificados de Shodan. No toca al objetivo. |Detección de servidores web que presentan certificados emitidos para renfe.com o sus subdominios. |
|P1 |Shodan |ssl.cert.subject.cn:renfe.com |whois sobre ASN |Consulta pasiva de certificados con Common Name específico en Shodan. |Identificación de hosts que utilizan el certificado principal y verificación de la titularidad de su IP. |
|P2, P3 |FOCA |Descarga y análisis de entre 15 y 30 documentos PDF de renfe.com (obtenidos vía dorking de la A03). |Lectura manual de propiedades del documento |Peticiones HTTP estándar de descarga pública a portales web como visitante ordinario |Extracción de metadatos de autor, software de creación/conversión, rutas de almacenamiento y nombres de usuario. |
|P1 |crt.sh / Censys (Contraste) |Dominio renfe.com |Shodan |Consulta a bases de datos de transparencia de certificados (CT Logs). |Validación independiente de si una IP o certificado pertenece formalmente a Renfe o a un proveedor (ej. Cloudflare). |

### 3.2 Configuración y seguridad de la operación

**Cuenta de Shodan:** Uso de cuenta gratuita académica, sin vincular a perfiles personales y sin recurrir a opciones de escaneo bajo demanda (on-demand scan).

**Instalación y modo de FOCA:**

- Ejecución en máquina con Windows 64-bit y base de datos local.

- Modo de obtención: Análisis local de documentos previamente descargados o búsqueda pasiva vía motor Google, con límite fijado entre 15 y 30 documentos.

- Extensiones permitidas: Exclusivamente documentos ofimáticos (.pdf, .docx, .xlsx).

- Funciones estrictamente deshabilitadas: No se utilizarán los módulos de red (Network), resolución DNS forzada (Domains), plugins de enumeración ni rastreo activo de servidores.

**Carpeta de trabajo y minimización:**

- Los documentos analizados y la base de datos de FOCA residirán en un directorio local temporal (workspace_a04/temp_docs/), fuera del repositorio de Git.

- Todos los nombres de usuario extraídos en FOCA serán sustituidos en el informe por identificadores anónimos (USR-01, USR-02...).

- En todas las capturas de Shodan se ocultarán de forma opaca los dos últimos octetos de cualquier IP (XXX.XXX.XX.XX).

- Al concluir la práctica, los archivos PDF descargados y los proyectos temporales de FOCA serán eliminados de forma segura, conservando únicamente las capturas anonimizadas en evidencias/.

**Modalidad B · Fecha y hora de cierre del plan:**

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
