# Soluciones · Parte grupal · Operación Pantalla Azul

*Soluciones orientativas con la puntuación de cada sección*

## Cronología en GMT+1

| Hora | Hecho |
|---|---|
| 08:30 | Se distribuye la actualización (F4-1) |
| 09:10 | Primeros fallos (F4-2) |
| 10:55 | Registro de escudo360-fix.example (F2-R2) |
| 10:58 | Registro de escudo360-soporte.example (F2-R3) |
| 11:00 | Publicación F1-S1 |
| 11:02 | Emisión del certificado F3-C1 |
| 11:05 | Reenvío del enlace por el chat interno (F4-3) |
| 11:10 | Publicación F1-S2 |
| 11:30 | Dos empleados ejecutan la herramienta (F4-4) |
| 11:40 | urlscan.io analiza la web (F3-U1) |
| 11:45 | Aviso de Sistemas (F4-5) |
| 12:10 | Llamada de la supuesta periodista |
| 12:40 | Aviso oficial del fabricante (F1-S3) |

Trampa: si no se convierten las horas, parece que el aviso oficial llegó 10 minutos después de que se ejecutara la herramienta. En realidad llegó 70 minutos después. Los dominios se registraron casi dos horas después de los primeros fallos, lo que indica una campaña oportunista.

## Sección 1 · Tema 3 (0,5)

- **Valoración:** la herramienta no es oficial, con confianza alta.
- **Evidencias:**
  - F1-S3: fuente primaria del fabricante.
  - F2-R2 y F2-R3: dominios creados ese mismo día.
  - F3-U1: la web pide donaciones.
- **Dependencias:** F1-S2 depende de F1-S1. La insignia azul es de suscripción, no de verificación.
- **Limitación:** no se sabe qué hace la herramienta ni quién está detrás.

## Sección 2 · Tema 4 (0,5)

- **IP compartida:** relación débil, porque la comparten 2.300 nombres de host.
- **Certificado:** relación más fuerte, porque quien lo solicitó controlaba los tres nombres. escudo360-ayuda.example es probablemente parte de la misma campaña.
- **Lo que no permite afirmar:** la autoría.
- **Indicadores que se bloquean:** los tres dominios. La IP, solo con reservas.
- **Acción interna más urgente:** aislar y revisar los dos equipos que ejecutaron la herramienta, y sus credenciales y sesiones. La hace Sistemas.

## Sección 3 · Tema 2 (0,5)

| Propuesta | Decisión | Motivo |
|---|---|---|
| F5-A | No | Riesgo de seguridad; si hay que analizarla, lo hace un equipo autorizado en un entorno controlado |
| F5-B | Dominios sí; titular no | El nombre del titular es un dato personal (N-02) y hay riesgo de señalar a quien no es (N-20) |
| F5-C | Sí | — |
| F5-D | No | Engaño (N-19) |
| F5-E | Sí | También se puede notificar a INCIBE-CERT (N-23) |

- **TLP para F5-C:** TLP:GREEN, por ser una comunidad sectorial. Se acepta AMBER si se justifica.
- **Llamada de la periodista:** puede ser ingeniería social. No se facilitan datos y se deriva la llamada al departamento de comunicación, aplicando la necesidad de conocer.

## Ajustes

- Por cada ficha que no se cite se restan 0,25 puntos.
- Si un miembro no participa, puede restársele hasta 0,5 puntos de forma individual.
