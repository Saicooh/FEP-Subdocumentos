# SD4 · Informe 2 · Índice y modo de trabajo

El checklist original se divide en **13 tareas**, cada una en un Markdown independiente. Se conservan **los 303 IDs de trabajo y todos los bloques temáticos**, con el texto corregido mediante validación contra fuentes, incluidas las cinco fuentes, las 22 decisiones del caso, los cruces de códigos y las correcciones del Informe 1. La división organiza la ejecución sin cambiar el índice obligatorio del SD4. Las casillas distinguen obligaciones, correcciones, desarrollos técnicos, condiciones y guía interna.

## Validación del plan

Leer las etiquetas **B / R / D / C / G** definidas en la parte 01. No tratar todas las 303 casillas como requisitos independientes ni transformar un desarrollo técnico en un producto o entregable obligatorio. La revisión conserva las cinco fuentes y aplica la precedencia de BA arts. 5 y 6.

El [Registro_validacion_de_fuentes.md](Registro_validacion_de_fuentes.md) explica las correcciones y permite comprobar el origen de cada ID. Es un registro de esta validación; no una nueva parte que deba incorporarse al SD4.

## Cómo entregárselo al agente

En la primera tarea, entregar este índice, la parte 01 y las cinco fuentes originales. Pedir que complete 01 antes de comenzar la arquitectura. En cada tarea posterior, entregar el Markdown de esa parte, los entregables previos que requiere y el registro vigente de decisiones/evidencia. Las reglas de 01 siguen aplicando, pero **no hace falta cargar las otras doce partes del checklist en cada turno**.

Las fuentes originales siguen siendo obligatorias. Este paquete divide las instrucciones y no reemplaza las bases ni la revisión. La lectura inicial de las cinco fuentes indicada por R-01 es una guía de ejecución del agente; luego consultar sus apartados pertinentes para fundamentar cada decisión.

## Orden de trabajo

| Parte | Archivo / contenido | Verificaciones |
|---|---|---:|
| 01 | [Fuentes, reglas, estructura e introducción](sandbox:/workspace/scratch/c5c546b6f2a0/SD4_Plan_por_partes/01_Bases_y_estructura.md) | 20 |
| 02 | [Arquitectura lógica e integraciones](sandbox:/workspace/scratch/c5c546b6f2a0/SD4_Plan_por_partes/02_Logica_e_integraciones.md) | 27 |
| 03 | [Seguridad, identidad y privacidad](sandbox:/workspace/scratch/c5c546b6f2a0/SD4_Plan_por_partes/03_Seguridad_y_privacidad.md) | 27 |
| 04 | [Datos y capacidades transversales](sandbox:/workspace/scratch/c5c546b6f2a0/SD4_Plan_por_partes/04_Datos_y_capacidades_transversales.md) | 15 |
| 05 | [Procesos, escenarios e interfaces](sandbox:/workspace/scratch/c5c546b6f2a0/SD4_Plan_por_partes/05_Procesos_e_interfaces.md) | 28 |
| 06 | [Tecnologías de software y observabilidad](sandbox:/workspace/scratch/c5c546b6f2a0/SD4_Plan_por_partes/06_Software_y_observabilidad.md) | 26 |
| 07 | [Infraestructura, ambientes y redes](sandbox:/workspace/scratch/c5c546b6f2a0/SD4_Plan_por_partes/07_Infraestructura_y_redes.md) | 24 |
| 08 | [Operación desconectada y dimensionamiento](sandbox:/workspace/scratch/c5c546b6f2a0/SD4_Plan_por_partes/08_Offline_y_dimensionamiento.md) | 30 |
| 09 | [Implementos, ciclo contractual y portabilidad](sandbox:/workspace/scratch/c5c546b6f2a0/SD4_Plan_por_partes/09_Implementos_y_ciclo_contractual.md) | 30 |
| 10 | [Data centers, alta disponibilidad y recuperación](sandbox:/workspace/scratch/c5c546b6f2a0/SD4_Plan_por_partes/10_Data_centers_y_continuidad.md) | 28 |
| 11 | [Decisiones, supuestos y trazabilidad](sandbox:/workspace/scratch/c5c546b6f2a0/SD4_Plan_por_partes/11_Decisiones_y_trazabilidad.md) | 9 |
| 12 | [Cierre de observaciones del Informe 1](sandbox:/workspace/scratch/c5c546b6f2a0/SD4_Plan_por_partes/12_Correcciones_del_Informe1.md) | 17 |
| 13 | [Integración, referencias, IA y comprobación final](sandbox:/workspace/scratch/c5c546b6f2a0/SD4_Plan_por_partes/13_Integracion_y_revision_final.md) | 22 |
| **Total** | **13 partes** | **303** |

Seguir el orden 01 → 02 → … → 13. Abrir el registro ADR de 11 al empezar 02 y mantenerlo durante todo el trabajo; su cierre se realiza después de 10. Los dimensionamientos de 08 y la continuidad de 10 pueden exigir ajustes en partes anteriores. Propagar esos cambios antes de avanzar al cierre de 11–13. Una dependencia se considera satisfecha por su entregable real, no porque su número aparezca antes en este índice.

## Instrucción reutilizable para cada tarea

> Ejecuta exclusivamente la parte indicada del plan SD4 para el Informe 2. Aplica las reglas y etiquetas B/R/D/C/G de la parte 01, y consulta las cinco fuentes originales según corresponda. Desarrolla contenido técnico concreto para Synaptix/Panitao y ubícalo bajo el índice obligatorio del SD4. Conserva los IDs de las casillas. Marca cada punto sólo con evidencia en el entregable; registra su ubicación y estado real. No inventes verificaciones, certificaciones ni aprobaciones. Si una decisión exige cambiar un entregable previo, incorpora o identifica exactamente el cambio y su impacto. Al finalizar, entrega el contenido de esta parte, su registro de evidencia y un traspaso breve de decisiones, supuestos y pendientes para la siguiente tarea. No declares completo el SD4 mientras falten otras partes.

## Qué conservar entre tareas

Mantener el borrador acumulado del SD4 bajo sus títulos oficiales y un registro de decisiones/ADR, supuestos y evidencia. El traspaso de cada tarea debe ser breve y contener sólo decisiones vigentes, nombres/versiones/regiones/umbrales seleccionados, pendientes con impacto y cambios que deban propagarse. No copiar todo el plan en el traspaso.

Usar estos estados en el registro: **cumplido con evidencia**, **pendiente**, **bloqueado por antecedente externo** o **no aplicable justificado**. La falta de evidencia no se convierte en cumplimiento. El registro mínimo por verificación es:

| ID | Ubicación del contenido | Evidencia concreta | Estado real | Pendiente / dependencia |
|---|---|---|---|---|
| ID original de la casilla | Sección, figura, tabla, anexo o formulario vigente | Decisión, cálculo, contrato, control o evidencia que exige el punto | Uno de los estados anteriores | Acción y efecto, si corresponde |

## Cierre del conjunto

La parte 12 comprueba las observaciones del Informe 1 y devuelve cualquier brecha a su parte responsable. La parte 13 integra y verifica el documento completo. Todas las partes deben terminar en un solo SD4 coherente: mismas tecnologías, cantidades, regiones, protocolos, cifras y compromisos. No añadir trece capítulos al informe ni dejar el resultado como fragmentos aislados.

La comprobación de la división confirmó **303 IDs únicos, sin omisiones ni duplicados**, y correspondencia entre la versión validada y sus partes. Ninguna parte supera las 2.000 palabras.
