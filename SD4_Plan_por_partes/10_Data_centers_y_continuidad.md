# SD4 · Informe 2 · Parte 10: Data centers, alta disponibilidad y recuperación

Trabajar esta parte como una tarea acotada. Leer primero [00_Indice_y_modo_de_trabajo.md](00_Indice_y_modo_de_trabajo.md) y aplicar las reglas de [01_Bases_y_estructura.md](01_Bases_y_estructura.md). Las partes son una división del plan de trabajo; **no sustituyen los títulos obligatorios del SD4**.

**Entradas y dependencias:** Partes 01–09. La pareja de regiones elegida debe conciliarse con software, privacidad, red, capacidad y T-12.

**Resultado de esta tarea:** Diseño de primaria/secundaria, alta disponibilidad, energía, protección, respaldos y recuperación con RTO/RPO y pruebas concretos.

**Ubicación del contenido:** 4.3, 4.3.1 y 4.3.2; vínculos explícitos con nodo local, red y seguridad.

**Fuentes:** BA, BT, CAS, EX y REV. Las cinco fuentes originales y sus etiquetas se identifican en la parte 01. No usar esta división para omitir alguna fuente aplicable.

**Criterio de cierre:** aplicar el alcance de B/R/D/C/G definido en la parte 01; registrar ID → sección/figura/tabla/formulario → evidencia → estado real. Una casilla sólo se marca con evidencia existente. Dejar identificados bloqueos, supuestos y cambios que deban propagarse a otras partes. Esta tarea contiene **28 verificaciones originales**.

---

## 4.3 Data center

Debe abrir con una explicación de la estrategia completa de centros de datos y borde. No puede quedar reducido a dos párrafos con nombres de regiones. [EX §11; BA art. 16/T-7; BT caps. 6–7; CAS RT-06.01; REV SD4.2]

- [ ] **DC-01.** Explicar la relación entre región primaria de nube, región/sitio secundario y gabinetes locales. Distinguir alta disponibilidad dentro de región, recuperación ante desastre regional y autonomía del recinto. [B · BA art. 16; EX capítulo 4.3]
- [ ] **DC-02.** Declarar una pareja primaria/secundaria definitiva y ejecutable, con separación y amenazas comunes justificadas. BA art. 16.3 y BT RT-03.01 exigen presencia del proveedor en Chile o Sudamérica, pero no dicen literalmente que ambas regiones deban estar allí. REV SD4.2 pide secundaria en Chile o Sudamérica o cambio de proveedor: responder esa corrección explícita y registrar cualquier discrepancia conforme a BA art. 5. No atribuir a BA una restricción geográfica que proviene de REV, ni presentar dos zonas de una región como DR regional. [R · BA art. 16.3; REV SD4.2; BT RT-07.02]
- [ ] **DC-03.** Fundamentar la ubicación con requisitos de datos, latencia, disponibilidad de servicios, distancia, amenazas comunes, soporte y sostenibilidad. No afirmar que una región futura está disponible; basar la oferta en disponibilidad verificable a la fecha de elaboración. [B · BA art. 16.2; BT RT-07.02 y §1.6]
- [ ] **DC-04.** Acreditar capacidad del proveedor global con presencia en Chile/Sudamérica y relación de Synaptix como socio o participación formal de socio certificado, en acuerdo con BA art. 34 y antecedentes corporativos. No sustituir evidencia por «pendiente de acreditación» ni inventar una carta. [B · BA art. 34; BT RT-03.01]
- [ ] **DC-05.** Especificar los niveles y certificaciones de los centros primario y secundario según lo solicitado en T-7, que menciona Tier III / ANSI/TIA-942, y aportar la evidencia pertinente al servicio y sitio elegidos. No convertir esa mención entre paréntesis en un umbral numérico adicional que el texto no declara como mínimo. No atribuir una certificación genérica del proveedor a todos sus edificios ni confundir ISO 27001 con una certificación de centro de datos; identificar cualquier aclaración necesaria. [B · BA T-7, ítem 4.2]

## 4.3.1 Especificaciones Data Center Primaria

Se desarrolla la infraestructura primaria contratada y la tipología local estrictamente necesaria para el caso.

- [ ] **P-01.** Individualizar proveedor, código/nombre exacto de región, zonas utilizadas, servicios y capacidad; demostrar disponibilidad efectiva de cada producto en esa ubicación y mantener la misma pareja en T-12, T-11 y figuras. [B · BT RT-03.01; EX capítulo 4.3.1]
- [ ] **P-02.** Especificar aislamiento de red, HA por capa, almacenamiento, claves, cuentas del cliente, accesos, monitoreo y protección; mostrar qué información se procesa/almacena en esa región y qué sale hacia terceros. [D · BT RT-03.02/04; BA art. 85]
- [ ] **P-03.** Clasificar cada emplazamiento on-premise conforme a BT §6.1: gabinete/borde operacional en administración y los puntos requeridos del pantalán/varadero. Justificar el mínimo para 24 h y gestión remota sin intervención normal. No convertirlo sin cálculo en una sala técnica con dos racks, N+1 y generador. [B · BT §6.1; CAS RT-06.01]
- [ ] **P-04.** Preparar esquema/plano del gabinete y conexiones reales: ubicación, dimensiones/ocupación, zonas de cómputo/comunicaciones/baterías, reserva, acceso físico, ventilación, alimentación, tierra y protección de agua/corrosión. Aplicar por tipología los requisitos de BT cap. 6; registrar uno a uno las exclusiones o adaptaciones con fundamento. [D · BT §6.1 y RT-06.03; REV SD4.2]
- [ ] **P-05.** Para gabinetes, desarrollar explícitamente protección eléctrica, control de acceso físico, monitoreo remoto y condiciones ambientales de fabricante. Si se adopta una sala técnica en algún sitio, aplicar los requisitos de esa tipología, incluidos segregación, distribución, energía, climatización, incendio, acceso, medios y operación; no omitirlos por llamarla «gabinete». [D · BT §6.1; CAS RT-06.01]
- [ ] **P-06.** Dimensionar UPS a plena carga con autonomía mínima de 30 min donde corresponde; alimentación independiente/protegida, puesta a tierra, protecciones diferenciales/galvánicas para pantalanes y normativa citada con aplicación concreta. Declarar revisión/medición eléctrica semestral donde aplica. Diferenciar caída del enlace exterior de corte de suministro eléctrico. [D · BT RT-06.07/09/10; CAS §16.2]
- [ ] **P-07.** Resolver energía autónoma requerida según tipología y análisis de continuidad. Si aplica generación 24 h de RT-06.08, dimensionar carga, combustible, reabastecimiento y mantenimiento gestionado; si se justifica otra solución proporcional para gabinete, documentar cobertura y pertinencia normativa. No dejar generación ni autonomía eléctrica sin análisis frente a la observación del Informe 1. [D · BT §6.1 y RT-06.08; REV SD4.2]
- [ ] **P-08.** Resolver temperatura, humedad, agua y disipación con límites de fabricante, alarmas al NOC y mantenimiento. Justificar si se requiere climatización; no exigir climatización de precisión N+1 o pasillos frío/caliente a un gabinete por mera copia de requisitos de sala. [D · BT §6.1 y RT-06.13/14]
- [ ] **P-09.** Resolver seguridad/incendio según tipología y riesgo: cierre, ingreso autorizado, bitácora, acompañamiento de terceros, detección/avisos y medidas de extinción. Justificar no aplicabilidad de recinto biométrico, pasillo, enrolamiento, detección por aspiración u otras medidas de sala cuando proceda, sin vaciar el control físico del gabinete. [D · BT §6.1 y §§6.5/6.6]
- [ ] **P-10.** Especificar respaldo/custodia, inventario de medios, verificación/rotación, alternativa más segura a medio transportable si se elige; espacio de operación separado de equipos y uso de instalaciones existentes cuando corresponda. No crear dependencias de manejo manual semanal de discos por la marina. [D · BT §§6.7/6.8; CAS restricción 7]
- [ ] **P-11.** Resolver rutas de comunicación separadas, canalizaciones y certificación de enlaces. Declarar disponibilidad de infraestructura 99,95 % conforme a BT §§6.1/7.2 y cómo contribuye al SLA crítico de extremo a extremo 99,9 %, sin equiparar ambos indicadores. [B · BT RT-06.32/33 y §§6.1/7.2]

## 4.3.2 Especificaciones Data Center Secundario

La recuperación debe ser realizable con productos, capacidad, responsables y procedimientos definidos, diferenciándose de alta disponibilidad y respaldo.

- [ ] **S-01.** Individualizar región/sitio secundario real, servicios críticos cubiertos, capacidad, datos replicados y modalidad activo-activo/activo-pasivo; justificar RTO, complejidad y recursos. Explicar capacidad mínima en espera y capacidad al conmutar. [B · BT §7.1 y RT-07.01]
- [ ] **S-02.** Declarar distancia entre sitios y análisis de amenazas compartidas: sismo, tsunami/inundación, energía, operadores, rutas, control del proveedor y dependencia de servicios globales. Aplicarlo al par realmente ofertado, no a una futura pareja distinta. [B · BT RT-07.02]
- [ ] **S-03.** Diseñar replicación continua por almacén, cifrado, orden, consistencia, retraso medido, **umbral de alerta** y escalamiento. Identificar qué datos siguen siendo locales durante desconexión y cómo se recuperan sin confundirlos con el RPO interregional. [D · BT RT-07.03; CAS RT-03.10]
- [ ] **S-04.** Comprometer para servicios críticos **RTO ≤4 h y RPO ≤15 min**, con inicio/fin de medición, dependencias, pérdida máxima admisible y pasos para alcanzarlos. Si se ofrece RTO local de 2 h u otra meta más estricta, sustentarla y conciliarla con recuperación regional. [B · BT RT-07.04]
- [ ] **S-05.** Preparar procedimiento de failover: detección/disparador, quién autoriza/ejecuta, prevención de doble activo, promoción de datos, conectividad, DNS/certificados, identidad/claves, reanudación de colas y validación del negocio. Automatizar cuanto sea posible; ofrecer ejecución guiada sin especialistas propios del cliente. [D · BT RT-07.05; CAS restricción 7]
- [ ] **S-06.** Preparar failback con conciliación de datos de contingencia, protección contra duplicados/pérdida, retorno de tráfico, criterio de éxito y reversión si falla. Si se ofrece conmutación automática, documentar protección contra disparos innecesarios. [D · BT RT-07.06/08]
- [ ] **S-07.** Comprometer pruebas de DR con conmutación real antes de producción y **al menos dos veces al año**, informes RTO/RPO obtenidos y plan de cierre de brechas; vincular tareas a SD7 y criterios a SD9, sin presentar resultados ficticios. [B · BT RT-07.07 y §20.1]
- [ ] **S-08.** Separar DR de respaldo: implementar esquema **3-2-1-1-0**, indicar tres copias, dos medios, copia fuera de sitio, inmutable/offline y verificaciones sin error. Réplica de producción no es por sí sola respaldo inmutable. [B · BT RT-07.09]
- [ ] **S-09.** Especificar cifrado y claves independientes de respaldo, protección contra borrado/modificación aun con credenciales administrativas comprometidas, mecanismo de retención y recuperación de claves. [B · BT RT-07.10/11]
- [ ] **S-10.** Definir por dominio frecuencia, retención, destino, volumen y tiempo de restauración completa; incluir borde, configuraciones, claves recuperables y evidencia operacional. Conciliar retenciones de CAS, SD5 y logs/auditoría. [D · BT RT-07.13; CAS RT-05.10]
- [ ] **S-11.** Comprometer restauración mensual documentada de muestra representativa y tiempo medido. Si se ofrece restauración granular de registro/tabla/módulo/sistema, explicar su mecanismo y evidencia. [B · BT RT-07.12/14]
- [ ] **S-12.** Relacionar plan de DR con continuidad ISO 22301/ISO 27031, análisis de impacto, clasificación crítico/alto/medio/bajo, procedimientos manuales y escenarios marinos. Mantener metas por clase: 99,9/99,5/99,0/98,0 %, respuesta 15 min/1 h/4 h/8 h y resolución 4 h/8 h/24 h/48 h, con cobertura contractual correspondiente. [B · BT RT-10.01/02/03/04; BA art. 78]
