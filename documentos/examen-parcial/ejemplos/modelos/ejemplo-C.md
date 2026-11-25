# Examen de práctica C · Revisa el informe

*CIBINT 2026-2027 · Material de preparación del parcial · Formato: revisión de un producto con errores*

**Este examen es de práctica.** Aquí no investigas desde cero. Te toca **revisar** el trabajo de otra persona: un informe con errores de método, legales, de fuentes y técnicos. Su estructura **no** coincide con la del examen real. Duración orientativa: **60 minutos**. Los temas pesan igual que en el parcial: T1 1 p · T2 2 p · T3 4 p · T4 3 p.

## El caso

**Caso real · FACC (Austria, 2016).** El fabricante aeronáutico austriaco FACC informó en enero de 2016 de que había perdido unos **50 millones de euros** en un fraude de suplantación de directivos, el llamado «fraude del CEO»: unos delincuentes se hicieron pasar por la dirección y ordenaron transferencias. Después, la empresa destituyó a su directora financiera y, meses más tarde, a su consejero delegado. *Fuentes: comunicados de FACC AG; Reuters, 2016.*

**Aerotec Moncayo, S.A.** es un fabricante ficticio de componentes aeronáuticos de Tarazona. El **viernes 13/11/2026**, la responsable de tesorería recibió este correo:

**De:** «Ignacio Lasheras, CEO» `<i.lasheras@aerotec-moncayo.example>`
«Estamos cerrando una adquisición confidencial. Necesito que hoy mismo hagas una transferencia de 480.000 € a la cuenta del despacho que nos asesora. No lo comentes con nadie: hay obligaciones de confidencialidad con la CNMV. Te llamará el abogado.»

El dominio legítimo de la empresa es `aerotecmoncayo.example`. La transferencia **no** llegó a hacerse.

## El informe del analista en prácticas (para revisar)

**INFORME DE INTELIGENCIA · URGENTE**
1. He investigado todo lo que hay en internet sobre el ataque y sobre el CEO para saber quién nos ataca.
2. El dominio `aerotec-moncayo.example` fue creado por una banda rusa, porque el titular está oculto.
3. He encontrado en un foro el perfil de un tal «I. Lasheras» que vive en Málaga y he guardado sus fotos, su dirección y las de su familia por si nos sirven.
4. LinkedIn, X y un blog confirman que el CEO estaba cerrando una adquisición, así que la parte de la adquisición es verdad. *(Nota: el blog y X citan como fuente el mismo post de LinkedIn.)*
5. He llamado al teléfono que dio el «abogado» haciéndome pasar por la tesorera para ver qué decían.
6. La IP del dominio falso es `203.0.113.45`, y en ella hay 900 dominios más. Todos son de la banda y deben bloquearse.
7. El registro MX del dominio falso apunta a un proveedor de correo gratuito, lo que prueba que el correo salió de ahí.
8. En crt.sh aparece `aerotec-moncayo.example` con un certificado de hoy. También aparece `vpn.aerotecmoncayo.example`, de 2020. Eso significa que nuestra VPN está expuesta y que nos han atacado por ahí.
9. Recomendación: avisar a todo el mundo. He compartido el informe completo en el grupo de WhatsApp de directores financieros de Aragón.
10. Conclusión: es un ataque de la banda que robó a FACC.

## Preguntas

**C1 (T1 · 1,0).** Las frases 1 y 10 tienen problemas de método. ¿Cuáles son? Reescribe el requerimiento implícito en la frase 1 con sus componentes y corrige la frase 10.

**C2 (T2 · 2,0).** Identifica los problemas legales, éticos y de OPSEC de las frases 3, 5 y 9. Cita el anexo y propón la alternativa correcta para cada una. Asigna la etiqueta TLP con la que debería haberse compartido el informe y explica a quién.

**C3 (T3 · 4,0).**

a) ¿Qué falla en la frase 4? Explica la diferencia entre la fiabilidad de una fuente y la credibilidad de una afirmación, y entre repetición e independencia. (1,0)

b) ¿Qué relación hay entre el «I. Lasheras» de la frase 3 y el CEO? ¿Qué debería haberse hecho? (0,8)

c) ¿Qué aprovechó el atacante de la información pública de Aerotec, desde su lado? Propón **tres medidas** de la empresa contra este tipo de fraude. (1,2)

d) Redacta la nota correcta para la dirección en 8 líneas como máximo, con valoración, confianza, evidencias, limitaciones y recomendaciones. (1,0)

**C4 (T4 · 3,0).** Corrige las frases 2, 6, 7 y 8 (0,6 cada una). Después indica qué **fuente** consultarías para solicitar la retirada del dominio falso y qué información incluirías en la solicitud (0,6).
