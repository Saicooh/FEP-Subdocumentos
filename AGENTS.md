# AGENTS.md — Criterios de trabajo Synaptix

## 1. Objetivo

Los subdocumentos, anexos, formularios, bibliografías y figuras se redactan
como una oferta profesional de Synaptix para la marina.

La prioridad es:

1. cumplir todas las cláusulas aplicables;
2. mantener coherencia entre documentos;
3. preservar trazabilidad y veracidad;
4. evitar cambios innecesarios;
5. mantener calidad técnica y de presentación.

No se introducen en los entregables referencias a la asignatura, profesor,
estudiantes, empresa ficticia, diálogo con IA ni notas internas.

Las notas de trabajo y control se mantienen en `.atl` y `registros_cambios`.


## 2. Fuentes y cumplimiento

Las fuentes originales prevalecen sobre resúmenes o revisiones anteriores:

- Bases Administrativas;
- Bases Técnicas Transversales;
- bases específicas de la marina;
- instrucciones extras;
- anexos y formularios aplicables.

No inventar cláusulas, requisitos, datos de fabricante, autores, revisores,
certificaciones, mediciones ni pruebas.

La oferta puede fijar decisiones de diseño propias, con supuestos, cálculos y
responsabilidades explícitos, sin presentarlas como características existentes.

Los compromisos futuros no deben presentarse como pruebas, contratos,
certificaciones o instalaciones ya ejecutadas.

Los datos atribuidos a fabricante deben corresponder a variantes reales y
fuentes verificables.


## 3. Coherencia documental

Después de resolver requisitos se comprueba la coherencia necesaria entre
SD1, SD2, SD3, SD4, SD5, SD13 y cualquier otro documento realmente afectado.

No modificar otros SD si no existe una dependencia concreta.

Se permite sustituir modelos o soluciones cuando sea necesario para cumplir,
siempre que la nueva solución sea coherente y verificable.


## 4. T-12

Cada estado T-12 se evalúa por todas sus cláusulas y por el diseño realmente
desarrollado.

No marcar cumplimiento completo con:

- alternativas sin seleccionar;
- cálculos parciales;
- declaraciones genéricas;
- evidencia incompleta.

Se conservan los 576 IDs/enunciados y los 27 complementos específicos.


## 5. IA y personas

José Lara es responsable de las nuevas intervenciones de IA.

Se conservan atribuciones y registros de las demás personas.

No afirmar que José ha revisado técnicamente contenido que todavía no haya
confirmado como revisado.

Un subagente no sustituye el control humano exigido por instrucciones extras
7.1/7.2.

Se mantiene el inventario detallado en T-11 y las síntesis/cálculos en SD4.

No inventar autores ni revisores.


## 6. Procedimiento de revisión de un SD

Cuando se solicite revisar, corregir, completar o cerrar un subdocumento:

### Antes de editar

- identificar archivos del SD;
- identificar anexos y formularios asociados;
- identificar requisitos aplicables;
- consultar las fuentes originales necesarias;
- revisar dependencias reales con otros SD;
- usar una matriz de control existente si la hay.

No comenzar reescribiendo sin haber determinado primero qué debe cumplirse.


### Control de cumplimiento

Para revisiones integrales crear o actualizar:

`registros_cambios/SD##_CONTROL_CUMPLIMIENTO.md`

Cada requisito debe registrar al menos:

- ID;
- fuente y referencia;
- requisito;
- ubicación donde debe cumplirse;
- estado;
- evidencia;
- acción pendiente.

Estados:

- `CUMPLE`
- `PARCIAL`
- `NO CUMPLE`
- `NO APLICA`
- `REQUIERE DECISIÓN`

No marcar `CUMPLE` sin evidencia concreta y localizable.

`NO APLICA` requiere justificación.

Usar `REQUIERE DECISIÓN` cuando falte una decisión, dato verificable o
confirmación humana.


### Corrección

Corregir los `PARCIAL` y `NO CUMPLE` resolubles.

Preferir cambios mínimos, localizados y trazables.

No reescribir contenido correcto sin necesidad.

No inventar información para cerrar un requisito.


### Verificación posterior

Después de editar:

- volver a comprobar los requisitos modificados contra su fuente original;
- confirmar que la evidencia cubre el requisito completo;
- actualizar la matriz;
- revisar posibles regresiones;
- comprobar cifras, unidades, referencias, tablas, anexos y dependencias
  afectadas.

Una modificación no constituye por sí sola evidencia de cumplimiento.


## 7. Iteraciones

Si existe una matriz de control previa:

- usarla como punto de partida;
- conservar sus IDs;
- no repetir innecesariamente toda la auditoría;
- reabrir los controles afectados;
- añadir requisitos omitidos cuando se descubran.

Si el usuario señala que algo está mal:

1. volver a la fuente original;
2. corregir el requisito afectado;
3. actualizar la matriz;
4. comprobar si el mismo tipo de error puede existir en requisitos relacionados.


## 8. Archivos y LaTeX

Los cambios van en las carpetas actuales de cada subdocumento.

No crear copias, ZIP o estructuras alternativas salvo solicitud.

Las figuras activas `coherencia.tex` son dependencias de compilación.

Preservar macros, comandos personalizados, etiquetas, referencias y estructura
LaTeX existente salvo que exista una razón concreta para modificarlos.

Se mantiene abierto el archivo LaTeX que el usuario tenga activo.


## 9. Compilación y revisión visual

La compilación nativa ha fallado previamente por:

`Unable to find standard directories for platform`

No declarar:

- que el PDF compila;
- que el PDF fue verificado;
- que la revisión visual fue realizada;

si esas comprobaciones no ocurrieron realmente.

Si es posible compilar, comprobar errores y revisar visualmente el resultado.


## 10. Cierre

No declarar una revisión integral como terminada mientras existan
`PARCIAL` o `NO CUMPLE` sin resolver.

Los `REQUIERE DECISIÓN` deben informarse explícitamente.

Al finalizar indicar brevemente:

- requisitos revisados;
- incumplimientos encontrados;
- correcciones realizadas;
- pendientes;
- decisiones requeridas;
- archivos modificados;
- estado de compilación y revisión visual.

No usar expresiones como “100 % conforme” o “totalmente verificado” sin
evidencia suficiente.


## 11. Eficiencia

El repositorio contiene documentos extensos.

Preferir:

1. localizar;
2. leer la sección relevante;
3. verificar contra la fuente;
4. modificar;
5. volver a verificar.

Reutilizar matrices, IDs y referencias ya localizadas.

No releer indiscriminadamente todo el repositorio en cada iteración.

Si una modificación tiene efectos transversales, ampliar la revisión solo a las
dependencias afectadas.


## Regla final

El objetivo no es producir muchos cambios.

El objetivo es hacer la menor cantidad de cambios necesaria para obtener una
propuesta completa, coherente, trazable y conforme.

Ante una duda relevante:

**verificar antes de asumir.**