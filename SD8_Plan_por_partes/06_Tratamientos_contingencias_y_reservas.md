# Parte 06 · Tratamientos, contingencias y reservas

**Destino:** sección 8.3 y vínculos al T-16. **Fuentes:** EX, 8.3; BA, T-7, T-16 y Arts. 17, 50.2 y 72; BTT, RT-19.04; CASO, caps. 10–13, 17 y 19; REV, SD3–SD5.

## 1. Decisión de tratamiento

La respuesta debe reducir la causa, la probabilidad o el impacto de un riesgo concreto. Nombrar una herramienta o un estándar no demuestra que lo haga.

- [ ] [E] Definir estrategia de mitigación y plan de contingencia para los riesgos registrados. Fuente: BA, T-7, gestión de riesgos.
- [ ] [A] Explicar para cada riesgo prioritario si se evita, se reduce, se comparte/transfiere o se acepta, y por qué. Esta taxonomía es una forma de desarrollar la metodología, no una lista literal impuesta por T-16.
- [ ] [A] Diferenciar control existente, acción preventiva propuesta, contingencia al materializarse y recuperación/retorno posterior.
- [ ] [A] Enlazar cada control con componente, proceso o servicio realmente ofrecido. No usar «respaldo en la nube» ante falla de la única operadora si falta conocimiento de cierre.
- [ ] [A] Si se transfiere parte de la exposición a proveedor, seguro o soporte, declarar qué cubre y qué permanece bajo responsabilidad de Synaptix. No afirmar que la transferencia elimina la obligación contractual.
- [ ] [A] Si se acepta exposición residual, explicar razón, condiciones, seguimiento y autoridad de aceptación. La aceptación no convierte un requisito obligatorio incumplido en admisible.
- [ ] [V] Comprobar que ninguna mitigación exige cámaras sobre niños, dispositivos prohibidos, interacción durante izaje, bloqueo de acceso por mora sin decisión formal o contratación de TI por la marina. Fuente: CASO, cap. 10.

## 2. Acción ejecutable por riesgo

Los campos de plazo y disparador proceden directamente de EX y RT-19.04. Los detalles adicionales permiten que el agente convierta la respuesta en trabajo verificable.

- [ ] [E] Declarar **responsable, plazo y disparador** de cada acción. Fuentes: EX, 8.3; BTT, RT-19.04.
- [ ] [A] Escribir qué se hace, sobre qué objeto y con qué resultado esperado, evitando «monitorear», «capacitar» o «mejorar seguridad» como único contenido.
- [ ] [A] Distinguir propietario del riesgo y ejecutor de la acción; comprobar que estén asignados en el equipo y tengan recursos.
- [ ] [A] Definir plazo como fecha o posición verificable en el cronograma —antes de piloto, corte, certificación o congelamiento— y no sólo «durante el proyecto».
- [ ] [A] Definir disparador observable: prueba fallida, réplica sobre límite declarado, pérdida de enlace, devolución de integración, ausencia del titular, compra retrasada o aviso oficial de marejada.
- [ ] [A] Si se fija un umbral nuevo para activar una respuesta, presentarlo como elección técnica fundada. No atribuirlo a las bases si no existe allí.
- [ ] [A] Identificar recursos y dependencias de ejecución: apoyo funcional, proveedor, repuesto, acceso por mar, turno, información de respaldo y autorización necesaria.
- [ ] [A] Enlazar acción con paquete de EDT, actividad y responsable de SD7/T-14/T-15. La capacidad no se demuestra con una promesa que carece de actividad y dedicación.
- [ ] [A] Definir evidencia de cumplimiento y efecto esperado sobre probabilidad o impacto. Diferenciar resultado previsto y resultado comprobado.
- [ ] [V] Revisar exposición residual tras aplicar el tratamiento y comprobar si requiere una segunda acción o escalamiento.

## 3. Contingencia y retorno

La contingencia debe operar cuando el control preventivo falla, incluido el caso en que la persona o el equipo habitual no están disponibles.

- [ ] [E] Desarrollar un plan de contingencia trazable al riesgo, no sólo una estrategia preventiva. Fuente: BA, T-7.
- [ ] [A] Definir condición de activación, autoridad, secuencia, responsable y comunicación al CLIENTE y usuarios afectados.
- [ ] [A] Identificar el proceso que continúa, la función suspendida, el registro alternativo y el modo de conservar integridad y evidencia.
- [ ] [A] Definir tiempo previsto de ejecución, límites de uso y criterio de retorno; coordinar con BCP/DRP de la parte 07.
- [ ] [A] Explicar cómo se incorporan y concilian las transacciones generadas durante la contingencia sin duplicar, perder ni sobrescribir registros críticos.
- [ ] [A] Para sistema de 2014, asegurar alternativa que no dependa de la presencia de la única operadora. Desarrollar respuesta anterior al mes 21 y cobertura de la convivencia. Fuente: REV, SD3 y SD5.
- [ ] [A] Para piloto de detección de ocupación, definir qué se hace si no logra el criterio de éxito y cómo se preservan registro de presencia/regreso y aceptación. Fuente: REV, SD3, DEC-01 y CA-01/CA-02.
- [ ] [A] Para mensaje de navegación que no llega, definir qué informa la plataforma, qué acción humana se solicita y qué no concluye automáticamente. Fuentes: CASO, 17.4; REV, SD4.1 y SD13.
- [ ] [V] No confundir reversión de una ola de implantación, conmutación a un sitio DR y salida de un proveedor: tienen causas, tiempos y procedimientos distintos.

## 4. Análisis costo-beneficio sin precios de la oferta

EX exige fundamentar las mitigaciones con análisis costo-beneficio y sitúa su valorización en la oferta económica. El SD8 técnico debe mantener un análisis reproducible sin montos ofertados.

- [ ] [E] Fundamentar las estrategias de mitigación en **análisis costo-beneficio**. Fuente: EX, 8.3.
- [ ] [A] Comparar, cuando existan opciones razonables, esfuerzo y complejidad del tratamiento frente a reducción de exposición, continuidad preservada, días recuperados, evidencia protegida o trabajo manual evitado.
- [ ] [A] Usar magnitudes técnicas y relativas fundadas —días, dedicación, horas estimadas, volumen, porcentajes de mejora— sin tarifas ni conversiones que revelen el monto de la oferta.
- [ ] [A] Mostrar método y supuestos y explicar por qué una opción se elige y otra se descarta. Si la evaluación económica necesita montos, remitir su valorización a la oferta económica y mantener en SD8 la decisión técnica y su sustento.
- [ ] [V] No denominar «costo-beneficio» a una lista de ventajas sin comparación de carga o recursos necesarios.
- [ ] [V] No convertir puntuaciones ordinales en dinero ni cuantificar un beneficio como medición ya obtenida cuando es sólo una estimación.

## 5. Reservas de contingencia y de gestión

Las fuentes exigen ambas reservas y su reflejo en el cronograma, pero no fijan porcentajes ni un monto mínimo. El proponente debe declarar su criterio y evitar doble conteo.

- [ ] [E] Incluir **reservas de contingencia y reservas de gestión**. Fuente: EX, 8.3.
- [ ] [A] Explicar qué cubre cada reserva, cómo se dimensiona, quién autoriza usarla y cómo se registra su consumo. La definición adoptada debe ser coherente con la metodología de SD6.
- [ ] [E] Reflejar las reservas en el **cronograma** y trasladar su **valorización a la oferta económica**. Fuente: EX, 8.3 y BA, Art. 50.2.
- [ ] [A] Relacionar contingencias conocidas con riesgos y tareas concretas: reensayo de migración, corrección de piloto, sustitución de equipo o cancelación de faena, según corresponda.
- [ ] [A] Mostrar cuantificación de reserva de plazo y, cuando se utilice, esfuerzo adicional con método, supuestos y recursos. No sumar indiscriminadamente todos los escenarios como si ocurrieran juntos.
- [ ] [E] Mostrar por separado la holgura calculada para marejadas y cómo cabe antes de hitos fijos. Fuente: CASO, 17.5 y cap. 19.
- [ ] [A] Distinguir duración normal de tarea, margen estimativo, holgura de red, reserva y retrabajo ya incluido para evitar computarlos dos veces.
- [ ] [A] Comprobar que recursos o alternativas para consumir reserva existen: una reserva de días no crea una ventana autorizada ni un técnico disponible.
- [ ] [E] No financiar la respuesta desplazando meses de producción, acortando marchas blancas o modificando el cronograma obligatorio. Fuente: BA, Arts. 17 y 72.
- [ ] [V] No usar un porcentaje arbitrario universal de reserva ni «a definir en Informe 3» como sustituto del criterio y efecto técnico que el Informe 2 ya requiere.

## 6. Cierre de esta parte

Un lector debe poder seguir riesgo → tratamiento → responsable → plazo → disparador → actividad/contingencia → evidencia → exposición residual. Las acciones y reservas deben concordar con la capacidad y las ventanas de SD7 y con los planes de continuidad.
