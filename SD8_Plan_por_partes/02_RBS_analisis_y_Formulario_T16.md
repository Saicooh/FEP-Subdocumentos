# Parte 02 · RBS, análisis y contenido del Formulario T-16

**Destino:** sección 8.2 y contenido de T-16. **Fuentes principales:** BA, T-7 y T-16; EX, 8.1–8.3; BTT, RT-19.04; CASO, 17.1 y cap. 19. Las partes 03–05 aportan los escenarios que deben entrar en este análisis.

## 1. Identificación y RBS

La RBS organiza las fuentes de riesgo y permite comprobar que no se omite una categoría. No reemplaza el análisis de los riesgos individuales.

- [x] [E] Presentar una **RBS —estructura de descomposición de riesgos—** con riesgos **técnicos, organizacionales, de proyecto, de seguridad y de operación**. Fuente: EX, 8.2.
- [x] [E] Cubrir expresamente **obsolescencia tecnológica, bloqueo por proveedor, escalabilidad, ciberseguridad y disponibilidad de contrapartes del CLIENTE**. Fuente: EX, 8.2.
- [x] [E] Identificar riesgos específicos de la solución, desarrollo e implantación. Fuente: BA, T-22, Informe 2.
- [x] [A] Recorrer alcance, arquitectura, integraciones, datos, seguridad, calidad, EDT, hitos, ventanas, innovaciones y operación para identificar escenarios. Citar el origen concreto, no sólo «riesgos tecnológicos».
- [x] [A] Redactar cada riesgo con causa, evento incierto y consecuencia. Ejemplo de estructura, no de riesgo ya aprobado: «si [condición], puede ocurrir [evento], afectando [proceso/hito]».
- [x] [A] Vincular cada riesgo con el proceso, componente, supuesto, dependencia o paquete de trabajo que realmente afecta.
- [x] [A] Separar impactos de seguridad física, datos sensibles, plazo, calidad, continuidad, obligaciones con terceros y sostenibilidad de operación cuando tengan respuestas distintas.
- [x] [V] No convertir cada requisito RT en una fila titulada «incumplimiento de RT-xx». Describir el modo de falla y la exposición concreta de Panitao; usar el RT como fuente o control asociado.
- [x] [V] No tratar exclusiones como ausencia de riesgo: analizar las dependencias de contabilidad, autoridad, hardware, obras del CLIENTE y terceros. Fuente: CASO, cap. 11.

## 2. Escalas y evaluación cualitativa

La fuente exige escalas de probabilidad e impacto, pero no fija cuántos niveles ni sus límites. La escala que el proponente elija debe quedar definida y aplicarse igual en todo el plan.

- [x] [E] Declarar las escalas de **probabilidad e impacto** y su significado. Fuente: EX, 8.1.
- [x] [A] Definir el período al que se refiere cada probabilidad: actividad, campaña, implantación, mes operativo o período contractual. Evitar comparar valores con horizontes distintos sin explicación.
- [x] [A] Definir criterios observables de impacto para el caso: afectación de custodia o personas, pérdida de datos, demora de hito, indisponibilidad y obligaciones ambientales. No inventar umbrales como si vinieran dados por las bases.
- [x] [E] Evaluar **probabilidad, impacto y exposición**, y priorizar. Fuentes: BA, T-7 y T-16.
- [x] [A] Mostrar la regla de exposición. Si se utiliza P×I, indicar qué representan ambas variables y si el resultado es una puntuación ordinal o una magnitud física.
- [x] [A] Definir bandas de prioridad y decisiones asociadas: qué requiere intervención, qué se escala, qué queda bajo vigilancia y quién puede aceptar lo residual.
- [x] [A] Fundamentar la asignación de cada valor con la condición del caso, una estimación trazable o un supuesto razonado. No asignar probabilidades iguales a todo por conveniencia.
- [x] [A] Explicar los riesgos dominantes y las dependencias entre ellos; por ejemplo, cancelación por marejada, compra tardía e instalación sin ventana pueden agravar un mismo hito.
- [x] [V] No confundir frecuencia de actividad con probabilidad de falla: 1.150 movimientos de travelift al año no significan 1.150 eventos de daño.
- [x] [V] No convertir automáticamente un nivel ordinal «4» en 80 % ni utilizar una matriz de colores como único análisis cuantitativo.

## 3. Análisis cuantitativo

La cuantificación debe mostrar qué cambia en la exposición o en el plan cuando se materializa un escenario. No basta mencionar FMEA, árbol de fallas o simulación sin aplicarlos.

- [x] [E] Desarrollar análisis cualitativo **y cuantitativo**. Fuentes: BA, T-7, gestión de riesgos; EX, 8.2.
- [x] [E] Aplicar técnica de **análisis de modos de falla, árbol de fallas o simulación**, escogiendo la que sirva al escenario y explicando por qué. EX admite alternativas; no obliga a aplicar las tres ni a usar Monte Carlo.
- [x] [A] Declarar entradas, unidades, supuestos, fuente y procedimiento de cálculo o modelado; presentar resultados interpretados y la decisión que sustentan.
- [x] [A] Para un modo de falla, identificar función, falla, causa, efecto y controles, y cuantificar conforme al método declarado. Si se usa detectabilidad u otro factor, definir su escala como elección del proponente.
- [x] [A] Para un árbol de fallas, definir evento superior y relaciones entre causas. Justificar las probabilidades y cualquier supuesto de independencia.
- [x] [A] Para simulación, declarar variables, escenarios o distribuciones, dependencias y criterio de resultado. No inventar distribuciones o percentiles como exigencias de las bases.
- [x] [A] Cuantificar, según el riesgo, días de retraso, duración de recuperación, volumen de registros expuestos, esfuerzo de corrección o probabilidad de cumplir el hito. No insertar montos ofertados.
- [ ] [E] Cuantificar específicamente la holgura para cancelaciones por marejada y explicar su base. Fuentes: CASO, introducción, 17.5 y cap. 19.
- [x] [A] Cuando se use retraso esperado, distinguirlo de una reserva para un escenario adverso. Como ejemplo de cálculo permitido, P(evento) × días de retraso expresa días esperados sólo si P es una probabilidad y los días representan ese evento; no usar puntuaciones ordinales en esa fórmula.
- [ ] [A] Mostrar el efecto de escenarios relevantes sobre ruta crítica, ventanas disponibles y frentes concurrentes; coordinar con SD7 para evitar reservas que no caben en el calendario.
- [x] [V] Señalar que las estimaciones son propuestas de ingeniería; no presentarlas como histórico medido de cancelaciones o tasa real de falla cuando el caso no entrega ese dato.
- [x] [V] Verificar aritmética, unidades y coherencia entre resultados, prioridad y tratamiento seleccionado.

## 4. Contenido obligatorio de T-16

El formulario base incluye ocho columnas. Sus dos filas vacías son una plantilla ilustrativa, no una exigencia de identificar exactamente dos riesgos.

- [x] [E] Completar, para cada riesgo registrado: **N°**, **Riesgo**, **Categoría**, **Prob.**, **Impacto**, **Expos.**, **Estrategia / Mitigación** y **Responsable**. Fuente: BA, T-16, p. 63.
- [x] [E] Incorporar también **plan de contingencia**, aunque no tenga columna propia en la plantilla. BA, T-7, lo exige expresamente: puede desarrollarse en el campo de estrategia con referencia precisa al detalle o en un complemento trazable.
- [x] [E] Incorporar **responsable, plazo y disparador** para las acciones. Si no caben en la plantilla, proporcionar un detalle vinculado inequívocamente a la misma fila. Fuentes: EX, 8.3; BTT, RT-19.04.
- [x] [A] Usar identificadores estables para enlazar análisis, T-16, acciones, continuidad, cronograma y riesgos de las innovaciones.
- [x] [A] Añadir al registro de trabajo fuente, causa, consecuencia, perspectiva de T-22, componente/paquete afectado, estado y referencia al análisis, cuando se requieran para comprobar trazabilidad. Son campos prácticos, no columnas literales adicionales del formulario.
- [x] [A] Diferenciar evaluación previa al tratamiento y exposición residual si se presentan ambas. No reducir la evaluación por una acción aún no ejecutada sin identificarla como residual prevista.
- [x] [V] Comprobar que categoría, escala, puntuación, prioridad y responsable coinciden con 8.1–8.3.
- [x] [V] Comprobar que el texto del cuerpo sintetiza y analiza el registro completo y lo cita; no pegar el formulario como sustituto del plan.
- [x] [V] No permitir filas con «mitigar», «capacitar», «monitorear» o «CLIENTE» como única respuesta o responsable. Debe existir una acción identificable y un rol ejecutable.

## 5. Cierre de esta parte

Esta parte está cerrada cuando un lector puede reproducir la valoración, identificar qué riesgos requieren acción y seguir cada prioridad hasta un tratamiento concreto. La existencia de una tabla llena no basta si faltan fundamentos, análisis cuantitativo o contingencias.

## Avance de parte 02 · 10 de octubre de 2026

**38 de 40 controles atendidos:** 36 CUMPLE, 2 NO APLICA justificados (árbol de fallas y simulación no seleccionados) y 2 PARCIAL. Las casillas marcadas como no aplicables no acreditan aplicación de esas técnicas: se utiliza FMEA y sensibilidad determinista, conforme a la alternativa de EX 8.2.

Se completan los ocho campos de la matriz oficial para 16 riesgos generales y 18 de innovaciones, sin cambiar sus IDs/P/I/E/propietarios. Se añade trazabilidad por categoría/perspectiva/fuente/paquete y se desarrolla función, causa, efecto y cálculo FMEA. Se distingue la exposición anual de la probabilidad de falla y se cubren dependencias excluidas de contabilidad, autoridad, hardware, obras y terceros.

P02-3.08 y P02-3.10 permanecen abiertos: diez días por campaña no prueban holgura para todos los frentes; T-18 contiene una red global, pero T-15 conserva otra referencia funcional y cargas pendientes. Se comparan márgenes y escenarios sin sumar ni sustituir ambos modelos y sin afirmar cabida de las respuestas. Los tres pendientes de parte 01 se mantienen.

SD8 y T-16 compilan localmente (41 y 31 páginas), sin referencias ?? detectadas. Revisión visual parcial registrada en `.atl/SD8_parte02_2026-10-10/`; revisión humana pendiente. No se auditan ni marcan las partes 03–09.
