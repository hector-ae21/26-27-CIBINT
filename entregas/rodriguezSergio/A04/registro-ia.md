# Registro de uso de inteligencia artificial · A04

## Uso 1

- **Herramienta y modelo:** Gemini  

- **Para qué:** Entender la sintaxis de un filtro de Shodan.  

- **Apartado del informe:** 3.1 Consultas y documentos previstos / 4.2 Shodan.  

- **Prompt, copiado tal cual:**

```
¿Cómo puedo buscar en Shodan los certificados SSL que hayan sido emitidos exactamente para un dominio específico, sin que me salgan los que solo lo mencionan de pasada o como dominio alternativo?
```

- **Qué hice con la respuesta:** Leí la explicación sobre cómo el filtro `ssl.cert.subject.cn:` apunta exclusivamente al campo *Common Name* y descarta dominios alternativos (SAN) o menciones en texto plano. Con ello, implementé este filtro exacto en mi consulta `OBT-02` para obtener resultados precisos.  

- **Evidencia:** `ia/uso-01.png`

## Uso 2

- **Herramienta y modelo:** Gemini  

- **Para qué:** Aclarar conceptos técnicos sobre externalización de infraestructura (CDN/WAF).  

- **Apartado del informe:** 5.1 Huella técnica / 6\. Perspectiva del atacante.  

- **Prompt, copiado tal cual:**

```
En un análisis técnico, si veo que los puertos web de una empresa responden desde IPs que pertenecen a Akamai Technologies y a Incapsula, ¿qué significa esto a nivel de infraestructura? ¿Tiene la empresa servidores propios expuestos ahí?
```

- **Qué hice con la respuesta:** Comprendí que Akamai e Incapsula actúan como proxy inverso y WAF, ocultando la IP real (Origin Server) de la empresa. Esto me permitió valorar correctamente mis hallazgos en Shodan y concluir que la exposición directa de Air Europa está delegada y protegida.  

- **Evidencia:** `ia/uso-02.png`

## Uso 3

- **Herramienta y modelo:** Gemini  

- **Para qué:** Buscar ideas de medidas defensivas técnicas y organizativas para los metadatos.  

- **Apartado del informe:** 6\. Perspectiva del atacante y recomendaciones.  

- **Prompt, copiado tal cual:**

```
¿Qué medidas defensivas (a nivel organizativo o técnico) puede aplicar una empresa para evitar que se filtren los nombres de usuario de los empleados en los metadatos de los PDFs que publican en su web oficial?
```

- **Qué hice con la respuesta:** Revisé el catálogo de opciones que me dio (como higienización automática en el CMS, herramientas de limpieza *scrubbing* o forzar políticas por GPO). Seleccioné y adapté la idea de las pasarelas de sanitización DLP y la configuración del software ofimático para mi tabla de recomendaciones en el informe.  

- **Evidencia:** `ia/uso-03.png`
