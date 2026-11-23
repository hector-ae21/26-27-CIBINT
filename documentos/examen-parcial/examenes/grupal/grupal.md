# Parte grupal · Operación Pantalla Azul

*Ciberinteligencia · 1,5 puntos · 30 minutos*

## Instrucciones

- **Funcionamiento:** cada persona lee su ficha durante tres minutos. Después, el equipo pone en común las cinco fichas, porque ninguna basta por sí sola, y completa una única hoja de respuesta.
- **Requisito:** cada ficha debe citarse al menos una vez en la hoja (por ejemplo, F2-R2). Por cada ficha que no se cite se restan 0,25 puntos.
- **Puntuación:** 1,5 puntos, la misma nota para todo el equipo: 0,5 del Tema 3 (sección 1), 0,5 del Tema 4 (sección 2) y 0,5 del Tema 2 (sección 3).

## Caso real de partida

El 19/07/2024, una actualización defectuosa del agente de seguridad de CrowdStrike para Windows provocó fallos en millones de equipos de todo el mundo. La agencia estadounidense CISA aclaró que no se trataba de un ciberataque, pero advirtió de que había actores maliciosos aprovechando el incidente para hacer phishing. El MS-ISAC informó de dominios parecidos que se hacían pasar por el soporte de la empresa. Un servicio de detección contabilizó más de 40 dominios de imitación en las primeras 24 horas, y algunas webs falsas de «reparación» pedían donaciones en bitcoin o PayPal. Fuentes: CISA (19/07/2024), TechCrunch (19/07/2024) y MS-ISAC.

## Situación del ejercicio

El lunes 16/11/2026, una actualización defectuosa del antivirus corporativo Escudo360 deja inutilizables decenas de equipos de Logística Meridiano, una empresa de transporte de Zaragoza con 400 empleados. Pocas horas después circulan mensajes que ofrecen una «herramienta oficial de reparación». La directora de operaciones necesita una nota de situación antes de las 13:00 GMT+1.

**Pregunta del requerimiento:** ¿Es oficial la herramienta de reparación que circula, qué riesgo supone para Meridiano y qué debe hacer la empresa ahora?

Las fichas incluyen horas en UTC (marca Z) y en GMT+1. Unifícalas antes de razonar sobre la secuencia de los hechos.

# Fichas individuales

Cada ficha se entrega a una sola persona.

## Ficha F1 · Publicaciones

| ID | Cuenta | Hora mostrada | Contenido |
|---|---|---|---|
| F1-S1 | X @Escudo360_Soporte, con insignia azul de suscripción, creada el 16/11/2026 | 10:00Z | «¿Pantalla azul tras la actualización? Descarga la herramienta oficial de reparación: escudo360-fix.example» |
| F1-S2 | LinkedIn, perfil de un «consultor IT» con 900 contactos | 11:10 GMT+1 | Comparte F1-S1: «Funciona, lo he probado en dos clientes». |
| F1-S3 | Web del fabricante, escudo360.example/estado | 11:40Z | «Hemos identificado una actualización defectuosa. No distribuimos herramientas por redes sociales. El procedimiento de recuperación está solo en nuestro portal de clientes.» |

## Ficha F2 · Registro y DNS

| ID | Dominio | Creado (RDAP) | Registrador | Titular |
|---|---|---|---|---|
| F2-R1 | escudo360.example | 2009 | Registrador Uno | Escudo360 Software, S.L. |
| F2-R2 | escudo360-fix.example | 16/11/2026 09:55Z | Registrador Cinco | Datos suprimidos |
| F2-R3 | escudo360-soporte.example | 16/11/2026 09:58Z | Registrador Cinco | Datos suprimidos |

| ID | Fuente | Dato |
|---|---|---|
| F2-D1 | DNS pasivo | escudo360-fix.example, registro A: 203.0.113.150 |
| F2-D2 | DNS pasivo | escudo360-soporte.example, registro A: 203.0.113.150 |
| F2-D3 | Shodan, ficha de 203.0.113.150 | Alojamiento compartido con 2.300 nombres de host de dominios diversos |

## Ficha F3 · Certificados y web

| ID | Fuente | Contenido |
|---|---|---|
| F3-C1 | crt.sh | Certificado emitido el 16/11/2026 a las 10:02Z con estos nombres: escudo360-fix.example, escudo360-soporte.example y escudo360-ayuda.example. |
| F3-U1 | Análisis ya existente en urlscan.io de escudo360-fix.example (16/11, 10:40Z) | Página «Herramienta de reparación Escudo360» con un botón de descarga, el logotipo del fabricante y el texto «Donación voluntaria para el equipo de soporte (PayPal o bitcoin)». |

## Ficha F4 · Lo que ocurre en Meridiano

Cronología interna del departamento de sistemas. Todas las horas están en GMT+1.

| ID | Hora | Hecho |
|---|---|---|
| F4-1 | 08:30 | Se distribuye automáticamente la actualización de Escudo360. |
| F4-2 | 09:10 | Primeros avisos de equipos con pantalla azul en el almacén y las oficinas. |
| F4-3 | 11:05 | Un empleado reenvía al chat general de la empresa el enlace de F1-S1. |
| F4-4 | 11:30 | Dos empleados de administración dicen en el chat que han descargado y ejecutado «la herramienta». |
| F4-5 | 11:45 | Sistemas pide por el chat que nadie descargue nada y recuerda que la recuperación la hace Sistemas. |

El contrato con el fabricante da acceso a su portal de clientes, donde están los procedimientos oficiales de recuperación.

## Ficha F5 · Propuestas de la dirección

| ID | Propuesta |
|---|---|
| F5-A | Descargar la herramienta en un portátil de la oficina «para ver qué hace». |
| F5-B | Publicar en el LinkedIn de la empresa los dominios falsos y, si se averigua, el nombre de quien los registró. |
| F5-C | Compartir los dominios y la IP con el grupo sectorial de seguridad de empresas logísticas, formado por 35 empresas. |
| F5-D | Llamar al teléfono de soporte de la web falsa haciéndose pasar por un cliente para averiguar quién hay detrás. |
| F5-E | Pedir a la plataforma X y al registrador la retirada de la cuenta y de los dominios, adjuntando las evidencias. |

A las 12:10 GMT+1, una supuesta periodista de un diario económico llama a la centralita. Pregunta cuántos equipos están afectados y si la empresa ha pagado algo a los atacantes.

# Hoja de respuesta del equipo

Una sola hoja por equipo.

## Sección 1 · ¿Es oficial la herramienta? (Tema 3 · 0,5 puntos)

**a) Valoración y grado de confianza. (0,15)**

&nbsp;

&nbsp;

**b) Evidencias que la sostienen, con sus identificadores. (0,15)**

&nbsp;

&nbsp;

**c) Publicaciones que dependen de otras. (0,1)**

&nbsp;

&nbsp;

**d) Una limitación. (0,1)**

&nbsp;

&nbsp;

## Sección 2 · Infraestructura y riesgo (Tema 4 · 0,5 puntos)

**a) Qué relación entre los dominios sostiene la IP compartida y cuál sostiene el certificado. (0,15)**

&nbsp;

&nbsp;

**b) Qué no permite afirmar ninguno de los dos. (0,05)**

&nbsp;

&nbsp;

**c) Indicadores que proponéis bloquear. (0,1)**

&nbsp;

&nbsp;

**d) Acción interna más urgente y quién debe hacerla. (0,2)**

&nbsp;

&nbsp;

## Sección 3 · Decisiones y difusión (Tema 2 · 0,5 puntos)

a) Decisión sobre cada propuesta de F5: sí, con condiciones o no. (0,05 por propuesta) (0,25)

| Propuesta | Decisión | Motivo y referencia del anexo |
|---|---|---|
| F5-A | | |
| F5-B | | |
| F5-C | | |
| F5-D | | |
| F5-E | | |

**b) Etiqueta TLP para F5-C y justificación. (0,1)**

&nbsp;

&nbsp;

**c) Respuesta a la llamada de la supuesta periodista. (0,15)**

&nbsp;

&nbsp;

## Firmas del equipo

| Ficha | Nombre y apellidos | Firma |
|---|---|---|
| F1 |  | |
| F2 |  | |
| F3 |  | |
| F4 |  | |
| F5 |  | |
