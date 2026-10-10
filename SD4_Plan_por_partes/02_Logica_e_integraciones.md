# SD4 · Informe 2 · Parte 02: Arquitectura lógica e integraciones

Trabajar esta parte como una tarea acotada. Leer primero [00_Indice_y_modo_de_trabajo.md](00_Indice_y_modo_de_trabajo.md) y aplicar las reglas de [01_Bases_y_estructura.md](01_Bases_y_estructura.md). Las partes son una división del plan de trabajo; **no sustituyen los títulos obligatorios del SD4**.

**Entradas y dependencias:** Parte 01; alcance y componentes vigentes de SD3. Abrir el registro de decisiones que se completa en la parte 11.

**Resultado de esta tarea:** Descomposición lógica, comparación de estilos, vistas y catálogo de integraciones con contratos y manejo de fallas.

**Ubicación del contenido:** 4.1 Arquitectura lógica; detalle de interfaces en anexos referenciados.

**Fuentes:** BA, BT, CAS y REV; estructura de EX. Las cinco fuentes originales y sus etiquetas se identifican en la parte 01. No usar esta división para omitir alguna fuente aplicable.

**Criterio de cierre:** aplicar el alcance de B/R/D/C/G definido en la parte 01; registrar ID → sección/figura/tabla/formulario → evidencia → estado real. Una casilla sólo se marca con evidencia existente. Dejar identificados bloqueos, supuestos y cambios que deban propagarse a otras partes. Esta tarea contiene **27 verificaciones originales**.

---

## 4.1 Arquitectura lógica

Este apartado debe explicar cómo se descompone la solución y cómo colaboran sus componentes. Los diagramas deben corresponder a Panitao y permitir seguir sus procesos críticos. [BA arts. 4.3 y 19–27, T-7/T-21; BT caps. 2, 5, 11–14 y 16–18; CAS §§16.1 y 17.4; REV SD4.1]

### Capas, módulos, responsabilidades y vistas

La descomposición debe mostrar qué hace cada componente, qué información utiliza y qué interfaces ofrece o consume.

- [ ] **L-01.** Declarar el estilo arquitectónico escogido y compararlo con **al menos otra alternativa**. Evaluar complejidad operacional, carga del caso, competencias y tamaño del equipo, evolución, despliegue independiente, recursos y capacidad de mantenerlo sin TI interna. No justificar un estilo por moda. [B · BT §2.3]
- [ ] **L-02.** Si se conserva el monolito modular del Informe 1, demostrar que sus componentes críticos pueden desplegarse de forma independiente. Si se mantienen Marina-Ops, Marina-Log y Marina-Admin, explicar sus fronteras y unidades de despliegue; la etiqueta «modular» no acredita por sí sola RT-02.02. [C · BT RT-02.02; REV SD4.1]
- [ ] **L-03.** Representar las **ocho capas obligatorias**: Presentación; Borde y exposición; Puerta de enlace de servicios; Servicios de negocio; Integración y eventos; Datos; Seguridad transversal; Observabilidad transversal. Identificar componentes e interfaces en cada una. [BT §2.1, RT-02.01] [B · BT §2.1 y RT-02.01]
- [ ] **L-04.** Demostrar que presentación no contiene lógica de negocio ni accede directamente a la base de datos; que la única entrada pública es el borde; y que el API gateway gobierna la publicación de servicios. [B · BT §2.1]
- [ ] **L-05.** Definir por cada módulo su límite de contexto, responsabilidades, entradas, salidas, dueño de datos, operaciones, eventos, interfaces y dependencias. Explicar bajo acoplamiento, alta cohesión, separación de responsabilidades y aplicación concreta de SOLID y diseño orientado al dominio. [D · EX capítulo 4; REV SD4.1]
- [ ] **L-06.** Cubrir, con los nombres definitivos del SD3, navegación y planes; alertas y marejadas; escuela; amarras y visitantes; invernada y varadero; contratistas; ambiente y residuos; consumos; boyas e inspecciones; contratos, facturación y cobranza; administración; identidad y autorización. Si se reorganizan los doce dominios del Informe 1, explicar el cambio y actualizar toda la trazabilidad. [D · CAS §§9/17; EX capítulo 4]
- [ ] **L-07.** Incorporar un modelo de dominio con entidades principales, relaciones y eventos que cambian sus estados. Mostrar las correspondencias entre Embarcación, Amarra, Contrato, Estadía/Recalada, Salida, Regreso, Plan de navegación, Alumno, Clase, Monitor, Medidor, Consumo, Residuo y Boya, entre otras necesarias; conciliarlo con SD5. [B · BT RT-02.13]
- [ ] **L-08.** Presentar las cinco vistas que exigen BA art. 19 y BT RT-02.03 al describir la arquitectura conforme a ISO/IEC/IEEE 42010: lógica, procesos, despliegue, datos y seguridad. Explicar qué preocupación del caso responde cada vista y su relación con 4.2. No atribuir a la norma, por sí sola, la imposición universal de ese conjunto de cinco vistas. [B · BA art. 19; BT RT-02.03]
- [ ] **L-09.** Declarar TOGAF o el marco equivalente de gobierno arquitectónico adoptado, su aplicación al proyecto y su relación con el Comité de Arquitectura. Explicar qué decisiones y revisiones gobierna; no limitarse a nombrar el framework. [BA arts. 4.3 y 71] [B · BA arts. 4.3/71]
- [ ] **L-10.** Explicar orquestación y coreografía en los flujos donde se utilicen, con participantes, estados y eventos. Distinguir transacciones locales, consistencia entre módulos y compensaciones cuando una operación distribuida no concluye. [D · BT §2.1; REV SD4.1]
- [ ] **L-11.** Mantener servicios de negocio sin estado; ubicar las sesiones y estados de proceso en almacenes externos con alta disponibilidad. No confundir la ausencia de estado en servicios con la necesidad de persistencia local del borde. [B · BT RT-02.05]
- [ ] **L-12.** Mostrar cómo nuevos pantalanes, amarras, puestos de invernada y boyas se incorporan por parametrización sin rediseño ni intervención de un especialista. Considerar 380 amarras y 70 boyas, y las proyecciones del caso. [B · CAS cap. 15, RT-02.12]

### Arquitectura de integración

El diseño debe identificar sistemas reales del caso, contratos y mecanismos de falla, evitando ofrecer interfaces inexistentes como si estuvieran verificadas.

- [ ] **INT-01.** Inventariar todas las integraciones internas y externas: contable y DTE; preparación de zarpe y canales de la autoridad; avisos meteorológicos y estación existente; accesos y 38 cámaras/NVR; submedición; surtidor; boyas; pagos; SMS; mensajería instantánea; correo; notificaciones de aplicación; firma electrónica; residuos y autoridad sanitaria; canal de baja capacidad. Unificar los nombres entre SD4 y SD5. [D · CAS §§15/17.4; REV SD4.1]
- [ ] **INT-02.** Para cada integración, definir emisor/receptor, dato o evento, modalidad síncrona/asíncrona, dirección, protocolo, autenticación, versión de contrato, volumen normal y peak, disponibilidad de la contraparte, latencia, reintentos, deduplicación, errores, recuperación y responsable. [D · BT RT-05.21; CAS §14.2]
- [ ] **INT-03.** Individualizar productos y protocolos efectivamente seleccionados. No copiar Wiegand/OSDP, Modbus, ONVIF/RTSP, MQTT o protocolos propietarios como alternativas simultáneas sin decidir qué equipo usa cada uno ni cómo se conecta de forma segura. [D · BT §1.5; REV SD4.1]
- [ ] **INT-04.** Documentar servicios síncronos con OpenAPI 3.1 y eventos con AsyncAPI 2.6 o superior. Presentar contratos representativos suficientes para evaluar el diseño, el catálogo y el mecanismo de documentación generada y actualizada desde código. [B · BT RT-05.16]
- [ ] **INT-05.** Definir versionado semántico, compatibilidad hacia atrás, política de deprecación con **al menos seis meses** de preaviso y gobierno de cambios de interfaces. [B · BT RT-05.17]
- [ ] **INT-06.** Resolver autenticación entre sistemas con OAuth 2.1 mediante credenciales de cliente o mTLS. Prohibir credenciales estáticas en URL. Distinguir identidad de personas, de servicios y de dispositivos. [B · BT RT-05.18]
- [ ] **INT-07.** Incorporar una capa anticorrupción para sistemas heredados y terceros. Mostrar cómo se traducen sus modelos y cómo un cambio del sistema contable, de la autoridad o de un proveedor no contamina el núcleo. [B · BT RT-05.20]
- [ ] **INT-08.** Diseñar escrituras expuestas a reintento como idempotentes: clave proporcionada por el cliente, ámbito de unicidad, ventana de deduplicación, persistencia de resultado y respuesta frente al duplicado. [B · BT RT-02.06]
- [ ] **INT-09.** Garantizar entrega al menos una vez, deduplicación en consumidores, orden dentro del agregado o partición que lo requiera, colas persistentes, cola de mensajes fallidos y procedimiento de reproceso auditable. Si se usa transactional outbox, explicar su transacción y drenaje. [B · BT RT-02.07 y §2.1]
- [ ] **INT-10.** Declarar en toda llamada remota timeout, reintento exponencial con variación aleatoria, cortacircuito, aislamiento de recursos y rate limit. Mostrar los valores adoptados y el efecto de indisponibilidad, error o lentitud de cada dependencia. [B · BT RT-02.08]
- [ ] **INT-11.** Correlacionar entrada y salida de cada integración con un identificador común de transacción, incluido el tramo móvil–borde–nube y los reintentos. [B · BT RT-05.19]
- [ ] **INT-12.** Diseñar importaciones y exportaciones masivas en formatos abiertos, validación previa, error por registro y procesamiento parcial. Las exportaciones voluminosas deben ser asíncronas, respetar permisos y registrar la exportación de datos sensibles. [B · BT RT-05.22 y RT-16.29/30]
- [ ] **INT-13.** Resolver el contable como **único emisor de DTE**: hechos facturables desde la solución, control de duplicados, confirmación de recepción, estados de procesamiento y conciliación. No atribuir al nuevo sistema la emisión tributaria. [B · CAS restricción 6 y exclusiones]
- [ ] **INT-14.** Identificar los formatos, canales y versiones sectoriales realmente disponibles para autoridad marítima, avisos oficiales, declaración de residuos, esquema ambiental y mensajería de baja capacidad. Si no existe API autorizada, adoptar un mecanismo compatible de preparación/exportación/importación y trazabilidad, con limitaciones explícitas. [B · CAS cap. 15, RT-05.23]
- [ ] **INT-15.** Separar extracción del sistema de 2014 de integración permanente. Definir el mecanismo de acceso seguro, copia de resguardo, extracción, convivencia y consulta histórica; conciliar con el plan de migración del SD5 y el riesgo de ausencia de su única operadora. [D · CAS cap. 15, RT-05.15; REV SD5]
