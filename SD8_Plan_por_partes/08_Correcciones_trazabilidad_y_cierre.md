# Parte 08 · Correcciones del Informe 1, trazabilidad y cierre

**Destino:** comprobaciones finales del contenido de SD8, tabla de correcciones del Informe 2 y secciones finales. **Fuentes:** BA, Arts. 46–47, T-7 y T-22; EX, secciones 2–8; BTT, 1.5 y RT-19.04; REV, General, SD1, SD3, SD4, SD5, SD13 y Consideraciones transversales.

## 1. Cómo usar la revisión previa

La revisión adjunta evaluó SD1, SD2, SD3, SD4, SD5 y SD13. No existe en esa fuente una evaluación de un SD8 ya entregado. Las observaciones siguientes se incorporan por su efecto sobre riesgos, contingencias y coherencia del Informe 2.

- [ ] [E] Incluir la resolución de observaciones previas en la tabla **observación — respuesta — sección modificada** del Informe 2. Fuente: BA, Art. 46 y T-22.
- [ ] [A] Para cada observación que afecta a SD8, identificar el texto observado en REV, la respuesta concreta, la sección de SD8 y el documento dependiente corregido.
- [ ] [V] No afirmar «corregido» por registrar el defecto como riesgo. Si es un requisito obligatorio o una decisión exigida, debe quedar una solución definida o una no aplicabilidad fundada, además del riesgo residual que corresponda.
- [ ] [V] No usar la revisión como certificación de la tecnología, soporte vigente o disponibilidad actual del proveedor. Sus hallazgos sirven para identificar lo que debe verificarse y corregirse.

## 2. Correcciones que SD8 debe recoger o enlazar

La tabla organiza observaciones verificadas en REV y el contenido que deben producir para este plan. La nomenclatura antigua sólo identifica lo observado; los nombres finales deben proceder de la solución corregida.

| Observación de REV | Tratamiento en SD8 | Parte de trabajo |
|---|---|---|
| SD3: única operadora sin contingencia antes del mes 21. | Riesgo temporal/permanente, salvaguarda anticipada y alternativa durante convivencia; no depender del titular ausente. | 04–07 |
| SD3/SD4: DEC-01 sin decisión de sensor/cobertura ni salida si falla el piloto. | Evaluar tecnología efectivamente elegida, criterio de éxito y contingencia para presencia y regreso. | 03, 04, 06 |
| SD3/SD4: DEC-22 y esfuerzo del CLIENTE con unidades incompatibles. | Usar una dedicación fundada, titular/sustituto y servicio gestionado coherentes, sin asumir 4 h/mes como dato. | 01, 04–06 |
| SD4.1: faltan escenarios de 90 zarpes sin enlace, falla del borde y mensaje satelital que no llega. | Desarrollar fallas y respuestas diferenciadas, con registros y tiempos concretos. | 03, 05, 07 |
| SD4/SD5: sincronización de 10, 30 y «≤10, máximo30» minutos. | Usar un compromiso inequívoco; el máximo del caso es 30 min tras 24 h; un objetivo más exigente requiere sustento y consistencia. | 03, 07 |
| SD3: alerta a 45 min desde ETA y discrepancia sobre gracia. | Definir vencimiento, gracia y momento de alerta; evaluar falsos positivos y omisiones. REV considera defendible 15 min tras fin de gracia si ése es el vencimiento definido. | 03, 04, 07 |
| SD3/SD4: pares de regiones incompatibles, secundaria observada en México. | Reflejar par corregido, residencia, autorización y amenazas comunes; no repetir diseño provisional. | 03, 07 |
| SD4.2: faltan reversibilidad, RAID, CIS/parches y definición de proveedores. | Analizar bloqueo, recuperación local, operación/actualización y dependencia de servicios concretos; enlazar evidencia de SD4. | 03, 06, 07 |
| SD4: ciclo de soporte incompleto y plan de reposición sin vida útil/cantidades. | Analizar fin de soporte a 56 meses, corrosión, flexión, repuestos y tiempo de sustitución. | 03–06 |
| SD4.2: recinto técnico sobredimensionado frente a gabinete mínimo sin TI. | Contingencia proporcional, con servicios y recursos mantenibles; no añadir generador/climatización por defecto. | 03, 07 |
| SD5: migración sin extracción, calendario, tolerancias ni reversión. | Analizar y enlazar plan con dos ensayos, conciliación, corte, reversión y contingencia de la operadora. | 03, 05–07 |
| SD5: retenciones incompletas y protección/auditoría sensibles parciales. | Cubrir pérdida de prueba, divulgación, salud/menores, deuda y borrado; enlazar política corregida. | 03, 07 |
| SD13: sin riesgo de adopción y ambigüedad sobre IA. | Incorporar riesgos de cinco innovaciones actuales y contingencias; aplicar bloque IA sólo si corresponde. | 03, 04, 06 |
| SD1: brecha sectorial y 400 h sin fundamento. | Riesgo de competencias con respuesta y esfuerzo derivado, sin copiar esa cifra. | 05, 06 |
| General: tablas sin análisis, referencias rotas y falta de revisión humana. | Desarrollo explicativo, fuentes trazables y lectura integral por revisor distinto. | 01, 02, 08 |

- [ ] [V] Localizar cada observación en la fuente REV antes de cerrar la respuesta; no convertir los ejemplos de solución sugeridos por el revisor en tecnologías obligatorias.
- [ ] [V] No introducir costos unitarios en SD8 porque REV los pidió en relación con T-11: Art. 50.2 conserva el límite de la oferta técnica y la valorización corresponde al ámbito económico.

## 3. Trazabilidad técnica

El contenido debe permitir comprobar que los riesgos pertenecen al mismo proyecto descrito en los demás subdocumentos.

- [ ] [E] Mantener mapeo explícito entre requerimientos, diseño, implementación y operación. Fuente: BA, T-7, consideraciones transversales; EX, sección 3.
- [ ] [A] Para cada riesgo relevante, enlazar origen, requisito/decisión/supuesto, componente o proceso, actividad/hito, control, acción, responsable y prueba o evidencia.
- [ ] [V] Comprobar nombres y decisiones iguales entre SD3–SD9 y SD13: dispositivo de terreno, protocolo, autenticación, cifrado, regiones, proveedores, motor, autonomía y sincronización.
- [ ] [V] Comprobar que las mitigaciones con trabajo aparecen en EDT y planificación; que tienen personal en T-15; y que la verificación aparece en SD9/T-13/T-17 cuando corresponda.
- [ ] [V] Comprobar que los riesgos y contingencias de cada innovación coinciden con SD13/T-19 y que el componente sigue perteneciendo a la cartera actual.
- [ ] [E] Proporcionar evidencia localizable para los requisitos de riesgo/continuidad que se acrediten en T-12, con sección y prueba prevista; mantener la matriz global en su ámbito correspondiente. Fuente: BTT, 1.5.
- [ ] [V] No marcar «cumple» por una intención futura sin contenido de diseño. Distinguir el plan presentado de la evidencia que se producirá durante ejecución.
- [ ] [V] Verificar referencias cruzadas reales: título, subdocumento y sección deben existir; no conservar numeración antigua después de reorganizar el índice.

## 4. Referencias y fundamentación

La sección final contiene las fuentes que efectivamente sustentan el contenido, y cada cita debe indicar qué dato o decisión respalda.

- [ ] [E] Incluir **Referencias** sin numerar y citar fuentes donde se utilizan, en APA 7. Fuente: EX, sección 6.
- [ ] [E] Asegurar correspondencia completa entre citas y entradas: sin cita huérfana ni fuente listada sin uso.
- [ ] [E] Citar bases por documento, capítulo/artículo y página original cuando se documente la cita final conforme a EX. No inventar folios a partir de números de línea del Markdown.
- [ ] [A] Para riesgo o cálculo, separar dato entregado por CASO, estimación de Synaptix y evidencia externa. Toda cifra debe seguirse hasta su fuente o cálculo.
- [ ] [E] Explicar cómo los estándares invocados se concretan en control y evidencia; no presentarlos como certificaciones institucionales ya obtenidas. Fuente: BA, Art. 4.3.
- [ ] [V] Usar fuentes de industria, documentación o normas para afirmaciones técnicas adicionales que se incorporen al SD8. No usar material de clases como soporte de la oferta profesional. Fuente: REV, General y SD2.

## 5. Declaración de uso de IA: contenido obligatorio

La declaración exige datos reales del trabajo realizado. El agente no puede inventar quién hizo revisión humana ni afirmar que ésta ocurrió si no existe.

- [ ] [E] Colocar **Declaración de uso de IA** sin numerar, después de Referencias, con texto introductorio. Fuente: EX, 7.2.
- [ ] [E] Incluir una fila por sección del capítulo y por cada anexo o formulario asociado, incluido T-16.
- [ ] [E] Incluir **Sección**, **Herramienta**, **Finalidad del uso**, **Nivel en texto**, **Nivel en diagramas** y **Revisión humana —quién y qué verificó—**.
- [ ] [E] Usar niveles **Ninguno, Bajo, Medio o Alto** con el sentido definido en EX, 7.2; distinguir texto y diagramas.
- [ ] [E] Si no hubo IA en una sección, declarar **Ninguno**; si hubo uso sustancial, declararlo sin rebajarlo artificialmente.
- [ ] [E] Consolidar la información con A-6. La declaración no sustituye la revisión humana ni permite entregar contenido íntegramente generado sin elaboración y verificación. Fuente: EX, 7.1–7.2.
- [ ] [V] Retirar del contenido final marcadores, notas del asistente, promesas de insertar figuras, referencias inexistentes y comentarios sobre curso, docente, estudiantes o simulación. Conservar las denominaciones oficiales de las bases.

## 6. Cierre verificable de SD8

Esta lista final comprueba el contenido integrado; no añade tareas de nomenclatura ni formato de entrega.

- [ ] [V] Están desarrollados 8.1, 8.2 y 8.3 y su introducción, sin títulos vacíos.
- [ ] [V] Se localizan análisis de solución, desarrollo e implantación; RBS con cinco categorías; y los cinco focos de EX.
- [ ] [V] Se localizan los siete riesgos señalados por cap. 19 del caso.
- [ ] [V] Hay análisis cualitativo y cuantitativo aplicado y reproducible, con técnica y supuestos declarados.
- [ ] [V] T-16 tiene los ocho campos base y desarrollo trazable de contingencia, plazo y disparador.
- [ ] [V] Las respuestas tienen fundamento costo-beneficio técnico y no contienen precios de la oferta.
- [ ] [V] Reservas de contingencia/gestión y holgura por marejadas están fundadas y reflejadas en SD7 sin alterar hitos.
- [ ] [V] BCP/DRP distingue desconexión, falla local, desastre, respaldo, reconciliación y retorno, con recursos reales.
- [ ] [V] Correcciones previas tienen respuesta y ubicación; se usan decisiones actuales coherentes.
- [ ] [V] Referencias y declaración IA están completas y veraces.
- [ ] [E] Un revisor distinto del autor lee el conjunto y verifica coherencia y fundamentos antes de entrega. Fuente: REV, General, expectativas para Informe 2.
- [ ] [V] El equipo puede explicar las escalas, cálculos, escenarios, reservas y decisiones, sin depender de prosa que no haya verificado. Fuente: EX, 7.1.
