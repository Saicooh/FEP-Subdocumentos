# Parte 03 · Riesgos técnicos, datos y seguridad

**Destino:** análisis de 8.2 y riesgos asociados del T-16; acciones en 8.3. **Fuentes:** EX, 8.2; BA, Arts. 16 y 19–25; BTT, caps. 2–5, 7–12 y 18; CASO, caps. 5–6, 14–16 y 17.4; REV, SD3, SD4 y SD5. Los escenarios [A] se analizan sobre la arquitectura corregida: no son un catálogo para copiar literalmente.

## 1. Arquitectura, conectividad y dependencia de proveedores

La valoración debe identificar qué proceso de Panitao falla y qué evidencia o transacción puede perderse.

- [x] [E] Evaluar **obsolescencia, bloqueo por proveedor, escalabilidad y ciberseguridad**. Fuente: EX, 8.2.
- [x] [A] Analizar caída del enlace principal, falla del enlace de respaldo y falla común de ambos por rutas, proveedor o infraestructura compartida. Contrastar con caminos y proveedores distintos y conmutación automática. Fuentes: BA, Art. 16.4; BTT, RT-03.17; CASO, cap. 6.
- [x] [A] Analizar cobertura insuficiente en los cinco pantalanes y varadero; cambios con marea, oleaje y flexión; y ausencia de cobertura durante trabajo de campo. Fuentes: CASO, cap. 6 y cap. 15, red operacional.
- [x] [A] Analizar falla de nodo de borde, disco, alimentación, red local o redundancia, incluyendo falla de ambos nodos si la solución los incorpora. No confundir perder Internet con perder el sistema local. Fuentes: BTT, RT-02.11, RT-03.10–03.16; REV, SD4.1.
- [x] [A] Identificar puntos únicos de falla que subsistan, su efecto y el tratamiento o justificación concreta. Considerar dependencias físicas y humanas además de equipos informáticos. Fuente: BTT, RT-02.11; REV, Consideraciones transversales.
- [x] [A] Analizar corte de energía, calor, humedad o acceso indebido al gabinete actual; considerar que la bomba de agua depende de energía y que no hay personal TI local. No añadir automáticamente un centro de datos completo como respuesta. Fuentes: CASO, cap. 6 y RT-06.01; REV, SD4.2.
- [x] [A] Analizar falla de zona o región, retraso de réplica y evento que afecte principal y secundario. El análisis de amenazas comunes debe usar el par de sitios efectivamente propuesto. Fuentes: BTT, RT-07.02–07.04; REV, SD4.2.
- [x] [A] Analizar servicios o regiones cuya disponibilidad no esté acreditada, cambios de condiciones de un proveedor y dependencia de una expansión futura. No usar una región futura como contingencia actual. Fuentes: BTT, 1.6 y RT-03.01; REV, SD4.1 y SD4.2.
- [x] [A] Analizar portabilidad real de datos, aplicación, identidades, mensajería e infraestructura; señalar qué no es portable y qué esfuerzo exige cambiar de proveedor. Fuentes: BA, Art. 16.3 y Art. 77; BTT, RT-03.07.
- [x] [A] Evaluar versiones que pierdan soporte antes del mes 56 y la posibilidad de que una actualización rompa integraciones o no quepa en las ventanas autorizadas. Relacionar con el plan de actualización y reposición, sin trasladar ese riesgo al CLIENTE. Fuente: BTT, 1.6; REV, SD4.1.

## 2. Capacidad, desempeño e integraciones

El volumen total moderado no elimina el riesgo del peak simultáneo ni el de una dependencia externa saturada.

- [ ] [A] Evaluar saturación de APIs, base de datos, colas, enlaces, red radioeléctrica, canal de notificación o atención humana. Identificar cuál limita primero la solución, según el dimensionamiento de SD4. Fuentes: BTT, RT-09.01–09.09; CASO, 14.2; REV, SD4.1.
- [x] [A] Analizar el peak de una mañana de fin de semana largo con hasta 90 zarpes, visitantes y clases simultáneas. No repartir la demanda uniformemente por el año para valorar el riesgo. Fuentes: CASO, 14.2 y Anexo B.1.
- [x] [A] Analizar crecimiento y telemetría: frecuencia de lectura, acumulación local durante desconexión, ráfaga al reconectar y contención con tareas analíticas. Fuentes: CASO, 14.1–14.2; BTT, RT-05.05 y RT-09.03–09.09.
- [x] [A] Relacionar el riesgo de crecimiento con **tres veces la volumetría inicial** en tres años exigido por BTT; distinguirlo de la ampliación evaluada a 380 amarras y 70 boyas, que no es una ampliación ya aprobada. Fuentes: BTT, RT-09.03; CASO, 13.2 y RT-02.12.
- [x] [A] Analizar caída, error, lentitud, cambio de formato o límite de uso en contabilidad, autoridad, meteorología, notificaciones, pagos, firma, residuos y demás integraciones realmente comprometidas. Fuentes: BTT, RT-05.17, RT-05.20–05.23 y RT-10.08.
- [x] [A] Para cada dependencia crítica, vincular el riesgo con comportamiento en falla: espera acotada, cola, reintento, deduplicación, degradación o procedimiento alternativo, según diseño. No inventar una API oficial disponible. Fuentes: BTT, RT-02.06–02.09; CASO, RT-05.23; REV, SD4.1 y SD5.
- [x] [A] Evaluar recepción tardía, desordenada, repetida o inexistente de mensajes de baja capacidad desde navegación; distinguir hora del hecho y hora de recepción para impedir cierre falso del regreso. Fuentes: CASO, 14.2, 17.4 puntos 6–7; REV, SD4.1.
- [x] [A] Evaluar conflicto entre nube y borde, duplicación de hechos facturables, pérdida de despacho, sobrescritura de asistencia o cierre de deuda erróneo. Referir reglas deterministas e idempotencia de SD4/SD5. Fuentes: BTT, RT-03.11–03.13; CASO, RT-03.13 y 17.6.

## 3. Datos, privacidad y evidencia

La valoración debe diferenciar pérdida, corrupción, divulgación y falta de prueba. Una copia existente no demuestra que sea recuperable ni suficiente como evidencia.

- [x] [A] Analizar extracción incompleta, duplicados, cambios de identidad, propiedad o saldos durante migración del sistema de 2014; enlazar con la parte 05. Fuentes: CASO, cap. 5 y RT-05.15; REV, SD5.
- [x] [A] Analizar consulta no autorizada a salud y datos de menores, deudas, contactos, datos de tripulantes y contratistas, y posición compartida voluntariamente. Fuentes: CASO, RT-11.10 y RT-16.09; BA, Art. 85.
- [x] [A] Evaluar pérdida de mínimos de visibilidad por cambios de rol, personal estacional, credenciales compartidas o acceso de terceros. Relacionar con los controles reales de identidad, privilegio mínimo, cifrado de campo y auditoría. Fuentes: BTT, RT-11.10 y cap. 12; CASO, decisiones 8 y 22.
- [x] [A] Analizar consentimiento inexistente, no verificable o revocado que siga habilitando datos voluntarios de navegación. La falta de consentimiento no puede resolverse imponiendo seguimiento. Fuentes: CASO, restricción 2, 16.1 y 17.6.
- [x] [A] Analizar pérdida o alteración de autorizaciones, avisos y acuses, planes de izaje, actas ambientales, estado de cuenta y expedientes de las 14 embarcaciones abandonadas. Fuentes: CASO, caps. 12, 15 y 18; BTT, RT-05.03.
- [x] [A] Analizar retención insuficiente o eliminación incorrecta, incluida la propagación a respaldos y borde y las obligaciones probatorias del caso. No fijar plazos nuevos sin fundamento. Fuentes: CASO, cap. 15, retención; BTT, RT-05.07; REV, SD5.
- [x] [A] Analizar pérdida de claves, certificados vencidos y falta de acceso a claves de respaldo durante una contingencia. Referir custodia, rotación y separación de funciones definidas. Fuentes: BA, Art. 21; BTT, RT-07.10 y RT-11.08–11.09.
- [x] [A] Analizar tratamiento o transferencia de datos personales por proveedores sin autorizaciones y resguardos adecuados. La residencia y permisos deben concordar con la arquitectura corregida. Fuentes: BA, Arts. 23 y 85; REV, SD4.2.

## 4. Ciberseguridad y desarrollo seguro

SD8 debe conectar amenazas, consecuencias y tratamiento con el modelado de amenazas y el plan de seguridad de la solución. No sustituirlos por una frase genérica sobre ataques.

- [x] [E] Considerar el modelado de amenazas por componente e integración y actualizarlo ante cambios relevantes. Referir el desarrollo técnico donde corresponda. Fuentes: BA, Art. 21.1; BTT, RT-11.02.
- [x] [A] Analizar ransomware, denegación de servicio, abuso de API, acceso privilegiado indebido, fuga de secretos y compromiso de dispositivos; vincular cada escenario pertinente con el proceso de negocio afectado.
- [x] [A] Analizar extensión de un compromiso desde la red de socios o cámaras a la operacional por segmentación insuficiente. Fuentes: CASO, cap. 6; BTT, RT-03.04 y RT-03.23.
- [x] [A] Analizar una dependencia vulnerable o artefacto alterado que llegue a producción. Relacionar con SAST/SCA/DAST, escaneo, SBOM, firma y procedencia, y aprobación de dependencias. Fuentes: BA, Art. 21.4; BTT, RT-11.22–11.27.
- [x] [A] Analizar exposición de datos productivos en desarrollo o pruebas, o acceso directo no controlado a producción. Fuente: BTT, RT-11.25 y RT-11.27.
- [x] [E] Alinear el tratamiento de vulnerabilidades con máximos de **7 días corridos para críticas, 15 para altas y 30 para medias**, desde publicación o detección. No confundir estos plazos con la respuesta a un incidente. Fuentes: BA, Art. 21.1; BTT, RT-11.04.
- [x] [E] Articular contingencias de seguridad con comunicación de incidente crítico al CLIENTE en **2 horas**, notificación de brecha en **24 horas** e informe de causa raíz en **5 días hábiles**. Fuentes: BA, Art. 21.3; BTT, RT-11.18–11.19.
- [x] [A] Evaluar falta de detección o evidencia: puntos ciegos nube/borde, logs alterados, alertas sin respuesta y SOC sin capacidad efectiva. Referir controles de observabilidad, SIEM, registros y cobertura del servicio. Fuentes: BTT, RT-03.16 y RT-11.14–11.17.

## 5. Inteligencia artificial: bloque condicional

Este bloque depende de una declaración inequívoca de la solución. No es obligatorio incorporar IA ni presentar reglas deterministas como IA.

- [x] [V] Comprobar que SD4 y SD13 declaran si incorporan IA y que SD8 usa la misma decisión. Fuente: REV, SD13.
- [x] [C] Si hay IA, evaluar **sesgo, alucinación, fuga de información y uso indebido**, conforme a NIST AI RMF 1.0 e ISO/IEC 42001. Fuentes: BA, Art. 86; BTT, RT-18.04.
- [ ] [C] Vincular riesgos con propósito, límites, supervisión humana, datos y ubicación de procesamiento; impedir entrenamiento de terceros sin autorización y conservar trazabilidad de decisiones. Fuentes: BTT, RT-18.01–18.05.
- [x] [C] Definir desactivación y respaldo manual sin comprometer el resto de la solución; si hay predicción, considerar deriva, desempeño y reentrenamiento. Fuentes: BTT, RT-18.06–18.09.
- [x] [C] Si una innovación modifica la arquitectura de seguridad, enlazar su modelado de amenazas propio. Fuente: BTT, RT-26.07.
- [x] [V] Si no hay IA, justificar esa no aplicabilidad sin añadir una nueva funcionalidad de IA para llenar el plan.

## 6. Cierre de esta parte

Para cada escenario aplicable debe existir un riesgo evaluado o una justificación de cobertura en otro riesgo, junto con tratamiento y contingencia. Los controles técnicos se refieren por nombre y sección de la solución actual; no se declaran probados sólo porque aparecían en el Informe 1.

## Avance de parte 03 · 10 de octubre de 2026

**38 de 40 controles atendidos:** 37 CUMPLE, 1 NO APLICA justificado (la condición de no incorporar IA no corresponde), 1 PARCIAL y 1 REQUIERE DECISIÓN. Se desarrollan 34 escenarios técnicos vinculados a riesgos existentes, con valoración heredada, causa/efecto, tratamiento, contingencia y control actual; no se crean reservas ni puntuaciones adicionales.

P03-2.01 requiere identificar el primer recurso limitante con una mezcla/carga conjunta coherente SD4/SD5/T-15. P03-5.03 requiere comprobar región/configuración de Textract y condiciones de no entrenamiento/tratamiento antes de enviar documentos del CLIENTE. Las remisiones a controles y pruebas previstas no acreditan eficacia ejecutada ni certificación del componente IA.

Se concretan remediación de vulnerabilidades 7/15/30 días corridos; aviso crítico en 2 horas, brecha en 24 horas y causa raíz en 5 días hábiles. Se conservan los pendientes de partes 01/02. SD8/T-16 compilan localmente (49/33 páginas), sin referencias ?? detectadas; revisión visual parcial y revisión humana pendiente. Evidencias en `.atl/SD8_parte03_2026-10-10/`. No se ejecuta parte 04.
