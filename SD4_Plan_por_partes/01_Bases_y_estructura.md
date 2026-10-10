# SD4 · Informe 2 · Parte 01: Fuentes, reglas, estructura e introducción

Trabajar esta parte como una tarea acotada. Leer primero [00_Indice_y_modo_de_trabajo.md](00_Indice_y_modo_de_trabajo.md) y aplicar las reglas de [01_Bases_y_estructura.md](01_Bases_y_estructura.md). Las partes son una división del plan de trabajo; **no sustituyen los títulos obligatorios del SD4**.

**Entradas y dependencias:** Primera tarea. Tener disponibles las cinco fuentes originales.

**Resultado de esta tarea:** Índice obligatorio y borrador de la introducción del capítulo 4; reglas de trabajo y límites de alcance establecidos.

**Ubicación del contenido:** Introducción del capítulo 4 y reglas aplicables a todo el SD4.

**Fuentes:** BA, BT, CAS, EX y REV. Las cinco fuentes originales y sus etiquetas se identifican en la parte 01. No usar esta división para omitir alguna fuente aplicable.

**Criterio de cierre:** aplicar el alcance de B/R/D/C/G definido en la parte 01; registrar ID → sección/figura/tabla/formulario → evidencia → estado real. Una casilla sólo se marca con evidencia existente. Dejar identificados bloqueos, supuestos y cambios que deban propagarse a otras partes. Esta tarea contiene **20 verificaciones originales**.

---

Instrucciones para el agente que redactará o corregirá el **Subdocumento 4: Arquitectura lógica y física de la solución**, para Marina y Club Náutico Bahía Panitao S.A.

Este checklist cruza las **cinco fuentes adjuntas**. Incluye el contenido técnico, los análisis, los cálculos, los diagramas, la trazabilidad y las correcciones exigidas para el Informe 2. Excluye nombres de archivos, ZIP, formatos de entrega, portadas, firmas, foliación, tipografías y otras condiciones de presentación administrativa. La estructura obligatoria, la explicación de figuras y tablas, las referencias y la declaración de IA se conservan porque afectan al contenido y a su acreditación.

## Fuentes y etiquetas

Las etiquetas identifican el origen de cada bloque. La revisión del Informe 1 se usa para cerrar observaciones; no se considera una especificación nueva que sustituya las bases.

| Etiqueta | Fuente adjunta | Aporte al checklist |
|---|---|---|
| BA | FEP01.26 Bases Administrativas TFEP-01-2026-3.md | Arts. 4–6, 14–27, 34, 46–47, 50, 57, 71–79, 83–86 y 91–92; formularios T-7, T-11, T-12, T-21, T-22 y E-25. |
| BT | FEP02.26 Bases Tecnicas Transversales TFEP-01-2026.md | Requisitos de arquitectura, nube y borde, ambientes, integración, infraestructura, capacidad, continuidad, seguridad, identidad, movilidad, observabilidad, sostenibilidad e innovaciones. |
| CAS | Bases_Tecnicas_Caso_07_Puerto_Deportivo.md | Operación y restricciones de Panitao; volumetría; parámetros particulares; 22 decisiones; 14 asuntos arquitectónicos del numeral 17.4; criterios de aceptación. |
| EX | instrucciones_extras.txt | Índice obligatorio y ubicación de contenidos; redacción analítica; integración de diagramas; referencias; declaración de IA; consistencia e innovaciones. |
| REV | Synaptix_G7_Informe1_Revision.md | Observaciones generales, de SD4.1 y SD4.2, y contradicciones con SD3, SD5 y SD13 que deben corregirse en el Informe 2. |

## Cómo interpretar el respaldo de cada casilla

Cada casilla termina con origen y tipo: **B** = exigencia explícita de BA, BT, CAS o EX; **R** = corrección pedida por REV; **D** = desarrollo técnico para acreditar el requisito citado, sin imponer un método único; **C** = sólo si se conserva/ofrece la alternativa o se cumple su condición; **G** = guía interna del agente, sin nuevo entregable formal. No todas las casillas son obligaciones independientes.

Los ejemplos y detalles de implementación admiten alternativas justificadas que satisfagan el requisito y las observaciones. No convertir un método sugerido, producto ilustrativo o requisito deseable en tecnología obligatoria. Los requisitos de ejecución se diseñan/comprometen aquí; las pruebas, certificaciones y contratos futuros no se presentan como ya realizados. SD4 desarrolla arquitectura y referencias de coherencia, sin duplicar documentos completos de datos, metodologías, planificación, riesgos, calidad u operación.

## Instrucción de ejecución y criterio para marcar una casilla

El agente debe desarrollar una propuesta de Synaptix para la marina, con decisiones propias del caso, sin convertir el SD4 en una recopilación de requisitos. Una casilla sólo puede marcarse cuando existe el contenido que exige y se puede señalar dónde está la evidencia.

- [ ] **R-01.** Leer las cinco fuentes completas antes de redactar. No limitarse al apartado «Subdocumento 4» de la revisión: las observaciones generales y las contradicciones con los otros subdocumentos también afectan al SD4. [G · Cinco fuentes adjuntas; instrucción del usuario]
- [ ] **R-02.** Aplicar las obligaciones de las bases y las aclaraciones conjuntamente. Distinguir requisitos obligatorios, requisitos «Según caso» y elementos deseables. Si una exigencia deseable queda comprometida en la propuesta, incluirla en arquitectura, planificación, pruebas y cantidades. [B · BA arts. 5/6; BT §1.4]
- [ ] **R-03.** Distinguir tres situaciones: **decisión de diseño que Synaptix debe tomar ahora**, **supuesto declarado que se validará durante el contrato** y **dato externo no disponible que requiere consulta o evidencia de un tercero**. Una validación futura no puede dejar sin decidir la tecnología, la región, la cantidad de equipos o el mecanismo de continuidad que se ofrece. [D · CAS §17.1; REV SD4.1]
- [ ] **R-04.** No inventar inspecciones, pruebas, certificaciones, contratos, aprobaciones, cotizaciones, proveedores comprometidos ni mediciones realizadas. Describir los diseños y las pruebas futuras como compromisos verificables. Cuando falte un antecedente real, registrar qué falta, cómo se obtiene y qué efecto tiene sobre la factibilidad. [G · EX §7.1; BT §1.5]
- [ ] **R-05.** Mantener un vocabulario único de componentes, módulos, servicios, integraciones, regiones, protocolos, versiones y umbrales en SD3, SD4, SD5, SD6, SD7, SD8, SD9, SD13 y los formularios relacionados. No asumir que las decisiones del Informe 1 siguen vigentes sin conciliarlas. [B · EX §3; BA art. 57.2]
- [ ] **R-06.** No incorporar precios, tarifas, costos unitarios ni montos que permitan inferir la oferta económica. Para hardware, nube, comunicaciones, reposiciones, licencias y operación, desarrollar aquí cantidades, frecuencias, recursos, responsables y dependencias de costeo; reservar los valores monetarios para la oferta económica. Esta regla también alcanza al T-11 y a los anexos técnicos. [BA art. 50.2; EX §3] [B · BA art. 50.2; EX §3]
- [ ] **R-07.** Tratar explícitamente la contradicción de costos: BT RT-08.10 y REV piden costo unitario estimado; BA art. 50.2 y el encabezado de formularios técnicos prohíben precios en la oferta técnica. Mantener la especificación completa y la correspondencia con el ítem económico, sin publicar allí el monto. Registrar la discrepancia para aclaración formal; no convertirla en una excepción a la prohibición. [B · BA art. 5.4; BT RT-08.10]
- [ ] **R-08.** No copiar literalmente de REV la supuesta estructura de «cinco columnas» del T-11: el formulario original de BA contiene **N°, Categoría / Tipo, Producto / servicio ofertado, Ubicación / Lugar, Cantidad y Justificación técnica**. Usar esos campos y complementarlos con las especificaciones y el ciclo de soporte. [R · BA T-11; REV SD4.2]
- [ ] **R-09.** Conservar las denominaciones oficiales de las bases al citarlas. Eliminar del desarrollo comercial referencias al docente, al curso, a los estudiantes, a la simulación y al diálogo con el asistente. Usar bibliografía de industria para fundamentar decisiones técnicas. [R · REV General; EX §§3/7.1]
- [ ] **R-10.** Desarrollar ahora la arquitectura necesaria para evaluar el Informe 2. No posponer al Informe 3 las decisiones de diseño, el hardware, la continuidad, el soporte de tecnologías o la incorporación arquitectónica de innovaciones. La valorización monetaria tiene su instancia económica; la definición técnica no se difiere por esa razón. [BA T-22; REV] [B · BA T-22; REV SD4.1/4.2]

## Estructura que debe tener el SD4

El documento resultante debe conservar los siguientes títulos, numeración y orden de EX §11. Los bloques de este checklist son instrucciones de trabajo, no capítulos adicionales que deban agregarse al índice del SD4.

```text
Capítulo 4 · Introducción a la Arquitectura lógica y física de la solución
4.1 Arquitectura lógica
4.1.1 Especificaciones Tecnologías de Software a utilizar
4.2 Arquitectura física
4.2.1 Especificaciones Implementos a proveer (Hardware y Software)
4.3 Data center
4.3.1 Especificaciones Data Center Primaria
4.3.2 Especificaciones Data Center Secundario
Referencias
Declaración de uso de IA
```

- [ ] **E-01.** Desarrollar todos los títulos anteriores. No renombrarlos, omitirlos, fusionarlos ni reordenarlos. Agregar sólo subtítulos de menor nivel cuando sean necesarios; no crear un 4.4, 4.5 u otro título del mismo nivel. [B · EX §§2/11]
- [ ] **E-02.** Bajo cada título, incluir primero un texto que introduzca y explique el contenido. Ningún título debe quedar seguido directamente de otro título, una figura, una tabla o una lista sin introducción. [B · EX §3]
- [ ] **E-03.** Mantener el análisis y las conclusiones en el cuerpo del SD4. Llevar los inventarios extensos, matrices detalladas, ADR y cálculos de detalle a sus anexos o formularios, con referencias explícitas. No trasladar toda la explicación ni todas las figuras a anexos. [B · EX §§3/4; BA T-21]
- [ ] **E-04.** Si alguna materia no aplica, mantener el título y justificar la no aplicabilidad con el proceso del caso, la tipología adoptada y la cobertura alternativa. No aceptar un título vacío ni la frase aislada «no aplica». [B · EX §2]

## Introducción del capítulo 4

La introducción debe permitir entender qué arquitectura se ofrece, qué necesidades de Panitao resuelve y cómo se relaciona con el resto de la propuesta. [EX §11; BA T-7/T-21/T-22; CAS caps. 1, 6, 9 y 19; REV General]

- [ ] **I-01.** Presentar el propósito del SD4: demostrar cómo la solución satisface el alcance y los requisitos mediante una arquitectura lógica, física, de integración, de datos, de seguridad y de despliegue verificable. [D · BA T-7; EX capítulo 4]
- [ ] **I-02.** Explicar el modelo híbrido obligatorio: carga principal en nube y componente local mínimo que permite continuar procesos críticos sin conexión exterior. Justificar su adecuación a una marina que no tiene ni tendrá personal de TI. [D · BA art. 16; CAS §§9.11/15]
- [ ] **I-03.** Identificar las condiciones que gobiernan el diseño: custodia de embarcaciones; 470 menores; cinco negocios; pantalanes flotantes; salinidad y cableado en flexión; surtidor clasificado; boyas remotas; radio marítima; estacionalidad y avisos de marejada. [D · CAS §§6/10/17.4]
- [ ] **I-04.** Explicar la relación con SD3 —alcance, modelo conceptual y requerimientos—, SD5 —modelo y gestión de datos—, SD6 —metodologías—, SD7 —EDT e implantación—, SD8 —riesgos—, SD9 —pruebas— y SD13 —innovaciones—. Citar el T-11 y los anexos de arquitectura donde efectivamente se usen. [D · EX §§2/11; BA art. 57.2]
- [ ] **I-05.** Diferenciar el modelo conceptual de solución del SD3 y la arquitectura del SD4. El SD3 debe tener su propio esquema; el SD4 debe profundizar capas, interfaces, despliegue y mecanismos técnicos, manteniendo correspondencia total. [R · EX §§11, capítulos 3/4; REV SD4.1]
- [ ] **I-06.** Resumir las decisiones principales ya adoptadas y las correcciones sustantivas del Informe 1. No narrar aquí toda la historia del proyecto ni reproducir el diagnóstico completo del SD2. [R · BA art. 46; EX capítulo 4]

## Alcance de esta lista respecto del resto del Informe 2

Este checklist exige **contenido del SD4 y sus soportes técnicos**, más sus interfaces de coherencia con los demás documentos. No exige redactar dentro del SD4 los otros nueve subdocumentos del Informe 2 ni la oferta económica. Tampoco exige producir ahora el video final o el prototipo interactivo que BT sitúa en Informe 3.

Las obligaciones corporativas, del equipo, de planificación, de riesgos y de calidad deben acreditarse en su lugar correspondiente. Cuando afecten la factibilidad de la arquitectura —socio de nube, roles especializados, soporte, marcha blanca, recursos, pruebas—, SD4 debe identificar la dependencia y citar contenido existente y verificable, sin usar una referencia futura como sustituto de la decisión actual.

**Resultado esperado:** un SD4 con arquitectura completa, coherente, dimensionada y verificable para Panitao, con las observaciones del Informe 1 corregidas, decisiones concretas, T-11 completo y correspondencia demostrable con alcance, datos, planificación, riesgos, pruebas, innovaciones y posterior costeo.
