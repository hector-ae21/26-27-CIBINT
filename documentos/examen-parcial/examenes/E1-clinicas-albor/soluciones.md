# Soluciones · Modelo E1 · Clínicas Albor

*Soluciones orientativas con la puntuación de cada apartado*

## Trampas del modelo

- Las horas de ALB-S01 y ALB-S04 están en UTC; las de ALB-S02 y ALB-S03, en GMT+1.
- ALB-P03 es una homónima. ALB-P04 reutiliza contenido real, pero eso no basta para relacionarla con la campaña: es «no determinable».
- ALB-S02 y ALB-S03 parecen confirmaciones, pero dependen de ALB-S01.
- El titular suprimido aparece en los dos dominios, incluido el legítimo.
- La IP de SH-3 es compartida por 312 nombres.
- SH-1 se llama «Acceso remoto», pero es un servicio previsto: su nombre no lo convierte en prioritario.

## Bloque 1 · Tema 3 (3,5)

**1.1 (0,8).**

| Perfil | Relación | Evidencia |
|---|---|---|
| ALB-P01 | No confirmada | No está enlazado desde ALB-F01; alta en 10/2026; dos cambios de nombre de usuario; enlaza al dominio de la campaña |
| ALB-P02 | Confirmada | Enlazado desde ALB-F01 |
| ALB-P03 | No relacionada | Homónima: otra profesión y otra ciudad |
| ALB-P04 | No determinable | Cuenta reciente que reutiliza contenido; no hay ningún enlace que la relacione |

**1.2 (0,9).**

a) ALB-S01 y ALB-S04 son originales. ALB-S02 y ALB-S03 dependen de ALB-S01.

b) Ninguna fuente independiente: las otras dos publicaciones repiten ALB-S01, y ALB-S04, que es la fuente oficial, lo niega.

c) Orden en GMT+1:

1. ALB-S01: 02/11, 11:05.
2. ALB-S02: 03/11, 08:30.
3. ALB-S03: 03/11, 19:40.
4. ALB-S04: 04/11, 09:12.

d) Demuestra que la imagen existía en 2022 en un contexto legítimo, así que no se tomó para la campaña. No demuestra quién controla ALB-P01 ni que la doctora participe.

**1.3 (0,8).**

a) La sociedad existe desde el 12/10/2026, tres semanas antes de la campaña.

b) No acredita relación con Clínicas Albor, S.L. (ALB-R01 tiene otra fecha y otro domicilio), ni autoría, ni autorización.

c) Ejemplos de consultas:

- `"albor-citas.example"`: dónde circula el enlace.
- `"Albor Salud Digital"`: otras menciones de la sociedad.
- `site:clinicasalbor.example "fianza"`: si existe algún aviso oficial.
- `"Lucía Ferrer Gil" "Albor" -fisioterapeuta`: la relación profesional, excluyendo a la homónima.

**1.4 (1,0).**

a) Ejemplos de frases:

- **Hecho:** ALB-P01 no está enlazado desde ALB-F01.
- **Inferencia:** la campaña es probablemente ajena a Albor.
- **Limitación:** no se sabe quién controla ALB-P01.
- **Recomendación:** avisar a los pacientes por los canales oficiales y pedir la retirada del perfil y del dominio.

b) Datos públicos que aprovechó la campaña: el nombre y el cargo de la doctora en la web, su fotografía y la marca. Medidas posibles: aviso «nunca pedimos fianzas», publicación de los canales oficiales, denuncia ante la plataforma y vigilancia de dominios parecidos. No es válido investigar a la doctora.

## Bloque 2 · Tema 1 (1,0)

**2.1 a) (0,6).**

| Componente | Respuesta esperada |
|---|---|
| Destinatario | Comité de crisis |
| Decisión | Notificar, avisar a los pacientes y publicar un comunicado |
| Objeto | Las capturas difundidas en el canal |
| Horizonte | Antes de las 17:00 |
| Alcance | Incluido: vista pública del canal, registros e inventario. Excluido: descargas, interacción con el canal e identificación de personas |
| Producto | Nota de situación con nivel de confianza y limitaciones |

**2.1 b) (0,4).** Ejemplos de preguntas de inteligencia:

- ¿Hay indicios de que se esté contactando con pacientes? (En Vastaamo se extorsionó directamente a los pacientes.)
- ¿Desde cuándo pudo producirse el acceso y qué periodo cubren nuestros registros? (En Vastaamo, la brecha de 2018 se descubrió en 2020.)

## Bloque 3 · Tema 4 (2,5)

**3.1 (0,5).** a) Dentro. b) Fuera: contacta con la infraestructura del adversario. c) Dentro. d) Fuera: es una obtención activa. e) Dentro.

**3.2 (0,8).**

a) Se debe a la política de privacidad del registro y no indica malicia, porque el dominio legítimo también lo tiene. Lo relevante es la fecha de creación.

b) No: es un alojamiento compartido del proveedor.

c) Quien solicitó el certificado controlaba los cuatro nombres en esa fecha. Es una relación más fuerte que una IP compartida, pero sigue siendo una inferencia.

d) Solo permite afirmar que se pidió un certificado para ese nombre; no demuestra despliegue. Queda pendiente: preguntar a sistemas.

**3.3 (0,4).**

a) nginx con una aplicación PHP.

b) Puede haber un intermediario o cabeceras alteradas; no confirma versiones ni vulnerabilidades.

**3.4 (0,8).**

| Hallazgo | Prioridad | Siguiente paso |
|---|---|---|
| H1 | Verificación de cierre o alta para validación | Sistemas comprueba si sigue publicado |
| H2 | Pendiente | Sistemas lo contrasta con el inventario |
| H3 | Revisión ordinaria | Comparar con los controles previstos |
| H4 | Acción defensiva externa | Retirada, INCIBE-CERT y aviso a pacientes |

Se acepta como prioritario H1 o H4 si se justifica.

## Bloque 4 · Tema 2 (1,5)

**4.1 (1,0).**

| Acción | Decisión | Justificación |
|---|---|---|
| A1 | Realizar con condiciones | Sin descargas ni datos de pacientes; minimización (N-02) |
| A2 | No realizar | Categoría especial y datos de terceros (N-06, N-12); material no fiable. Hay que detenerse y consultar con la DPD |
| A3 | No realizar | Engaño (N-19) |
| A4 | No realizar | Minimización (N-02, N-06): se registra la existencia de los datos, no su contenido |
| A5 | Realizar | Fuente propia, obtenida por el canal contractual |

**4.2 (0,5).**

a) El plazo cuenta desde que se tiene constancia, es decir, desde esta mañana. N-08 permite notificar por fases.

b) La decisión corresponde al responsable del tratamiento, asesorado por la DPD. El analista aporta una valoración con nivel de confianza y limitaciones: no haber encontrado un acceso no equivale a que no haya habido violación.
