# SD4 · Informe 2 · Parte 13: Integración, referencias, IA y comprobación final

Trabajar esta parte como una tarea acotada. Leer primero [00_Indice_y_modo_de_trabajo.md](00_Indice_y_modo_de_trabajo.md) y aplicar las reglas de [01_Bases_y_estructura.md](01_Bases_y_estructura.md). Las partes son una división del plan de trabajo; **no sustituyen los títulos obligatorios del SD4**.

**Entradas y dependencias:** Partes 01–12 integradas, referencias vigentes y verificación humana efectivamente realizada antes de declararla.

**Resultado de esta tarea:** SD4 integrado con figuras/cálculos explicados, referencias, declaración fiel de IA y registro de evidencia de las 303 verificaciones.

**Ubicación del contenido:** Todo el cuerpo; Referencias y Declaración de uso de IA al final, en ese orden.

**Fuentes:** BA, BT, CAS, EX y REV. Las cinco fuentes originales y sus etiquetas se identifican en la parte 01. No usar esta división para omitir alguna fuente aplicable.

**Criterio de cierre:** aplicar el alcance de B/R/D/C/G definido en la parte 01; registrar ID → sección/figura/tabla/formulario → evidencia → estado real. Una casilla sólo se marca con evidencia existente. Dejar identificados bloqueos, supuestos y cambios que deban propagarse a otras partes. Esta tarea contiene **22 verificaciones originales**.

---

## Figuras, tablas, referencias y declaración de IA

Este bloque controla la sustancia explicativa del documento. No es una revisión de nombres o formatos de archivos. [EX §§2–7 y 11; BA arts. 4.3/13.5/T-21; REV General]

- [ ] **DOC-01.** Integrar en el cuerpo las vistas exigidas —lógica, procesos, despliegue, datos y seguridad— y figuras que expliquen los asuntos particulares de CAS §17.4, incluidos offline, red, primaria/recuperación y respaldo cuando requieran explicación gráfica. No imponer un número fijo ni una figura independiente por cada casilla: agrupar o dividir conforme a la complejidad, manteniendo contenido legible y explicado. [D · BT RT-02.03; EX §4; CAS §17.4]
- [ ] **DOC-02.** Para cada figura, incluir número, título y fuente; citarla antes y recorrerla después explicando componentes, conexiones, reglas, fallas y conclusión. Si es compleja, preparar vista general y diagramas de detalle independientes; no sustituirlos por recortes/ampliaciones de una misma imagen. [B · EX §4]
- [ ] **DOC-03.** No dejar leyendas sin figura, gráficos genéricos ni diagramas que contradigan el texto/T-11. Todas las flechas deben tener significado verificable —dato/evento/protocolo/dirección cuando corresponde—; no agregar logos o componentes sin papel real en el diseño. [D · EX §§4/7.1; REV General]
- [ ] **DOC-04.** Usar tablas para comparar alternativas, cuantificar, mapear o sintetizar; escribir como prosa las explicaciones de funcionamiento y decisión. Incluir título, fuente, referencia previa y conclusión posterior; trasladar listados completos al detalle sin vaciar el análisis del cuerpo. [B · EX §5]
- [ ] **DOC-05.** Mostrar el cálculo que sustenta cada cifra relevante: entradas, fuente o supuesto, unidad, operación y resultado, con efecto sobre el dimensionamiento o decisión. Analizar sensibilidad o margen cuando sea pertinente o expresamente requerido; no exigir un estudio de sensibilidad independiente para cada cálculo elemental. [D · EX §3; CAS §14; BT RT-09.01]
- [ ] **DOC-06.** Citar en APA 7 donde se usa cada dato/criterio: bases con documento, capítulo/artículo y página original; fuentes técnicas con contribución concreta. Mantener bibliografía con correspondencia bidireccional cita–entrada, sin material de clases como fundamento tecnológico ni fuentes huérfanas. [B · EX §6; REV General]
- [ ] **DOC-07.** Incluir al final **Referencias** y después **Declaración de uso de IA**, ambas sin numerar. La declaración comienza con texto y contiene por sección/anexo/formulario: herramienta, finalidad, nivel de texto, nivel de diagramas y revisión humana —quién y qué verificó—; declarar «Ninguno» donde corresponda y conciliar con A-6. [B · EX §§2/7.2; BA A-6]
- [ ] **DOC-08.** No inventar revisión humana ni atribuir aprobación a integrantes que no revisaron. Indicar fielmente el uso del agente; exigir revisión humana efectiva de arquitectura, cálculos, referencias y coherencia antes de entrega, porque desde Informe 2 las instrucciones sancionan contenido íntegramente generado sin elaboración/revisión y los indicios señalados. [B · EX §7.1/7.2]
- [ ] **DOC-09.** Mantener un revisor distinto del autor para lectura integral y validación cruzada. Los responsables deben poder explicar cada decisión, figura, supuesto y cálculo, incluidos compromisos futuros, sin depender del texto del agente. [R · REV General; EX §7.1]

## Comprobación final antes de dar el SD4 por terminado

Este cierre sirve para que el agente entregue un resultado auditable. No sustituye las casillas de desarrollo ni convierte pendientes en cumplimiento.

- [ ] **FIN-01.** Están desarrollados todos los títulos obligatorios con introducción y análisis; el documento explica la solución de Panitao y no una arquitectura de referencia rebautizada. [D · EX capítulo 4 y §3]
- [ ] **FIN-02.** Existe mapeo del 100 % entre SD3, SD4 lógico/físico y T-11; no quedan componentes sin despliegue, recursos sin función, integraciones sin contrato/falla ni cantidades sin fundamento. [D · EX capítulo 4; BA T-11]
- [ ] **FIN-03.** Los 14 asuntos de CAS §17.4 están resueltos: estado de amarra; 24 h local; reparto nube/local; cobertura flotante; 760 puntos; baja capacidad/mensaje perdido; plan vencido; marejada; escuela; segregación; surtidor; boyas offline; menores; crecimiento y primer cuello de botella. [D · CAS §17.4]
- [ ] **FIN-04.** Las 22 decisiones tienen solución/supuesto fundado, impacto y validación; están especialmente cerradas la 1, la 21 y la 22. Las preguntas a terceros se distinguen de decisiones que correspondía tomar a Synaptix. [D · CAS §17.1; REV SD4.1]
- [ ] **FIN-05.** Se verifican autonomías 24/12/8 h; sincronización ≤30 min; procesos 45/10/90/60 s, marejada ≤10 min y plan vencido ≤15 min; latencias analíticas; RTO ≤4 h/RPO ≤15 min; SLA y pruebas requeridos. Las metas más estrictas están sustentadas y son idénticas en toda la propuesta. [D · CAS cap. 15; BT cap. 7; BA art. 78]
- [ ] **FIN-06.** Hay una sola oferta de tecnologías, protocolos, identidad/MFA, cifrado, regiones, instrumentación y umbrales. Todos los servicios/software/hardware principales tienen soporte y ruta de evolución a 56 meses, incluida reposición de elementos marinos. [D · BT §1.6; EX §3; REV SD4]
- [ ] **FIN-07.** El nodo mínimo funciona sin administración humana normal; las tareas especializadas tienen servicio/responsable y recursos; no se exige un área de TI de la marina ni interacción peligrosa en maniobras. [D · CAS restricciones 1/7 y RT-06.01]
- [ ] **FIN-08.** Hardware y obras del cliente están especificados por ubicación/cantidad y compatibles con ambiente/clasificación; soporte/repuestos/reposición están cuantificados; la oferta económica puede derivar de ellos sin inventar posteriormente cantidades. [D · BT cap. 8; CAS cap. 11]
- [ ] **FIN-09.** Seguridad, datos personales, consentimiento, auditoría, firma, amenazas y recuperación tienen implementación y evidencia; toda IA incorporada está declarada y gobernada. No se confunde el uso de IA para redactar la oferta con IA incluida en el sistema. [D · BT caps. 11/12/18; CAS cap. 15]
- [ ] **FIN-10.** El diseño está conciliado con EDT/meses/recursos, restricciones estacionales y ambientales, riesgos reales y criterios de prueba/aceptación. SD4 no reproduce el cronograma completo ni el plan de calidad, pero sus compromisos están reflejados allí. [D · BA art. 57.2; CAS §17.5]
- [ ] **FIN-11.** La tabla de cierre del Informe 1 tiene respuesta concreta y sección/evidencia por observación; la matriz T-12 apunta al documento vigente y no contiene «Sí» injustificados ni notas de una autoauditoría externa sobre «el PDF revisado». [D · BA art. 46; BT §1.5; REV SD3]
- [ ] **FIN-12.** No quedan placeholders, «por individualizar», alternativas sin decidir, referencias inexistentes, certificaciones inventadas, cifras sin derivación ni montos prohibidos. Los antecedentes externos aún faltantes se reportan con impacto, tratamiento y acción necesaria, sin ocultarlos como cumplimiento. [D · EX §7.1; BT §1.5; BA art. 50.2]
- [ ] **FIN-13.** Como control interno del agente, mantener ID de casilla → ubicación → evidencia → estado real y bloqueos. Este registro de ejecución no es un nuevo anexo ni formulario exigido al SD4; no duplicar T-12 ni la tabla de correcciones. Usarlo para comprobar que no subsisten brechas obligatorias de arquitectura, continuidad o seguridad antes de declarar terminado el trabajo. [G · Guía interna; BT §1.5; BA art. 46]
