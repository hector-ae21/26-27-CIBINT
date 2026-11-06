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
| --- | --- | --- | --- |
| Nombre legal | AIR EUROPA LINEAS AEREAS S.A. | (A03 OBT-03) | Referencia general |
| Marcas | Air Europa, SUMA | (A03 OBT-01) | FOCA (metadatos de autoría) |
| Dominios oficiales | `aireuropa.com`, `agencias.aireuropa.com` | (A03 OBT-01, OBT-05) | Shodan y FOCA |
| Canales de contacto | `delegadopd@aireuropa.com` | (A03 OBT-04) | FOCA (búsqueda de correos) |

### 2.2 Requerimiento

| Componente | Contenido |
| --- | --- |
| Destinatario | Responsable de seguridad de la información (CISO) de Air Europa. |
| Decisión | Identificar qué servicios web/correo y metadatos documentales exponen información útil para un atacante, para aplicar medidas de bastionado y sanitización. |
| Objeto | Huella técnica (servicios web y correo expuestos vinculados a dominios) y huella documental (metadatos en documentos ofimáticos publicados). |
| Horizonte | Corto plazo (cierre de ejercicio 2026), orientado a subsanar vulnerabilidades operativas rápidas. |
| Alcance | Dominios principales de Air Europa, limitando el descubrimiento de servicios estrictamente a consultas por certificado y *hostname* (sector transporte). Documentos PDF indexados en el dominio principal. |
| Exclusiones | Análisis de vulnerabilidades específicas, comprobaciones activas (escaneos de red), consultas `org:` o `net:` en Shodan, e investigación de personas físicas. |
| Producto | Informe técnico de exposición estructurado con evidencias anonimizadas y recomendaciones defensivas. |

### 2.3 Preguntas de inteligencia

| Prioridad | Pregunta | Huella que cubre | Te ayuda a decidir |
| ---: | --- | --- | --- |
| 1 | ¿Qué servicios web o de correo vinculados a los dominios corporativos se observan desde Internet y quién los provee? | Técnica | Evaluar la dependencia de terceros y la superficie expuesta web/correo para bastionado. |
| 2 | ¿Qué metadatos internos (nomenclatura de usuarios, rutas, versiones de software) revelan los documentos públicos? | Documental | Implementar procesos de sanitización documental antes de la publicación web. |
| 3 | ¿Cómo se relaciona la infraestructura técnica observada con los portales identificados en la A03? | Técnica y Relaciones | Comprender la arquitectura externa para delimitar el alcance de posibles incidentes de terceros. |

---

## 3\. Plan de obtención

### 3.1 Consultas y documentos previstos

| Pregunta | Herramienta | Consulta, filtro o criterio | Fuente de contraste | Qué expone y a quién | Resultado esperado |
| --- | --- | --- | --- | --- | --- |
| PI-01 | Shodan | `hostname:aireuropa.com` | DNS Lookup / crt.sh | El *hostname* a la API de Shodan. No toca al objetivo. | Servicios web/correo bajo el dominio. |
| PI-01 | Shodan | `ssl.cert.subject.cn:"*.aireuropa.com"` | Censys | El CN a Shodan. No toca al objetivo. | Proveedores y certificados emitidos para la empresa. |
| PI-02 | FOCA | `site:aireuropa.com filetype:pdf` | Búsqueda manual de Google | Envía peticiones a Google y descarga archivos públicos web. | Hasta 30 PDFs con metadatos internos expuestos. |
| PI-03 | Maltego | Importación de dominios y resoluciones DNS básicas. | DNS manual | Envía el dominio a servidores DNS públicos. | Grafo vinculando la entidad jurídica, sus subdominios y la IP/ASN. |

### 3.2 Configuración y seguridad de la operación

La obtención se realiza en una máquina virtual de análisis aislada. Se utiliza una cuenta gratuita de Shodan registrada con el alias de investigación (sin vinculación personal). FOCA se ejecuta sobre Windows 10 con SQL Server Express local.

- **Configuración de FOCA:** Proyecto restringido al dominio `aireuropa.com`. Búsqueda web habilitada exclusivamente para extensiones `.pdf` mediante el motor de Google. Límite máximo establecido en 30 documentos. Las funciones de resolución DNS, escaneo de puertos y descubrimiento de red están *desactivadas* por normativa de la asignatura y prohibición de escaneo activo.

- **Gestión post-obtención:** Al terminar, los documentos PDF descargados, el proyecto FOCA local y la base de datos SQL se eliminarán de forma segura. Nada se subirá al repositorio público.

**Nota Modalidad A:** Este apartado y el anterior se completaron y consolidaron en un *commit* previo al inicio de la fase de obtención.

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
