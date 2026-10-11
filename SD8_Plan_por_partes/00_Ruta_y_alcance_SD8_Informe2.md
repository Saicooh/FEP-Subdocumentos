# SD8 · Checklist por partes · Informe 2

Este conjunto sirve para desarrollar el contenido del **Plan de riesgos de Synaptix para Marina y Club Náutico Bahía Panitao** en el Informe 2. No constituye el SD8 redactado. Cada parte es una tarea acotada para un agente y debe integrarse bajo el índice obligatorio del capítulo 8.

## 1. Alcance y lectura de las etiquetas

Se consideran las cinco fuentes adjuntas. La imagen se usa exclusivamente como referencia de la división del trabajo en Markdown.

- **[E] Exigencia explícita:** contenido pedido directamente por la fuente citada.
- **[A] Aplicación al caso:** descomposición práctica de una exigencia para analizar la solución de Panitao. El escenario deriva de la fuente, pero su redacción como riesgo no es una cita literal ni una obligación adicional independiente.
- **[C] Condicional:** exigencia que corresponde únicamente si la propuesta incorpora ese componente o esa decisión.
- **[V] Verificación:** control de consistencia del trabajo; no añade alcance contractual.

Los archivos 03, 04 y 05 proporcionan escenarios a analizar. No obligan a inventar un riesgo por cada viñeta ni a alcanzar una cantidad predeterminada de filas. Pueden agruparse escenarios si conservan causas, consecuencias y tratamientos distinguibles; deben separarse cuando la agrupación esconda una respuesta diferente.

## 2. Fuentes y abreviaturas

Esta tabla identifica las fuentes usadas en las citas internas del checklist.

| Código | Fuente adjunta | Función en SD8 |
|---|---|---|
| BA | FEP01.26 Bases Administrativas TFEP-01-2026-3 | T-7, T-16, T-22; continuidad, gobierno, contrato y límites económicos. |
| BTT | FEP02.26 Bases Técnicas Transversales TFEP-01-2026 | ISO 31000, registro vivo, controles técnicos, continuidad y respuesta. |
| CASO | Bases Técnicas Caso 07 · Puerto Deportivo | Riesgos, restricciones, actores, dependencias y ventanas propios de Panitao. |
| EX | Instrucciones extras | Índice obligatorio del capítulo 8; RBS, análisis, acciones y reservas. |
| REV | Synaptix G7 · Informe 1 · Revisión | Correcciones y contradicciones previas que afectan al riesgo del Informe 2. |

## 3. Orden de ejecución

La siguiente ruta evita mezclar identificación, evaluación y respuesta antes de tener una misma solución de referencia.

| Orden | Parte | Resultado de trabajo |
|---|---|---|
| 01 | [Estructura y gobierno](01_Estructura_y_gobierno_del_riesgo.md) | Introducción y contenido de 8.1. |
| 02 | [Método de análisis y T-16](02_RBS_analisis_y_Formulario_T16.md) | RBS, escalas aplicadas, análisis y registro coherente. |
| 03 | [Riesgos técnicos y seguridad](03_Riesgos_tecnicos_datos_y_seguridad.md) | Escenarios de arquitectura, datos, seguridad y tecnologías. |
| 04 | [Riesgos operacionales y adopción](04_Riesgos_operacionales_y_de_adopcion.md) | Escenarios de custodia, personas, resistencia y operación. |
| 05 | [Desarrollo e implantación](05_Riesgos_de_desarrollo_e_implantacion.md) | Escenarios de ejecución, dependencias, migración y puesta en producción. |
| 06 | [Respuestas y reservas](06_Tratamientos_contingencias_y_reservas.md) | Acciones de 8.3, contingencias y efecto en la planificación. |
| 07 | [Continuidad y recuperación](07_Continuidad_y_recuperacion.md) | BCP/DRP articulado con 8.2 y 8.3. |
| 08 | [Correcciones y cierre](08_Correcciones_trazabilidad_y_cierre.md) | Trazabilidad de la revisión previa, referencias, declaración IA y verificación final. |
| 09 | [Validación de fuentes](09_Validacion_de_las_cinco_fuentes.md) | Mapa de cobertura y límites de lo exigido. |

## 4. Límites que el agente debe respetar

Estos límites forman parte del encargo y evitan añadir exigencias que las fuentes no contienen.

- [ ] [E] Desarrollar **análisis de riesgo de la solución, del desarrollo del proyecto y de implantación** en esta entrega. No diferirlos a la propuesta final. Fuente: BA, T-22, Informe 2.
- [ ] [E] Incluir riesgos de operación y continuidad como parte del plan de riesgos, aunque SD10, SD11 y SD12 no sean subdocumentos exigidos en el Informe 2. No redactar aquí esos subdocumentos completos. Fuentes: BA, T-7, apartado de gestión de riesgos; EX, capítulo 8; BA, T-22.
- [ ] [E] Incluir un BCP/DRP conforme a ISO 22301 e ISO/IEC 27031. Su integración bajo 8.2/8.3 conserva el índice de EX. Fuente: BA, T-7, apartado 10; BTT, RT-10.03 y RT-10.04.
- [ ] [V] Trabajar con las decisiones corregidas de SD3, SD4, SD5, SD6, SD7, SD9 y SD13; la revisión del Informe 1 identifica problemas anteriores y no demuestra cuál es la solución corregida actual.
- [ ] [V] Si faltan esos subdocumentos actuales, dejar en el registro de trabajo la dependencia que debe resolverse. No inventar sensores, proveedores, nombres de responsables, regiones, pruebas realizadas o decisiones aprobadas para completar el checklist.
- [ ] [V] Distinguir una condición ya conocida de un evento futuro: el rechazo a cámaras sobre menores es una restricción existente; el riesgo es incumplirla o que una alternativa permitida fracase. La ausencia de TI en el CLIENTE también es un hecho, no una probabilidad por estimar.
- [ ] [E] Usar sólo cifras del caso, cálculos mostrados o supuestos fundados. Las probabilidades y estimaciones propuestas se declaran como estimaciones, no como mediciones del CLIENTE. Fuente: EX, sección 3; CASO, 14.2 y 17.1.
- [ ] [E] Mantener fuera de la oferta técnica precios, tarifas, costos unitarios y cifras que permitan inferir el monto ofertado. Fuente: BA, Art. 50.2; EX, 8.3.
- [ ] [V] No exigir mostrar la ponderación de SD8 en el contenido. T-21 asigna 10 % al Informe 2 y 7 % a la evaluación final, pero eso no es una instrucción para añadir esos porcentajes al plan de riesgos.
- [ ] [V] No imponer un mínimo de riesgos, escala 5×5, porcentaje fijo de reserva, software de simulación ni un número de escenarios que las fuentes no fijan.
- [ ] [V] No incluir tareas sobre nombres de PDF, ZIP, firmas, portadas, tipografías o formatos de entrega. Este checklist se limita al contenido; conserva referencias y declaración de IA porque contienen información exigida.

## 5. Criterio de terminación del conjunto

El trabajo está completo cuando todos los riesgos relevantes están identificados y evaluados, las respuestas son ejecutables y trazables, el T-16 coincide con el análisis, existe continuidad específica de Panitao y las observaciones anteriores vinculadas a SD8 tienen respuesta verificable. Marcar una casilla requiere contenido o una justificación de no aplicabilidad; una promesa de completarlo después no cierra la casilla.
