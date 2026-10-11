# Parte 01 · Estructura y gobierno del riesgo

**Destino:** introducción del capítulo 8 y sección 8.1. **Fuentes principales:** EX, secciones 2, 3 y 11, capítulo 8; BA, T-7, T-22 y Arts. 71–72; BTT, RT-19.04–19.06 y RT-19.09. Leer las etiquetas en la parte 00.

## 1. Estructura de contenido obligatoria

El índice de EX fija dónde desarrollar el contenido de SD8, aunque el apartado de gestión de riesgos figure como número 10 dentro del listado original de T-7. No trasladar el equipo de trabajo a SD8 por el número 8 de ese listado original.

- [x] [E] Mantener el título **«Capítulo 8 · Introducción a los Riesgos»**.
- [x] [E] Abrir el capítulo con un texto que resuma el plan y explique su conexión con alcance, arquitectura, datos, metodologías, planificación, calidad, innovaciones y Formulario T-16.
- [x] [E] Mantener, en este orden, **«8.1 Plan de riesgos»**, **«8.2 Identificación y Análisis de Riesgos»** y **«8.3 Plan de Acción a Riesgos»**.
- [x] [E] Usar subtítulos de menor nivel para ordenar temas extensos. No añadir un 8.4 ni sustituir los tres títulos obligatorios por títulos propios.
- [x] [E] Desarrollar bajo 8.1 el enfoque de gestión, roles, escalas de probabilidad e impacto y ciclo de revisión.
- [x] [E] Desarrollar bajo 8.2 la identificación, RBS, cuantificación y análisis cualitativo y cuantitativo.
- [ ] [E] Desarrollar bajo 8.3 las acciones, su análisis costo-beneficio, responsables, plazos, disparadores y reservas con efecto en el cronograma.
- [ ] [E] Incorporar el contenido de continuidad y recuperación que exige T-7 bajo subtítulos de 8.2 y/o 8.3, enlazado con los riesgos que trata.
- [x] [E] Terminar con las secciones sin numerar **«Referencias»** y **«Declaración de uso de IA»**, en ese orden. Su contenido se verifica en la parte 08.

## 2. Enfoque de gestión

El plan debe explicar cómo se tomarán decisiones frente a incertidumbres de esta solución, no limitarse a describir una norma.

- [x] [E] Adoptar ISO 31000 y explicar su aplicación al proyecto: identificación, evaluación, priorización, tratamiento, seguimiento y actualización. Fuente: BTT, RT-19.04.
- [x] [E] Explicar la metodología de evaluación cualitativa y cuantitativa y de tratamiento. Fuente: BA, T-7, gestión de riesgos; EX, 8.2.
- [x] [A] Declarar el contexto de evaluación: custodia de embarcaciones, menores en el agua, combustible y residuos peligrosos, personal estacional y CLIENTE sin TI. Fuentes: CASO, caps. 1–3 y 19.
- [x] [A] Delimitar el horizonte: diseño y construcción, marchas blancas, producción de ambas etapas y 36 meses de operación, dentro de los 56 meses contractuales. Fuentes: BA, Art. 17; EX, 8.2.
- [x] [A] Explicar cómo se relacionan las tres perspectivas exigidas por T-22 —solución, desarrollo e implantación— con las categorías de la RBS. No usar ambas clasificaciones como si fueran una sola.
- [x] [A] Identificar las decisiones, supuestos y dependencias que sirven de línea de referencia para evaluar. Si un supuesto falla, explicar qué riesgo se activa y qué parte del alcance resulta afectada. Fuente: CASO, 16.1 y 17.1.
- [x] [A] Explicar cómo se priorizan impactos sobre personas, custodia, integridad de registros y obligaciones ambientales frente a otros impactos. No presentar una matriz que rebaje automáticamente un evento grave sólo porque su probabilidad sea baja.
- [x] [V] Distinguir riesgos, incidentes y restricciones: una falla materializada requiere respuesta y registro de incidente; una restricción del caso debe cumplirse desde el diseño; un riesgo describe una incertidumbre y su consecuencia.

## 3. Responsabilidades concretas

Cada rol debe poder ejercer lo que el plan le atribuye. El CLIENTE puede aportar validación funcional, pero no un administrador técnico inexistente.

- [x] [E] Definir responsables de identificación, evaluación, tratamiento y seguimiento del riesgo. Fuentes: EX, 8.1 y 8.3; BTT, RT-19.04; BA, T-16.
- [x] [A] Alinear la responsabilidad de coordinación con el Jefe de Proyecto y los responsables técnicos con arquitectura, seguridad, datos, calidad, integración, implantación y operación según el equipo real. No crear cargos sin recursos en SD7/T-15. Fuentes: BTT, 19.2; BA, T-22.
- [ ] [A] Asignar a cada riesgo un propietario y a cada acción un ejecutor concreto; pueden coincidir. Comprobar su capacidad de decisión y disponibilidad.
- [x] [A] Identificar a las contrapartes funcionales de marina, escuela, varadero, portería y administración para las acciones que requieran su participación, sin tratarlas como personal TI. Fuentes: CASO, 2.4, 16.1 decisión 22 y 17.6.
- [x] [A] Declarar sustitución y continuidad cuando el titular se ausente. En particular, coordinar la contingencia de administración y sistema de 2014 con las partes 04–07. Fuentes: CASO, cap. 19; REV, SD3 y SD5.
- [x] [A] Definir quién decide la activación de contingencias, quién comunica al CLIENTE y quién autoriza cambios o aceptación de riesgos residuales. Las facultades deben ser compatibles con el gobierno contractual.
- [x] [V] No atribuir aprobación previa ni compromiso de participación a una persona sólo porque aparece entrevistada en el caso.

## 4. Ciclo de revisión y escalamiento

El registro debe mantenerse vivo durante la ejecución. La cadencia obligatoria del Comité de Proyecto no puede sustituirse por una revisión anual genérica.

- [x] [E] Revisar el registro en **cada Comité de Proyecto**, cuya frecuencia es **quincenal**. Fuentes: BTT, RT-19.04; BA, Art. 71.
- [x] [E] Escalar riesgos mayores al **Comité Ejecutivo mensual** y riesgos técnicos al **Comité de Arquitectura mensual**, según sus funciones. Fuente: BA, Art. 71.
- [x] [E] Articular el seguimiento de riesgos operacionales con el **Comité de Operación mensual desde el mes 13**. Fuente: BA, Art. 71.
- [x] [E] Mantener el registro actualizado en un espacio colaborativo accesible al CLIENTE. Fuente: BTT, RT-19.05.
- [x] [E] Incluir riesgos, desviaciones, incidencias y compromisos en el informe mensual de avance. Fuente: BTT, RT-19.06.
- [x] [E] Registrar acuerdos, responsables y plazos de los comités en actas dentro de los dos días hábiles siguientes. Fuente: BTT, RT-19.09.
- [x] [A] Definir eventos que obligan a reevaluar sin esperar la siguiente reunión: cambio arquitectónico, falla de piloto, resultado de migración, cambio de ventana, incidente grave o indisponibilidad de un actor crítico.
- [x] [A] Explicar cómo se actualizan evaluación, acciones, exposición y estado; cómo se comprueba el cierre; y cómo se reabre un riesgo si cambia su causa.
- [x] [E] Para una respuesta que cambie la línea base, aplicar análisis de impacto y aprobación previa del control de cambios. No ejecutar unilateralmente cambios de alcance ni modificar el cronograma obligatorio. Fuentes: BA, Art. 72; BTT, RT-19.03.

## 5. Evidencia que debe quedar en el cuerpo

El subdocumento resume y analiza; el registro completo y los cálculos extensos detallan la evaluación.

- [x] [E] Explicar por qué los riesgos principales pertenecen a la solución efectivamente propuesta. Fuente: EX, capítulo 8; BA, Art. 57.
- [x] [E] Incluir figuras integradas que apoyen el análisis, citarlas y explicarlas antes y después según EX. Para esta materia pueden servir la RBS y un flujo de detección, decisión y escalamiento; el diseño concreto es una elección del proponente.
- [x] [E] Interpretar las síntesis o matrices del cuerpo: qué muestra la distribución, qué domina la exposición y qué decisión se deriva. Evitar un capítulo compuesto sólo por tablas. Fuentes: EX, 3–5; REV, General.
- [x] [V] Verificar que la metodología descrita en 8.1 es la que se aplica en el T-16 y en las acciones. No declarar una escala o técnica que luego no se utilice.

## Avance de la parte 01 · 10 de octubre de 2026

Se leyó la parte 00 y se continuó únicamente la parte 01. Estado actual: **33 de 37 controles marcados**. La matriz `../registros_cambios/SD8_CONTROL_CUMPLIMIENTO.md` conserva los IDs y registra evidencias de ambas iteraciones. La parte 01 sigue abierta.

Se cerraron la identificación de la línea de referencia, la asignación propuesta Implantación/SRE, el procedimiento de relevo y contingencia temprana del legado, y la concordancia metodológica SD8/T-16. Se propone a José Lara Arce en Implantación desde el mes 8 y SRE desde el 6, con agenda única alineada en T-15. R-05 conserva el antecedente funcional vigente de 5.257,66/7.360,72 HH y sensibilidad de 40 %, sin convertirlo en reserva disponible.

Pendientes: análisis completo y cuantificación (P01-1.06, parte 02), respuestas y reservas (P01-1.07, parte 06), BCP/DRP (P01-1.08, parte 07) y ejecutores/suplentes con competencia, agenda y capacidad comprobadas (P01-3.03). La asignación nominal propuesta no acredita contratación ni cobertura simultánea. No se ejecutaron integralmente las partes 02–09.

## Desarrollo de pendientes · 10 de octubre de 2026

**34 de 37 controles marcados.** P01-1.06 incorpora fundamento cualitativo de los 34 riesgos y escenarios cuantificados de disponibilidad, restauración, atención, ventanas y capacidad. Se desarrollaron 34 acciones con ejecutor propuesto, costo-beneficio, cargas de preparación y reservas; BIA, procedimientos manuales, conmutación, retorno, respaldo y pruebas. SD5 se alinea con el destino DR vigente de SD4; T-15 recibe la dependencia concreta de acciones.

Siguen abiertos P01-1.07 (reservas sin cabida global demostrada), P01-1.08 (brechas técnicas/ejecución por CLIENTE y tiempo por doce dominios) y P01-3.03 (capacidad, suplentes y agenda). La matriz conserva evidencias y acciones precisas; no se marca cumplimiento con asignaciones nominales ni con hipótesis de tiempos. Compilación local correcta de SD8/T-16/T-15/SD5 y revisión visual parcial registradas en `.atl/SD8_parte01_2026-10-10/pendientes/`.
