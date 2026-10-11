# Parte 05 · Riesgos del desarrollo y de la implantación

**Destino:** 8.2, T-16 y respuestas de 8.3. **Fuentes:** BA, T-22, Arts. 17–18, 71–72 y 76; EX, 8.2–8.3; BTT, caps. 19–20 y RT-05.11–05.15; CASO, 10–13, 16–17 y Anexo B; REV, SD1, SD3, SD4 y SD5.

## 1. Riesgos de desarrollo del proyecto

El Informe 2 exige una perspectiva de desarrollo reconocible. Debe relacionarse con actividades reales de Synaptix y no con una lista genérica de «atraso, costo y calidad».

- [ ] [E] Desarrollar análisis específico de riesgos del desarrollo, separado analíticamente de los riesgos de solución e implantación. Fuente: BA, T-22.
- [ ] [A] Analizar alcance incompleto, supuestos erróneos, reglas de negocio no acordadas o decisiones técnicas abiertas que afecten construcción y aceptación. Fuentes: CASO, 16.1 y 17.1; REV, SD3.
- [ ] [A] Analizar brecha de conocimiento de náutica deportiva, normativa, combustible y residuos; vincular acciones con especialistas y tareas estimadas, sin copiar las «400 horas» observadas del Informe 1. Fuentes: CASO, 16.2 y RT-15.02; REV, SD1.
- [ ] [A] Analizar rotación o ausencia del equipo clave del adjudicatario, concentración del conocimiento y falta de reemplazo compatible. Referir autorización escrita, perfil equivalente o superior y traslape mínimo de 15 días hábiles de Art. 76.
- [ ] [A] Analizar capacidad insuficiente para integraciones, pruebas, migración, seguridad y acompañamiento simultáneos; comprobar disponibilidad efectiva en T-15, no sólo existencia de roles. Fuentes: BA, Art. 17.2; BTT, 19.2.
- [ ] [A] Analizar pérdida de productividad, defectos, deuda técnica, integración tardía y retrabajo por contratos o ambientes inconsistentes. Relacionar mitigaciones con metodologías de SD6 y controles de SD9.
- [ ] [A] Analizar hallazgos críticos de seguridad o defectos bloqueantes que impidan certificar una etapa; incluir reserva de corrección y tiempo de nueva verificación antes del hito. Fuentes: BTT, cap. 20; BA, Art. 17.3.
- [ ] [A] Analizar demoras de revisión, aprobación o validación funcional por carga de trabajo de la marina, ausencia de contrapartes o decisión societaria no resuelta. Fuentes: EX, 8.2; CASO, 2.4 y cap. 19.
- [ ] [A] Analizar cambios no aprobados, expansión de alcance y acciones de mitigación que alteren la línea base. La respuesta se tramita por control de cambios, con análisis de impacto y aprobación previa. Fuentes: BA, Art. 72; BTT, RT-19.03.
- [ ] [A] Considerar tiempos de revisión y subsanación de entregables: **10 días hábiles** para pronunciamiento del CLIENTE y **10 días hábiles** para subsanar cuando existan observaciones. No asumir aprobación instantánea. Fuente: BA, Art. 18.3.

## 2. Dependencias del CLIENTE y terceros

Las exclusiones del alcance generan dependencias que deben aparecer en riesgo y en la planificación. La solución no puede responder «lo compra el CLIENTE» y omitir el efecto del retraso.

- [ ] [A] Analizar adquisición tardía, cantidad equivocada o no conformidad del hardware que compra el CLIENTE, incluidos medidores, red, lectores y dispositivos de campo. Fuentes: CASO, cap. 11; BTT, cap. 8.
- [ ] [A] Analizar obra civil, canalizaciones, instalación eléctrica, torretas o postación no ejecutadas a tiempo por el CLIENTE; enlazar especificación, entrega y ventana de integración. Fuente: CASO, cap. 11.
- [ ] [A] Analizar permisos, disponibilidad de técnicos, acreditación para faena y conformidad de equipos para atmósfera marina o zona clasificada. Fuentes: CASO, cap. 6 y restricciones 9–10.
- [ ] [A] Analizar interfaces, pruebas o autorizaciones de contabilidad, autoridad, comunicaciones, gestor de residuos, pagos y firma que no dependan de Synaptix. Mantener las competencias de cada tercero. Fuentes: CASO, caps. 5, 11 y RT-05.23.
- [ ] [A] Declarar para dependencias críticas el responsable de coordinación, fecha necesaria, disparador de atraso, efecto sobre EDT y alternativa permitida. Enlazar con riesgos de la parte 03.
- [ ] [V] No cambiar unilateralmente de proveedor, región, alcance o mecanismo contractual para cerrar una dependencia; reflejar el cambio aprobado en toda la propuesta.

## 3. Ventanas, marejadas y reserva de plazo

Las fechas de producción contractuales son fijas. La reserva debe caber dentro de ellas y de las ventanas locales permitidas.

- [ ] [E] Respetar la estructura contractual: desarrollo E1 **meses 1–12**; marcha blanca E1 **13–15**; producción E1 **16**; desarrollo E2 **13–18**; marcha blanca E2 **19–20**; producción E2 **21**; operación **21–56**. Fuente: BA, Art. 17.
- [ ] [A] Analizar riesgo de no sostener simultáneamente marcha blanca E1 y desarrollo E2 en meses **13–15**, y producción E1 con marcha blanca E2 en **19–20**. Relacionar dotación y frentes con T-15. Fuente: BA, Art. 17.2.
- [ ] [E] Incorporar como restricciones las intervenciones prohibidas entre **15 de diciembre y 15 de marzo**, en las **14 fechas náuticas** y en el **varadero** durante campañas de **abril–mayo y septiembre–noviembre**. No aplicar el cierre del varadero automáticamente a todo el recinto. Fuentes: CASO, restricción 11 y 13.2.
- [ ] [E] Analizar suspensión de toda actividad programada por aviso de marejada, recibido con **24–48 horas** y varias veces al año. La respuesta debe absorberla **sin desplazar hitos contractuales**. Fuentes: CASO, restricción 12 y 17.5.
- [ ] [E] Declarar **cuánta holgura** se reserva para esas cancelaciones y **sobre qué base se calcula**. Mostrar el efecto en cronograma y ruta crítica; no usar una frase «se considera holgura». Fuentes: CASO, introducción, 17.5 y cap. 19; EX, 8.3.
- [ ] [A] Declarar como supuestos los datos que el caso no cuantifica: número de cancelaciones, duración y recuperación de ventana. Analizar sensibilidad o escenarios con esos supuestos, sin atribuirlos a un histórico entregado.
- [ ] [A] Considerar que junio–agosto facilita intervenciones en tierra, pero también presenta cancelaciones por marejadas y temporales. Fuente: CASO, Anexo B.2.
- [ ] [A] Analizar instalación de medidores sólo con embarcación desconectada o fuera del agua; coordinar torretas con campañas sin intervenir el varadero congelado. Fuente: CASO, 17.5 y Anexo B.2.
- [ ] [A] Analizar llegada tardía de medición o evidencia ambiental que impida acumular serie antes de temporada 2029. No sustituir serie previa por la promesa de medir desde 2029. Fuentes: CASO, 13.1–13.2 y 17.3.
- [ ] [A] Analizar acceso por mar a boyas, ventanas de navegación, instalación/mantenimiento/reposición aplazados y limitación de logística. Fuente: CASO, RT-21.16.
- [ ] [V] Si no existe fecha de inicio contractual disponible, declarar el supuesto calendario y su validación en SD7. No inventar equivalencias mes–fecha para afirmar que las ventanas ya son compatibles.

## 4. Migración del sistema de 2014 y continuidad administrativa

La revisión exige una contingencia anterior al mes 21 para la única operadora. No basta ampliar la convivencia si ella falta, porque también es quien mantiene el sistema anterior.

- [ ] [A] Analizar indisponibilidad de la operadora antes de extracción, cierre, validación de saldos o corte, incluyendo ausencia anterior al mes 21 si la administración migra en Etapa 2. Fuentes: REV, SD3 y SD5; CASO, cap. 5 y 17.6.
- [ ] [A] Plantear salvaguarda anticipada: documentar cierre y extracción, distribuir conocimiento, verificar respaldo y habilitar un reemplazo funcional o apoyo gestionado. Definir responsable y fecha que no dependan de que la ausencia ya ocurrió.
- [ ] [A] Analizar corrupción del origen, extracción parcial por falta de documentación, historia insuficiente, archivo digital incompleto y errores de transformación. Vincular con volumen y método de migración de SD5. Fuentes: BTT, RT-05.11–05.15; REV, SD5.
- [ ] [A] Proteger el alcance requerido: padrones y contratos vigentes completos, 6 años de pagos y saldos, antecedentes completos de **14 embarcaciones abandonadas**, embarcaciones/invernadas y matrícula de escuela de los últimos 3 años. Fuente: CASO, cap. 15, datos históricos a migrar.
- [ ] [A] Analizar conciliación y trazabilidad de diferencias; definir frecuencia, umbral de detención y decisión antes de aceptar saldos nuevos. No permitir diferencias no explicadas. Fuentes: CASO, 17.6; BTT, RT-05.14; BA, Art. 17.3.
- [ ] [A] Enlazar como controles **dos ensayos completos en Preproducción**, tiempos medidos, conciliación y reversión probada. Presentarlos como actividades futuras salvo evidencia de ejecución. Fuentes: BTT, RT-05.13 y cap. 20; REV, SD5.
- [ ] [A] Analizar corte que exceda ventana, imposibilidad de volver al origen y operaciones nuevas que deban reconciliarse al revertir. Referir el procedimiento concreto de SD5/SD7.

## 5. Implantación, marcha blanca y adopción

La puesta en producción puede fallar aun con software correcto si no hay inventario fiable, respaldo operativo o usuarios preparados.

- [ ] [E] Desarrollar análisis específico del riesgo de implantación. Fuente: BA, T-22.
- [ ] [A] Analizar despliegue masivo que afecte varios procesos a la vez. Relacionar con implantación gradual y reversible por proceso/zona, criterio de avance y tiempo de reversión declarado. Fuentes: CASO, 13.3; BTT, RT-20.01–20.02.
- [ ] [A] Analizar corte con inventario de embarcaciones, esloras o ubicaciones incorrecto. Verificar en terreno antes del corte, considerando el 22 % de amarras mal asignadas. Fuente: CASO, 17.6, punto 3.
- [ ] [A] Analizar incongruencia entre etapas, doble digitación, fuente de verdad duplicada o pérdida de integridad durante convivencia. Fuentes: BA, Art. 17.2; BTT, RT-20.03.
- [ ] [A] Analizar marcha blanca con volumen real insuficiente, indicadores incumplidos, diferencias sin explicar, incidentes abiertos o personal sin capacitación certificada. Relacionar con los criterios copulativos de Art. 17.3.
- [ ] [E] Explicar la respuesta si no se cumplen esos criterios: no autorizar el paso por decisión unilateral; la extensión es a cargo del adjudicatario y no desplaza las fechas de las fases siguientes. Fuente: BA, Art. 17.3.
- [ ] [A] Analizar reversión fallida en mañana de peak: zarpes, escuela, combustible y registro de regreso deben conservar continuidad y datos. Fuentes: CASO, 17.6; REV, SD4.1.
- [ ] [A] Analizar acompañamiento insuficiente en pantalanes/varadero y fines de semana; coordinar dotación, duración y estabilización reforzada con SD7. Fuentes: CASO, 13.3 y 17.6; BTT, RT-20.05–20.06.
- [ ] [A] Analizar capacitación estacional tardía y rechazo de interfaces por uso real; enlazar con parte 04 y con calendario anterior al congelamiento. Fuentes: CASO, RT-22.04 y 17.6.

## 6. Cierre de esta parte

Cada riesgo de plazo debe afectar una actividad o hito identificable. Cada mitigación o reserva debe aparecer en SD7/T-14/T-15/T-18 cuando corresponda. Una contingencia no queda cerrada si depende del mismo recurso único cuya pérdida provoca el riesgo.
