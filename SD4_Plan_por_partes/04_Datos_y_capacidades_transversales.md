# SD4 · Informe 2 · Parte 04: Datos y capacidades transversales

Trabajar esta parte como una tarea acotada. Leer primero [00_Indice_y_modo_de_trabajo.md](00_Indice_y_modo_de_trabajo.md) y aplicar las reglas de [01_Bases_y_estructura.md](01_Bases_y_estructura.md). Las partes son una división del plan de trabajo; **no sustituyen los títulos obligatorios del SD4**.

**Entradas y dependencias:** Partes 01–03 y modelo/criterios vigentes de SD5; devolver decisiones sobre datos a ese subdocumento.

**Resultado de esta tarea:** Capacidades transversales y arquitectura de persistencia, analítica, retención, exportación y eliminación conciliadas con SD5.

**Ubicación del contenido:** 4.1 Arquitectura lógica; modelo detallado en SD5 mediante referencias reales.

**Fuentes:** BA, BT, CAS y REV; ubicación de contenidos de EX. Las cinco fuentes originales y sus etiquetas se identifican en la parte 01. No usar esta división para omitir alguna fuente aplicable.

**Criterio de cierre:** aplicar el alcance de B/R/D/C/G definido en la parte 01; registrar ID → sección/figura/tabla/formulario → evidencia → estado real. Una casilla sólo se marca con evidencia existente. Dejar identificados bloqueos, supuestos y cambios que deban propagarse a otras partes. Esta tarea contiene **15 verificaciones originales**.

---

### Capacidades transversales y arquitectura de datos

Además de los módulos de negocio, el diseño debe identificar las capacidades que hacen administrable, auditable y sostenible la plataforma. El detalle del modelo de datos corresponde al SD5.

- [ ] **TR-01.** Incorporar administración de usuarios, roles, permisos, unidades y catálogos por la marina; parametrización versionada de umbrales y reglas; doble aprobación para cambios operacionales; declarar qué requiere desarrollo y qué es realmente configurable. [B · BT RT-16.01/02/03/04]
- [ ] **TR-02.** Incorporar auditoría inalterable consultable/exportable por el cliente, flujos de trabajo con estados, responsables, plazos, delegación y escalamiento, y bandeja unificada de pendientes. Si se ofrece motor de reglas o simulación de parámetros, individualizarlo y explicar su ejecución. [B · BT RT-16.06/07/08/11/12/13]
- [ ] **TR-03.** Diseñar gestión documental con metadatos, versiones, permisos, búsqueda, previsualización, integridad, retención y plantillas administrables. Individualizar el prestador de firma; seleccionar modalidad legal por contrato, autorización de apoderado, recepción/entrega en custodia, acta de izaje y entrega de residuos; conservar certificado, sello de tiempo y evidencia verificable tras su vencimiento. [B · BT RT-16.15/16/17/18/19; CAS RT-16.14]
- [ ] **TR-04.** Incorporar notificaciones asíncronas con plantillas y preferencias versionadas, entregas, aperturas cuando el canal las permita, errores, reintentos y deduplicación; distinguir avisos obligatorios y comerciales y su mecanismo de baja. [B · BT RT-16.20/21/22/23/25; CAS RT-16.21]
- [ ] **TR-05.** Diseñar búsqueda global con indexación, tolerancia a errores y filtros, respetando autorizaciones. Incorporar listados paginados y exportaciones con filtros conservados, sin bloquear la sesión ni exponer información por un índice o caché mal autorizado. [B · BT RT-16.27/28/29/30]
- [ ] **TR-06.** Mostrar el portal público aislado de recursos transaccionales: disponibilidad de visitas, condiciones, tarifas comerciales de la marina como contenido administrable y avisos, sin inventar sus valores. Diseñar autoatención y pagos; portales de armador, apoderado y contratista, en español e inglés donde el caso lo exige. [B · CAS cap. 15, RT-16.30; BT RT-16.34]
- [ ] **TR-07.** Relacionar autoatención con un indicador estimado de reducción de atención asistida, método y supuestos, y con la capacidad/mesa de servicio. No insertar un porcentaje de ahorro sin derivación. [B · BT RT-16.33]
- [ ] **DAT-01.** Individualizar persistencia transaccional, documental, series de consumo, almacenamiento local, caché y capa analítica. Justificar motor y paradigma por dominio, transaccionalidad y elección consistencia/disponibilidad ante particiones, en acuerdo con SD5; CAP no puede quedar explicado únicamente aquí. [B · BT RT-05.02; EX capítulo 5]
- [ ] **DAT-02.** Separar consultas analíticas de transacciones operacionales. Definir alimentación de analítica —eventos/CDC/cargas incrementales—, modelo semántico, autoservicio, profundización al dato de origen, informes abiertos y envío programado. [B · BT RT-05.05/25/26/27/28]
- [ ] **DAT-03.** Mostrar cómo se logran las latencias del caso: ocupación ≤60 s; consumos al menos horarios; estado de cuenta en tiempo real; indicadores ambientales diarios; escuela en tiempo real sin excepción. Explicar los límites durante pérdida de conectividad sin ocultar una contradicción con estos objetivos. [B · CAS cap. 15, RT-05.29]
- [ ] **DAT-04.** Diseñar datos maestros compartidos sin duplicación, claves e identidad de entidades, reglas de validación y mecanismos de calidad ISO/IEC 25012. Referenciar el diccionario completo del SD5 y mostrar aquí el impacto sobre interfaces, consistencia y rendimiento. [B · BT RT-05.01/04/09]
- [ ] **DAT-05.** Conciliar indexación, particionamiento, caché y archivos con el cálculo de capacidad. Explicar protección y expiración de cachés, incluyendo deuda, escuela, autorizaciones y consentimientos, que no pueden mostrar información obsoleta como vigente. [D · EX §11, capítulo 5.4; REV SD5]
- [ ] **DAT-06.** Aplicar técnicamente la retención del caso: escuela de menores hasta 18 años +5, mínimo 10 años; salidas/regresos y zarpe 5 años; contratos/custodia/estado de cuenta 6; residuos/derrames 6; consumos 5; trenes de fondeo vida útil +5; combustible 5; videovigilancia 6 meses. [B · CAS cap. 15, RT-05.10]
- [ ] **DAT-07.** Definir retención de dominios no resueltos por la lista anterior —consentimientos, avisos, acreditaciones, auditoría, contactos, planes y telemetría cruda/agregada—. Respetar auditoría mínima de 5 años cuando no se fije otro plazo y diferenciarla del log de seguridad de 12+24 meses; conservar evidencia de cumplimiento durante todo el contrato y 24 meses adicionales conforme al art. 27; contemplar suspensión de eliminación por litigio. [B · BT RT-05.07 y RT-16.10; BA art. 27; REV SD5]
- [ ] **DAT-08.** Diseñar exportación completa y autoservida en formatos abiertos y eliminación segura verificable en nube, borde, dispositivos, réplicas y respaldos conforme a su ciclo y a retención legal. Explicar cómo se evita restaurar datos ya eliminados legítimamente. [D · BT RT-05.06/07; BA art. 85]
