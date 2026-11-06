# A04 · Exposición técnica y documental

## Estudiante

- Nombre: Sergio Rodríguez López  
- Carpeta personal: entregas/rodriguezSergio/A04/  
- Modalidad: Modalidad A · Organización  
- Objetivo: Air Europa (Globalia)  
- Entrega de la A03 (enlace al *pull request* o «entregada en el Campus Virtual»): entregada en el Campus Virtual  
- Periodo de obtención, con zona horaria: Del 02/11/2026 al 03/11/2026 (Europe/Madrid)

---

## 1\. Resumen ejecutivo

> **Qué debe contener.** Se escribe al final. Como máximo 300 palabras. Un párrafo que el destinatario pueda leer sin el resto del informe, con las conclusiones de la A03 que cambian, y una tabla que responda cada pregunta del apartado 2.3 con su nivel de confianza y sus referencias.

| Pregunta | Respuesta breve | Confianza | Referencias |
| :---- | :---- | :---- | :---- |
|  |  |  |  |

---

## 2\. Punto de partida

### 2.1 Ficha del objetivo de la A03

| Campo | Dato | Referencia | Entrada para |
| :---- | :---- | :---- | :---- |
| Nombre legal | AIR EUROPA LINEAS AEREAS S.A. | (A03 OBT-03) | Shodan (org) |
| Dominios oficiales | `aireuropa.com` | (A03 OBT-01) | Shodan (hostname, ssl) y FOCA |
| Canales de contacto | `delegadopd@aireuropa.com` | (A03 OBT-04) | Validación cruzada |

### 2.2 Requerimiento

| Componente | Contenido |
| :---- | :---- |
| Destinatario | Responsable de seguridad de la información (CISO) de Air Europa. |
| Decisión | Determinar qué infraestructura subyacente y metadatos documentales son visibles públicamente y deben ser protegidos o sanitizados. |
| Objeto | Huella técnica y documental de Air Europa. |
| Horizonte | Corto plazo, informe de noviembre de 2026\. |
| Alcance | Servicios asociados a los dominios corporativos (`aireuropa.com`) y documentos ofimáticos indexados en dicho dominio. |
| Exclusiones | Escaneos activos, pruebas de vulnerabilidad, análisis de infraestructura sanitaria/transporte crítica (restricción estricta de Shodan). |
| Producto | Informe técnico con registro de obtención, evidencias anonimizadas y recomendaciones defensivas. |

### 2.3 Preguntas de inteligencia

| Prioridad | Pregunta | Huella que cubre | Te ayuda a decidir |
| ----: | :---- | :---- | :---- |
| 1 | PI-04: ¿Qué servicios web y de correo asociados al dominio principal se observan desde Internet y en qué proveedores se alojan? | Técnica | Identificar si la infraestructura está alojada internamente o externalizada, para ajustar el perímetro de monitorización. |
| 2 | PI-05: ¿Qué metadatos (usuarios, rutas, software) revelan los documentos públicos del dominio corporativo? | Documental | Determinar la necesidad de implementar una pasarela de sanitización de documentos antes de su publicación. |
| 3 | PI-06: ¿Las observaciones técnicas y documentales coinciden con las medidas de seguridad y modernización esperadas de la aerolínea? | Técnica y Documental | Evaluar la higiene digital de los procesos de publicación corporativa. |

---

## 3\. Plan de obtención

### 3.1 Consultas y documentos previstos

| Pregunta | Herramienta | Consulta, filtro o criterio | Fuente de contraste | Qué expone y a quién | Resultado esperado |
| :---- | :---- | :---- | :---- | :---- | :---- |
| PI-04 | Shodan | `hostname:"aireuropa.com"` | DNS / crt.sh | La consulta a la base de datos de Shodan, sin contactar a Air Europa. | Banners web y certificados asociados al dominio. |
| PI-04 | Shodan | `ssl.cert.subject.cn:"aireuropa.com"` | DNS / crt.sh | La consulta a Shodan. | Identificación precisa de certificados emitidos al dominio. |
| PI-05, PI-06 | FOCA | Descarga selectiva de 15 PDFs indexados (vía Google `site:aireuropa.com filetype:pdf`). | Google / Análisis local ExifTool | Búsquedas a Google y descargas web estándar; no interacciona con infraestructura interna. | Extracción de metadatos (software, usuarios, rutas). |
| PI-04, PI-05 | Maltego | Ampliación manual del grafo de la A03. | Resultados propios | Consulta local y a proveedores OSINT autorizados. | Mapa actualizado con infraestructura técnica y documental. |

### 3.2 Configuración y seguridad de la operación

**Cuenta de Shodan:** Cuenta gratuita de investigación académica (sin privilegios de escaneo on-demand ni Shodan Images). Solo lectura. **Instalación de FOCA:** Proyecto configurado en entorno local aislado. Dominio principal: `aireuropa.com`. Buscador configurado: Google y Bing. Límite: 20 documentos PDF. Funciones excluidas: No se usarán `Network`, `Domains` ni ningún `Plugin` de reconocimiento de red para cumplir estrictamente las normas del sector sensible. Al terminar la obtención, el proyecto de FOCA y los PDFs descargados serán eliminados permanentemente del almacenamiento local.

---

## 4\. Obtención

### 4.1 Registro de obtención

> **Qué debe contener.** Una fila por consulta o acción, incluidos los errores, los resultados vacíos y las restricciones. Fecha y hora en formato `AAAA-MM-DD HH:MM`, con la zona horaria indicada en la cabecera.

| ID | Herramienta | Consulta o acción exacta | Fecha y hora | Resultado | Límite | Evidencia |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| OBT-01 |  |  |  |  |  |  |

### 4.2 Shodan

> **Qué debe contener.** Las consultas con su número de resultados y lo que muestran sus facetas. Las fichas abiertas. Una tabla agregada de servicios clasificados en los tres grupos, con la fuente de contraste de cada atribución. Sin vulnerabilidades asociadas a servicios concretos.

| Consulta | Resultados | Facetas relevantes | Referencia |
| :---- | ----: | :---- | :---- |
|  |  |  |  |

| Grupo | Servicios o puertos observados | Fechas de observación | Cómo se ha contrastado | Referencias |
| :---- | :---- | :---- | :---- | :---- |
| Del objetivo |  |  |  |  |
| De un proveedor |  |  |  |  |
| Relación no demostrada |  |  |  |  |

### 4.3 FOCA

> **Qué debe contener.** Proyecto y configuración. Documentos localizados y analizados, por tipo. Criterio de selección. Resumen por categorías con recuentos, patrones e interpretación. En la modalidad A, nunca con valores personales: por ejemplo, «formato nombre.apellido (USR-01 a USR-06)». Si usaste el procedimiento alternativo, por qué.

| Tipo de documento | Localizados | Analizados | Intervalo de fechas |
| :---- | ----: | ----: | :---- |
|  |  |  |  |

| Categoría | Elementos | Patrón observado | Interpretación y límite | Referencia |
| :---- | ----: | :---- | :---- | :---- |
| Usuarios |  |  |  |  |
| Carpetas y rutas |  |  |  |  |
| Impresoras |  |  |  |  |
| Software |  |  |  |  |
| Correos |  |  |  |  |
| Sistemas operativos |  |  |  |  |
| Servidores |  |  |  |  |

### 4.4 Revisión de la elección

| Pregunta | Prevista | Utilizada | Evidencia obtenida | ¿Resuelve la pregunta? | Cambio justificado |
| :---- | :---- | :---- | :---- | :---- | :---- |
|  |  |  |  |  |  |

---

## 5\. Análisis e integración con la A03

### 5.1 Huella técnica

> **Qué debe contener.** Dos partes separadas: **Observado**, con referencias, y **Valoración**, con fiabilidad de la fuente, credibilidad de la información y lo que falta.

### 5.2 Huella documental

> **Qué debe contener.** Igual que el apartado anterior, para los metadatos.

### 5.3 Ficha del objetivo actualizada

> **Qué debe contener.** Qué datos de la A03 confirman, añaden o contradicen Shodan y FOCA.

| Campo | Dato en la A03 | Cambio en la A04 | Referencia |
| :---- | :---- | :---- | :---- |
|  |  |  |  |

### 5.4 Grafo final

> **Qué debe contener.** La imagen del grafo de Maltego ampliado, enlazada desde `evidencias/`, y una leyenda de las relaciones nuevas, observadas, declaradas o pendientes, cada una con su referencia.

| Relación | Tipo | Referencia |
| :---- | :---- | :---- |
|  |  |  |

### 5.5 Valoración de hallazgos clave

| Hallazgo | Referencias | Fiabilidad de la fuente | Credibilidad de la información | Hecho o inferencia | Contraste independiente |
| :---- | :---- | :---- | :---- | :---- | :---- |
|  |  |  |  |  |  |

---

## 6\. Perspectiva del atacante y recomendaciones

> **Qué debe contener.** Al menos cinco filas, cada una a partir de un hallazgo propio; al menos tres salen de Shodan o FOCA. Describe el riesgo sin instrucciones operativas. Termina con lo que estas recomendaciones **no** cubren.

| Información visible | Referencia | Cómo podría aprovecharla un atacante | A qué afectaría | Medida defensiva | Prioridad |
| :---- | :---- | :---- | :---- | :---- | :---- |
|  |  |  |  |  |  |

**Qué no cubren estas recomendaciones:**

---

## 7\. Limitaciones, datos descartados e incidencias

> **Qué debe contener.** Preguntas que no has podido responder y por qué. Datos que has descartado por quedar fuera del alcance. Restricciones de la cuenta de Shodan o problemas de FOCA. Incidencias, solo con su categoría y su fila `OBT`, e indicación de si avisaste por el canal privado. Si no hubo incidencias, escríbelo.

---

## 8\. Índice de evidencias

| Evidencia | Qué muestra | Fila del registro | Qué se ha ocultado |
| :---- | :---- | :---- | :---- |
|  |  |  |  |

---

## 9\. Uso de inteligencia artificial

Ver [registro-ia.md](http://registro-ia.md).

---

## Comprobación

- [ ] Trabajo sobre el mismo objetivo y la misma modalidad que en la A03.  
- [ ] Cerré los apartados 2 y 3 antes de la obtención: *commit* en la modalidad A, fecha de cierre en la modalidad B.  
- [ ] Cada afirmación lleva su referencia `OBT` y la he comprobado.  
- [ ] Las capturas están recortadas y anonimizadas, con las IP ocultas.  
- [ ] Entrego antes del viernes 6 de noviembre a las 23:59.  
- [ ] Modalidad A: solo he modificado `entregas/apellidoNombre/A04/`. Modalidad B: nada está en el repositorio del curso.
