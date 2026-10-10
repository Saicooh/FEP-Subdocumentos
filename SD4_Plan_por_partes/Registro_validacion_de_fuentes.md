# Validación del plan SD4 — Informe 2

Se contrastaron los 303 IDs del plan con las cinco fuentes adjuntas: Bases Administrativas (BA), Bases Técnicas Transversales (BT), Caso 07 (CAS), instrucciones extras (EX) y revisión del Informe 1 (REV). El plan corregido mantiene sus 13 partes y excluye condiciones administrativas de entrega.

La validación comprueba respaldo documental y alcance del plan. No afirma que Synaptix ya ejecutó pruebas, obtuvo certificaciones o implementó la solución. Los requisitos contractuales futuros se traducen a diseño, compromiso y mecanismo de verificación; sus resultados se acreditan cuando corresponda.

## Resultado y criterio de clasificación

Se corrigieron **25 casillas**, además de aclarar el índice y la tabla de decisiones. Se mantienen **303 IDs únicos** para no romper el seguimiento previo. Ese número corresponde a instrucciones y controles de trabajo, no a 303 requisitos obligatorios independientes.

| Tipo | Significado | Casillas |
|---|---|---:|
| B | Exigencia explícita en BA, BT, CAS o EX; desarrollar con su alcance real. | 151 |
| R | Corrección pedida en REV; responderla sin atribuirla literalmente a las bases. | 30 |
| D | Desarrollo del requisito citado; método y detalle admiten equivalentes justificados. | 116 |
| C | Aplicación condicionada a la alternativa, compromiso o tecnología elegida. | 3 |
| G | Guía interna del agente, sin nuevo anexo/formulario exigido. | 3 |
| Total | IDs cubiertos individualmente. | 303 |

Una casilla B no convierte cada ejemplo técnico en una solución única. Las condiciones, «según caso», deseables y plazos se interpretan con el texto de origen y BA arts. 5–6. R conserva las correcciones de la quinta fuente; D no autoriza omitir el requisito que desarrolla. Los deseables que se ofrezcan pasan a formar parte del compromiso ofertado.

## Correcciones concretas

| ID | Ajuste realizado | Respaldo |
|---|---|---|
| L-08 | Se corrige la atribución: las cinco vistas las enumeran las bases. | BA art. 19; BT RT-02.03 |
| SEG-02 | Se limita la exigencia literal a componentes e integraciones externas y se evita imponer una plantilla. | BT RT-02.03 y RT-11.02 |
| SEG-07 | KMS y HSM son alternativas admitidas, no dos productos obligatorios. | BT RT-11.09 y RT-07.10 |
| OBS-07 | Se conserva el requisito tras verificar la exigencia superior de BA; se precisa su origen. | BA arts. 25 y 79; BT RT-14.06 y RT-09.09 |
| UX-06 | Se retira del SD4 el umbral específico del prototipo de Informe 3. | BT RT-13.09; BT §25.1 y RT-25.05 |
| UX-07 | Se limita el multiidioma al alcance expresamente fijado por el caso. | CAS cap. 15, RT-13.12 y RT-21.06 |
| SW-10 | Se conserva la necesidad de HA concreta; fencing queda condicionado al diseño. | BT RT-03.14; REV SD4.1, factibilidad cruzada |
| F-03 | Se elimina un número implícito de diagramas no fijado en las fuentes. | EX §§4 y 11, capítulo 4; CAS §17.4 |
| F-09 | Se corrige la descripción de los meses 13–15: Etapa 1 aún está en marcha blanca. | BA arts. 15 y 17 |
| RED-01 | Se elimina la obligación agregada de seis segmentos y gestión fuera de banda. | CAS cap. 15, RT-03.24; REV SD4.2, red operacional |
| CAP-01 | Se distingue demanda de medición de equipamiento existente. | CAS §14.1 |
| CAP-05 | Se elimina la equivalencia no exigida entre puntos de servicio y medidores. | CAS §§14.1, 14.2 y 16.1, decisión 3 |
| CAP-13 | Se sujeta el cálculo eléctrico y térmico a tipología y aplicabilidad. | BT §6.1 y RT-06.07/11/13; REV SD4.2 |
| CAP-19 | Se delimita el contenido de SD4 frente al desarrollo operativo de otros documentos. | CAS §14.2; BT RT-09.09 y RT-21.06/14 |
| VID-02 | Se elimina un piloto obligatorio de consumos que las fuentes no piden. | CAS §§10 y 17.5; REV SD4.1 |
| VID-07 | Se separan FinOps obligatorio y alternativas tecnológicas deseables. | BT RT-03.06/08/09; EX capítulo 4 |
| HW-04 | Se evita imponer un mecanismo de aislamiento único manteniendo la redundancia exigida. | BT RT-03.14 y RT-08.01/02; REV SD4.1/4.2 |
| HW-07 | Se restituye la libertad de diseño explícita del caso. | CAS §16.1, decisión 3; CAS §§15 y 18, criterio 18 |
| HW-08 | Se distingue la observación específica de REV de una obligación general de sensorización. | CAS §§16.1 y 17.4; REV SD4.1, Qué se espera |
| DC-02 | Se corrige la atribución geográfica conservando la solicitud expresa de la revisión. | BA arts. 5, 16 y 47; BT RT-03.01 y RT-07.02; REV SD4.2 |
| DC-05 | Se conserva la especificación/certificación solicitada sin inventar un mínimo numérico adicional. | BA T-7, ítem 4.2 |
| ADR-01 | Se retira la plantilla ampliada impuesta y se conservan mínimos y trazabilidad. | BT RT-02.04; CAS §17.1; REV SD4.1 |
| DOC-01 | Se elimina una cantidad implícita de figuras no establecida en las fuentes. | BT RT-02.01/03; CAS §17.4; EX §4 |
| DOC-05 | Se limita la sensibilidad a casos pertinentes y requisitos explícitos. | EX §3; CAS §14; BT RT-08.05 y RT-09.01 |
| FIN-13 | El registro del checklist se reconoce como guía de ejecución, no entregable adicional. | Guía del agente; BT §1.5 y BA art. 46 como controles formales ya existentes |

## Comprobaciones que evitaron eliminar obligaciones reales

- Presupuesto de error: BT RT-10.09 lo llama deseable, pero BA art. 25 lo exige. Se conserva por precedencia administrativa.
- OWASP SAMM: BT RT-11.28 es deseable, pero BA art. 4.3 lo exige para el proceso. Se conserva.
- Reducción/apagado de ambientes no productivos: BT RT-04.13 es deseable, pero BT RT-15.02 y BA art. 26 lo exigen. Se conserva.
- Cobertura ≥70 %, crecimiento ≥3× en tres años, pruebas a 1,5× peak, ocho capas y cinco ambientes: requisitos explícitos en BT/BA/EX, no agregados por el plan.
- Umbrales 24/12/8 h, sincronización ≤30 min y tiempos de procesos 45/10/90/60 s, emergencia ≤10 min y vencimiento ≤15 min: provienen del capítulo 15 del caso.
- T-11: el formulario original tiene seis campos. La referencia a cinco de REV no reemplaza el original.
- Costos unitarios: se conserva el detalle técnico solicitado por BT/REV, pero los montos quedan en la oferta económica conforme a BA art. 50.2 y EX §3.
- Secundaria en Chile/Sudamérica, AES-256 y sensor/piloto de DEC-01: se identifica la solicitud de REV y se distingue del alcance literal general de BA/BT/CAS.

## Contenidos que no se convierten en exigencias del SD4

La frase «añadir una indicación compacta de ponderación de Informe 2: 19 %, con ambos subtotales» **no estaba en los Markdown entregados**. La búsqueda se realizó sobre el checklist y las trece partes. T-21 p. 66/77 permite calcular 7 % + 12 % = 19 %, pero no exige escribir esa indicación en el cuerpo del SD4; no se incorpora.

No se exige entregar el prototipo interactivo ni su paleta de cinco colores en Informe 2; un número fijo de diagramas; seis redes como mínimo; gestión fuera de banda; dos productos KMS y HSM simultáneos; un sensor por amarra; exactamente 640 medidores; un piloto independiente de consumos; fencing para toda alternativa de HA; una plantilla ADR ampliada única; ni un nuevo registro formal de este checklist adjunto al SD4.

Se mantienen libertad tecnológica, aplicación proporcional del capítulo 6 a gabinetes, límites de responsabilidad/exclusiones del caso y ubicación de contenidos según EX. Los planes completos de otros subdocumentos no se duplican en SD4: se desarrollan sus decisiones arquitectónicas y referencias de coherencia.

## Trazabilidad individual de las 303 casillas

Cada referencia se contrastó con el apartado correspondiente. Para CAS, un código RT remite a la fila del capítulo 15 de ese documento; sus códigos homónimos en BT se leen por separado. Para REV, las secciones se identifican por subdocumento y tema.

| ID | Parte | Tipo | Fuente y ubicación |
|---|---:|---|---|
| R-01 | 01 | G | Cinco fuentes adjuntas; instrucción del usuario |
| R-02 | 01 | B | BA arts. 5/6; BT §1.4 |
| R-03 | 01 | D | CAS §17.1; REV SD4.1 |
| R-04 | 01 | G | EX §7.1; BT §1.5 |
| R-05 | 01 | B | EX §3; BA art. 57.2 |
| R-06 | 01 | B | BA art. 50.2; EX §3 |
| R-07 | 01 | B | BA art. 5.4; BT RT-08.10 |
| R-08 | 01 | R | BA T-11; REV SD4.2 |
| R-09 | 01 | R | REV General; EX §§3/7.1 |
| R-10 | 01 | B | BA T-22; REV SD4.1/4.2 |
| E-01 | 01 | B | EX §§2/11 |
| E-02 | 01 | B | EX §3 |
| E-03 | 01 | B | EX §§3/4; BA T-21 |
| E-04 | 01 | B | EX §2 |
| I-01 | 01 | D | BA T-7; EX capítulo 4 |
| I-02 | 01 | D | BA art. 16; CAS §§9.11/15 |
| I-03 | 01 | D | CAS §§6/10/17.4 |
| I-04 | 01 | D | EX §§2/11; BA art. 57.2 |
| I-05 | 01 | R | EX §§11, capítulos 3/4; REV SD4.1 |
| I-06 | 01 | R | BA art. 46; EX capítulo 4 |
| L-01 | 02 | B | BT §2.3 |
| L-02 | 02 | C | BT RT-02.02; REV SD4.1 |
| L-03 | 02 | B | BT §2.1 y RT-02.01 |
| L-04 | 02 | B | BT §2.1 |
| L-05 | 02 | D | EX capítulo 4; REV SD4.1 |
| L-06 | 02 | D | CAS §§9/17; EX capítulo 4 |
| L-07 | 02 | B | BT RT-02.13 |
| L-08 | 02 | B | BA art. 19; BT RT-02.03 |
| L-09 | 02 | B | BA arts. 4.3/71 |
| L-10 | 02 | D | BT §2.1; REV SD4.1 |
| L-11 | 02 | B | BT RT-02.05 |
| L-12 | 02 | B | CAS cap. 15, RT-02.12 |
| INT-01 | 02 | D | CAS §§15/17.4; REV SD4.1 |
| INT-02 | 02 | D | BT RT-05.21; CAS §14.2 |
| INT-03 | 02 | D | BT §1.5; REV SD4.1 |
| INT-04 | 02 | B | BT RT-05.16 |
| INT-05 | 02 | B | BT RT-05.17 |
| INT-06 | 02 | B | BT RT-05.18 |
| INT-07 | 02 | B | BT RT-05.20 |
| INT-08 | 02 | B | BT RT-02.06 |
| INT-09 | 02 | B | BT RT-02.07 y §2.1 |
| INT-10 | 02 | B | BT RT-02.08 |
| INT-11 | 02 | B | BT RT-05.19 |
| INT-12 | 02 | B | BT RT-05.22 y RT-16.29/30 |
| INT-13 | 02 | B | CAS restricción 6 y exclusiones |
| INT-14 | 02 | B | CAS cap. 15, RT-05.23 |
| INT-15 | 02 | D | CAS cap. 15, RT-05.15; REV SD5 |
| SEG-01 | 03 | B | BT RT-11.01 |
| SEG-02 | 03 | B | BT RT-02.03 y RT-11.02 |
| SEG-03 | 03 | B | BA art. 4.3; BT RT-11.05/06 y §11.5 |
| SEG-04 | 03 | B | BT RT-11.07 |
| SEG-05 | 03 | B | BT RT-11.08; CAS §§10/17.4 |
| SEG-06 | 03 | R | BT RT-11.09; REV SD4.1 |
| SEG-07 | 03 | B | BT RT-11.09 y RT-07.10 |
| SEG-08 | 03 | B | CAS cap. 15, RT-11.10 |
| SEG-09 | 03 | D | BT RT-12.05; CAS cap. 15, RT-12.12 |
| SEG-10 | 03 | D | CAS decisión 8; REV SD5 |
| SEG-11 | 03 | D | CAS cap. 15, RT-16.09; BT RT-16.06 |
| SEG-12 | 03 | B | BT RT-12.01/02 |
| SEG-13 | 03 | D | BT RT-12.03/11; CAS RT-12.11 |
| SEG-14 | 03 | R | REV SD4.1; BT RT-12.03/04 |
| SEG-15 | 03 | B | BT RT-12.07/08 |
| SEG-16 | 03 | B | BT RT-12.09/10; CAS RT-12.11 |
| SEG-17 | 03 | B | BT RT-12.06/13 y RT-11.27 |
| SEG-18 | 03 | D | BT RT-12.12; CAS RT-12.12 |
| SEG-19 | 03 | B | BT RT-04.09 |
| SEG-20 | 03 | B | BT RT-11.14/15/16 |
| SEG-21 | 03 | B | BT RT-11.17; CAS RT-03.10 |
| SEG-22 | 03 | B | BT RT-11.18/19 |
| SEG-23 | 03 | B | BT RT-11.04; CAS RT-10.05 |
| SEG-24 | 03 | B | BT RT-11.20 y §20.1 |
| SEG-25 | 03 | B | BA arts. 23/85 |
| SEG-26 | 03 | D | CAS restricción 2 y §17.6.9; REV SD5 |
| SEG-27 | 03 | B | BA arts. 27/85 |
| TR-01 | 04 | B | BT RT-16.01/02/03/04 |
| TR-02 | 04 | B | BT RT-16.06/07/08/11/12/13 |
| TR-03 | 04 | B | BT RT-16.15/16/17/18/19; CAS RT-16.14 |
| TR-04 | 04 | B | BT RT-16.20/21/22/23/25; CAS RT-16.21 |
| TR-05 | 04 | B | BT RT-16.27/28/29/30 |
| TR-06 | 04 | B | CAS cap. 15, RT-16.30; BT RT-16.34 |
| TR-07 | 04 | B | BT RT-16.33 |
| DAT-01 | 04 | B | BT RT-05.02; EX capítulo 5 |
| DAT-02 | 04 | B | BT RT-05.05/25/26/27/28 |
| DAT-03 | 04 | B | CAS cap. 15, RT-05.29 |
| DAT-04 | 04 | B | BT RT-05.01/04/09 |
| DAT-05 | 04 | D | EX §11, capítulo 5.4; REV SD5 |
| DAT-06 | 04 | B | CAS cap. 15, RT-05.10 |
| DAT-07 | 04 | B | BT RT-05.07 y RT-16.10; BA art. 27; REV SD5 |
| DAT-08 | 04 | D | BT RT-05.06/07; BA art. 85 |
| ESC-01 | 05 | D | CAS decisiones 1/5 y §17.4.1 |
| ESC-02 | 05 | D | REV SD4.1, DEC-01; CAS criterios 1/2 |
| ESC-03 | 05 | D | CAS decisión 4 y RT-09.01 |
| ESC-04 | 05 | D | CAS §§14.2/17.4.6; decisión 4 |
| ESC-05 | 05 | D | CAS §17.4.6; REV SD4.1 |
| ESC-06 | 05 | D | CAS RT-16.21 y RT-09.01; §17.4.8 |
| ESC-07 | 05 | D | CAS criterio 5 y §17.5 |
| ESC-08 | 05 | D | CAS decisión 6, RT-09.01; criterios 6/23 |
| ESC-09 | 05 | D | CAS decisión 7 y criterio 7 |
| ESC-10 | 05 | D | CAS RT-09.01; criterios 10/11/12 |
| ESC-11 | 05 | D | CAS decisiones 9/10; criterios 8/9 |
| ESC-12 | 05 | D | CAS decisión 21 y RT-09.01; REV SD4.1 |
| ESC-13 | 05 | D | CAS decisiones 12/13; criterios 14/15/24 |
| ESC-14 | 05 | D | CAS decisiones 14/15/16; criterios 16/17 |
| ESC-15 | 05 | D | CAS restricciones 8/10; §17.4.11 |
| ESC-16 | 05 | D | CAS decisión 3; criterios 18/19 |
| ESC-17 | 05 | D | CAS decisiones 19/20; §17.4.12 |
| ESC-18 | 05 | D | CAS decisiones 17/18; restricción 15 |
| ESC-19 | 05 | D | REV SD4.1; BT RT-03.14 y RT-10.03 |
| ESC-20 | 05 | D | BT RT-10.07/08; CAS decisión 22 |
| UX-01 | 05 | B | BA art. 4.3; BT RT-13.01 |
| UX-02 | 05 | B | BT RT-13.02/07/11 |
| UX-03 | 05 | B | CAS RT-13.08 y RT-09.01 |
| UX-04 | 05 | B | BT RT-13.04/05; CAS RT-09.01 |
| UX-05 | 05 | B | BT RT-13.06 y RT-02.09 |
| UX-06 | 05 | B | BT RT-13.09; BT §25.1 |
| UX-07 | 05 | B | CAS cap. 15, RT-13.12 |
| UX-08 | 05 | B | BT RT-13.03; BA art. 26 |
| OBS-01 | 06 | B | BT RT-14.01; CAS RT-03.10 |
| OBS-02 | 06 | B | BT §1.7 y RT-14.02/03 |
| OBS-03 | 06 | D | BT RT-14.04; CAS §17.4 |
| OBS-04 | 06 | B | BT RT-21.01; BA art. 78; CAS RT-21.06 |
| OBS-05 | 06 | D | BT RT-14.05; CAS restricción 7 |
| OBS-06 | 06 | B | BT RT-14.07/08 |
| OBS-07 | 06 | B | BA arts. 25/79; BT RT-14.06 y RT-09.09 |
| SW-01 | 06 | D | EX capítulo 4.1.1; BT §1.5 |
| SW-02 | 06 | B | BT §1.6; REV SD4.1 |
| SW-03 | 06 | D | BT §1.6; guía de acreditación |
| SW-04 | 06 | D | BT §§1.6/2.3; REV SD4.1 |
| SW-05 | 06 | B | EX capítulo 4.1.1 |
| SW-06 | 06 | R | BT RT-17.02; REV SD4.1 |
| SW-07 | 06 | B | BT RT-17.03 |
| SW-08 | 06 | D | BT RT-17.04/05/07 y RT-13.10 |
| SW-09 | 06 | B | BT RT-03.03 y RT-04.08/09 |
| SW-10 | 06 | D | BT RT-03.14; REV SD4.1 |
| SW-11 | 06 | R | REV SD4.1; BT RT-05.16/21 |
| SW-12 | 06 | B | BT RT-04.03/04 |
| SW-13 | 06 | B | BT RT-04.05/11 y RT-11.22/23/24 |
| SW-14 | 06 | B | BA art. 4.3; BT RT-11.26/28 |
| SW-15 | 06 | B | BT RT-04.06/07/10 |
| SW-16 | 06 | B | BT RT-04.12; BA art. 78.3 |
| SW-17 | 06 | B | BA art. 84 |
| SW-18 | 06 | C | BT cap. 18; BA art. 86; REV SD13 |
| SW-19 | 06 | B | BA art. 24 |
| F-01 | 07 | B | EX capítulo 4; BA T-11 |
| F-02 | 07 | B | BA art. 16.2; BT RT-03.05 |
| F-03 | 07 | D | EX §4 y capítulo 4; CAS §17.4 |
| F-04 | 07 | D | BT RT-03.04; REV SD4.2 |
| F-05 | 07 | B | BT RT-03.02 |
| F-06 | 07 | D | EX capítulo 4.2; BT RT-09.01 |
| F-07 | 07 | B | BT §4.1 y RT-04.01; EX capítulo 4.2 |
| F-08 | 07 | B | BT RT-04.02 y RT-11.25 |
| F-09 | 07 | B | BA arts. 15/17 |
| F-10 | 07 | B | BT RT-02.11 y RT-10.06; EX capítulo 4.2 |
| RED-01 | 07 | B | CAS cap. 15, RT-03.24; REV SD4.2 |
| RED-02 | 07 | D | REV SD4.2; EX capítulo 4.2 |
| RED-03 | 07 | B | BT RT-11.13 y RT-03.04/22 |
| RED-04 | 07 | B | BT RT-03.17; BA art. 16.4 |
| RED-05 | 07 | B | REV SD4.1/4.2; BT §1.5 |
| RED-06 | 07 | B | BT RT-03.20/21/24; REV SD4.1 |
| RED-07 | 07 | B | CAS cap. 15, RT-03.24; BT RT-03.23 |
| RED-08 | 07 | D | CAS RT-03.24 y RT-13.08 |
| RED-09 | 07 | D | CAS restricción 9 y §§16.2/17.4.4 |
| RED-10 | 07 | D | CAS §17.4.5; BT RT-03.18 |
| RED-11 | 07 | B | CAS RT-05.10 y restricción 3; BT RT-06.24 |
| RED-12 | 07 | D | CAS restricción 4; §17.4.6 |
| RED-13 | 07 | D | CAS RT-17.06; REV SD4.2 |
| RED-14 | 07 | D | CAS RT-21.16 y §17.4.12 |
| OFF-01 | 08 | D | CAS cap. 15, RT-03.10 |
| OFF-02 | 08 | D | CAS cap. 15, RT-03.10 |
| OFF-03 | 08 | D | BT RT-03.11; CAS §14.2 |
| OFF-04 | 08 | D | BT RT-03.11; BT RT-16.06 |
| OFF-05 | 08 | D | BT RT-03.12; REV SD4.1 |
| OFF-06 | 08 | D | CAS cap. 15, RT-03.13; REV SD4.1/SD5 |
| OFF-07 | 08 | D | CAS §14.2; BT RT-03.12 |
| OFF-08 | 08 | D | BT RT-03.13; CAS restricción 5 |
| OFF-09 | 08 | D | BT RT-03.15/18 |
| OFF-10 | 08 | D | CAS RT-03.10/13; BT §20.1 |
| CAP-01 | 08 | B | CAS §14.1 |
| CAP-02 | 08 | D | CAS §§6/14.1; EX §3 |
| CAP-03 | 08 | B | CAS §14.2; BT RT-09.01 |
| CAP-04 | 08 | B | CAS §14.2; BT RT-09.01 |
| CAP-05 | 08 | D | CAS §14.2 y decisión 3 |
| CAP-06 | 08 | D | CAS §14.2; BT RT-09.01 |
| CAP-07 | 08 | B | CAS RT-05.15 y §14.2 |
| CAP-08 | 08 | B | CAS RT-16.21/09.01 y §14.2 |
| CAP-09 | 08 | D | CAS §14.2; REV SD4.1 |
| CAP-10 | 08 | D | CAS RT-03.13 y §14.2 |
| CAP-11 | 08 | D | BT RT-03.20; CAS §14.2 |
| CAP-12 | 08 | D | BT RT-08.01 y RT-09.01; EX capítulo 4.2 |
| CAP-13 | 08 | D | BT §6.1 y RT-06.07/11/13; REV SD4.2 |
| CAP-14 | 08 | B | BT RT-08.05 y RT-09.03; CAS §14.1 |
| CAP-15 | 08 | B | BT RT-02.10 y RT-09.04 |
| CAP-16 | 08 | B | BT RT-09.05; CAS §17.4.14 |
| CAP-17 | 08 | B | BT §9.1; CAS RT-09.01 |
| CAP-18 | 08 | B | BT RT-09.06/07/08 |
| CAP-19 | 08 | D | CAS §14.2; BT RT-09.09 y RT-21.06/14 |
| CAP-20 | 08 | R | CAS §14.2 y decisión 22; REV SD4.1 |
| VID-01 | 09 | B | BA art. 17 y E-25; BT RT-04.01 |
| VID-02 | 09 | D | CAS §§10/17.5; REV SD4.1 |
| VID-03 | 09 | B | BA art. 17.3; BT RT-20.03 |
| VID-04 | 09 | B | CAS §§13.2/17.5; criterio 19 |
| VID-05 | 09 | B | BA art. 29; EX §8; REV SD13 |
| VID-06 | 09 | B | BA arts. 4.3/26; BT RT-15.01/02/03/04 |
| VID-07 | 09 | B | BT RT-03.06/08/09 |
| VID-08 | 09 | B | BT RT-03.07/05.06; BA art. 77 |
| VID-09 | 09 | B | BA arts. 77/84 |
| HW-01 | 09 | B | CAS cap. 11; BA art. 14.2 |
| HW-02 | 09 | B | BA T-11; REV SD4.2 |
| HW-03 | 09 | D | BT RT-08.01/10/13; §8.4 |
| HW-04 | 09 | D | BT RT-03.14 y RT-08.01/02 |
| HW-05 | 09 | B | BT RT-08.03/04; REV SD4.2 |
| HW-06 | 09 | D | CAS RT-06.01; BT RT-08.10/12 |
| HW-07 | 09 | D | CAS decisión 3 y criterio 18; BT RT-08.10 |
| HW-08 | 09 | R | CAS decisión 1; REV SD4.1 |
| HW-09 | 09 | D | CAS RT-17.01 y §14.1; REV SD4.2 |
| HW-10 | 09 | B | BT RT-08.11/12; CAS RT-13.08 |
| HW-11 | 09 | B | CAS RT-17.06; BT RT-08.10 |
| HW-12 | 09 | D | CAS restricción 10 y §17.4.11 |
| HW-13 | 09 | D | CAS RT-17.06; exclusiones; BT RT-08.10 |
| HW-14 | 09 | D | BT §6.1 y RT-06.07; REV SD4.2 |
| HW-15 | 09 | B | BT RT-08.07/08/09 |
| HW-16 | 09 | B | BT RT-08.06 y §8.4 |
| HW-17 | 09 | B | BT §8.4 |
| HW-18 | 09 | D | BT RT-08.13; CAS restricción 9 |
| HW-19 | 09 | B | BT RT-08.16/17/18/19 |
| HW-20 | 09 | D | CAS cap. 11; BA art. 50.2 |
| HW-21 | 09 | C | BT RT-08.15/19 |
| DC-01 | 10 | B | BA art. 16; EX capítulo 4.3 |
| DC-02 | 10 | R | BA art. 16.3; REV SD4.2; BT RT-07.02 |
| DC-03 | 10 | B | BA art. 16.2; BT RT-07.02 y §1.6 |
| DC-04 | 10 | B | BA art. 34; BT RT-03.01 |
| DC-05 | 10 | B | BA T-7, ítem 4.2 |
| P-01 | 10 | B | BT RT-03.01; EX capítulo 4.3.1 |
| P-02 | 10 | D | BT RT-03.02/04; BA art. 85 |
| P-03 | 10 | B | BT §6.1; CAS RT-06.01 |
| P-04 | 10 | D | BT §6.1 y RT-06.03; REV SD4.2 |
| P-05 | 10 | D | BT §6.1; CAS RT-06.01 |
| P-06 | 10 | D | BT RT-06.07/09/10; CAS §16.2 |
| P-07 | 10 | D | BT §6.1 y RT-06.08; REV SD4.2 |
| P-08 | 10 | D | BT §6.1 y RT-06.13/14 |
| P-09 | 10 | D | BT §6.1 y §§6.5/6.6 |
| P-10 | 10 | D | BT §§6.7/6.8; CAS restricción 7 |
| P-11 | 10 | B | BT RT-06.32/33 y §§6.1/7.2 |
| S-01 | 10 | B | BT §7.1 y RT-07.01 |
| S-02 | 10 | B | BT RT-07.02 |
| S-03 | 10 | D | BT RT-07.03; CAS RT-03.10 |
| S-04 | 10 | B | BT RT-07.04 |
| S-05 | 10 | D | BT RT-07.05; CAS restricción 7 |
| S-06 | 10 | D | BT RT-07.06/08 |
| S-07 | 10 | B | BT RT-07.07 y §20.1 |
| S-08 | 10 | B | BT RT-07.09 |
| S-09 | 10 | B | BT RT-07.10/11 |
| S-10 | 10 | D | BT RT-07.13; CAS RT-05.10 |
| S-11 | 10 | B | BT RT-07.12/14 |
| S-12 | 10 | B | BT RT-10.01/02/03/04; BA art. 78 |
| ADR-01 | 11 | D | BT RT-02.04; CAS §17.1 |
| ADR-02 | 11 | B | BT RT-02.04; BA art. 71 |
| ADR-03 | 11 | R | REV SD4.1; CAS §17.1 |
| ADR-04 | 11 | B | CAS §17.1; decisiones de §16.1 |
| MAP-01 | 11 | D | CAS cap. 15 y filas homónimas de BT |
| MAP-02 | 11 | B | BT §1.5; BA T-12 |
| MAP-03 | 11 | B | BT §1.5 y anexo A; BA T-22 |
| MAP-04 | 11 | B | CAS §17.1; EX §3 |
| MAP-05 | 11 | B | BT §1.5; BA arts. 4.3/58 |
| REV-01 | 12 | R | REV SD4.1, esquema; EX capítulo 4 |
| REV-02 | 12 | R | REV SD4.1, contradicciones |
| REV-03 | 12 | R | REV SD4.1, Qué se espera |
| REV-04 | 12 | R | REV SD4.1, escenarios faltantes |
| REV-05 | 12 | R | REV SD4.1, decisiones |
| REV-06 | 12 | R | REV SD4.2, regiones |
| REV-07 | 12 | R | REV SD4.2, Qué se espera |
| REV-08 | 12 | R | REV SD4.2, T-11 |
| REV-09 | 12 | R | REV SD4.2, tipología on-premise |
| REV-10 | 12 | R | REV SD4.1/4.2, ausencias |
| REV-11 | 12 | R | REV SD4.2, reposición |
| REV-12 | 12 | R | REV SD4.1, factibilidad cruzada |
| REV-13 | 12 | R | REV SD4.1, dimensionamiento |
| REV-14 | 12 | R | REV SD5; EX capítulo 5 |
| REV-15 | 12 | R | REV SD13; EX §8 |
| REV-16 | 12 | R | REV General; EX §§3/4/6/7 |
| REV-17 | 12 | R | BA art. 46; REV General |
| DOC-01 | 13 | D | BT RT-02.03; EX §4; CAS §17.4 |
| DOC-02 | 13 | B | EX §4 |
| DOC-03 | 13 | D | EX §§4/7.1; REV General |
| DOC-04 | 13 | B | EX §5 |
| DOC-05 | 13 | D | EX §3; CAS §14; BT RT-09.01 |
| DOC-06 | 13 | B | EX §6; REV General |
| DOC-07 | 13 | B | EX §§2/7.2; BA A-6 |
| DOC-08 | 13 | B | EX §7.1/7.2 |
| DOC-09 | 13 | R | REV General; EX §7.1 |
| FIN-01 | 13 | D | EX capítulo 4 y §3 |
| FIN-02 | 13 | D | EX capítulo 4; BA T-11 |
| FIN-03 | 13 | D | CAS §17.4 |
| FIN-04 | 13 | D | CAS §17.1; REV SD4.1 |
| FIN-05 | 13 | D | CAS cap. 15; BT cap. 7; BA art. 78 |
| FIN-06 | 13 | D | BT §1.6; EX §3; REV SD4 |
| FIN-07 | 13 | D | CAS restricciones 1/7 y RT-06.01 |
| FIN-08 | 13 | D | BT cap. 8; CAS cap. 11 |
| FIN-09 | 13 | D | BT caps. 11/12/18; CAS cap. 15 |
| FIN-10 | 13 | D | BA art. 57.2; CAS §17.5 |
| FIN-11 | 13 | D | BA art. 46; BT §1.5; REV SD3 |
| FIN-12 | 13 | D | EX §7.1; BT §1.5; BA art. 50.2 |
| FIN-13 | 13 | G | Guía interna; BT §1.5; BA art. 46 |

## Verificación del paquete corregido

Se verificó cobertura de los cinco documentos, 303 IDs únicos, una sola aparición de cada ID en las trece tareas, correspondencia entre checklist consolidado y partes, enlaces existentes, referencias a códigos RT presentes en las fuentes y conservación de las identidades de los archivos actualizados. La clasificación y este registro no se incorporan automáticamente al cuerpo del SD4; orientan al agente.
