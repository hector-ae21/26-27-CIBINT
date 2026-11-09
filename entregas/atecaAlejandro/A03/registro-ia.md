# Registro de uso de inteligencia artificial · A03

## Uso 1

- **Herramienta y modelo:** Google Gemini (Gemini Flash 3.8)
- **Para qué:** Consultar el funcionamiento combinado de los operadores `site:`, `filetype:` y el operador de exclusión (`-`) en Google Search, así como las limitaciones técnicas del recuento de resultados que ofrece el buscador.
- **Apartado del informe:** Apartado 3.1 (Herramientas por pregunta), Apartado 4.2 (Resultados por herramienta) y Apartado 5.4 (Valoración de hallazgos clave).
- **Prompt, copiado tal cual:**

  ```text
  Explícame de forma breve cómo funciona la combinación de los operadores site:, filetype: y el operador de exclusión (-) en Google Search, y qué limitaciones tiene el recuento de resultados que muestra el buscador en investigaciones OSINT.
  ```

- **Qué hice con la respuesta:** Utilicé la explicación sobre la lógica booleana implícita y la sintaxis del guion sin espacio (`-site:`) para estructurar mis consultas con operadores en Google (`OBT-02`, `OBT-03`, `OBT-04`). Además, incorporé las limitaciones técnicas explicadas por el modelo (estimación heurística no exacta, corte de paginación a los ~300-400 resultados y deduplicación algorítmica) para documentar los límites de Google en el apartado 4.2 y calificar el volumen de PDFs en el hallazgo `H-03` como una estimación sujeta a truncamiento, no como un conteo forense exacto.
- **Evidencia:** `ia/uso-01.png`

## Uso 2

- **Herramienta y modelo:** Google Gemini (Gemini Flash 3.8)
- **Para qué:** Aclarar la distinción metodológica entre fiabilidad de la fuente (A-F) y credibilidad de la información (1-6), y entender por qué dos agregadores que extraen datos del mismo boletín oficial no constituyen confirmación independiente.
- **Apartado del informe:** Apartado 5.2 (Huella por dimensiones) y Apartado 5.4 (Valoración de hallazgos clave).
- **Prompt, copiado tal cual:**

  ```text
  En metodología OSINT, ¿cuál es la diferencia entre fiabilidad de la fuente y credibilidad de la información? Pon un ejemplo de por qué dos registros web que toman datos del mismo boletín oficial no cuentan como confirmación independiente.
  ```

- **Qué hice con la respuesta:** Apliqué el criterio de separación entre origen (fuente) y contenido (información), y tuve en cuenta el concepto de dependencia de nodo único (*Circular Reporting*). Gracias a ello, en los apartados 5.2 y 5.4 evité tratar la coincidencia entre OpenCorporates (`OBT-07`) y el BORME (`OBT-08`) como una confirmación independiente (dado que OpenCorporates toma sus datos del propio BORME), valorando la credibilidad en nivel `2` (*Probablemente verdadera*) cuando no existía una fuente primaria desacoplada adicional.
- **Evidencia:** `ia/uso-02.png`

## Uso 3

- **Herramienta y modelo:** Google Gemini (Gemini Flash 3.8)
- **Para qué:** Obtener ideas generales sobre controles técnicos y de procedimiento estándar frente a la fuga de metadatos en documentos ofimáticos y la suplantación mediante dominios parecidos (*typosquatting*).
- **Apartado del informe:** Apartado 6 (Perspectiva del atacante).
- **Prompt, copiado tal cual:**

  ```text
  ¿Qué medidas defensivas técnicas y de procedimiento se recomiendan de forma general en una organización para evitar la exposición accidental de metadatos en documentos públicos y prevenir la suplantación de identidad (phishing) mediante dominios parecidos?
  ```

- **Qué hice con la respuesta:** A partir del catálogo general de controles defensivos devuelto por el modelo (sin haberle introducido ningún dato ni hallazgo de mi objetivo), seleccioné las medidas más adecuadas para mis filas del apartado 6: la higienización automatizada de metadatos en el ciclo de publicación del CMS (`exiftool`/`pdfcpu`) junto con el protocolo de doble control previo a la subida de archivos (descartando el uso de `robots.txt` por no ser un control de acceso válido en documentos de transparencia), la monitorización de registros *Certificate Transparency* (CT) / `dnstwist` frente a dominios similares, y la validación fuera de banda (*Out-of-band*) para cambios en datos de facturación de adjudicatarios.
- **Evidencia:** `ia/uso-03.png`