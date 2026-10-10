# SD4 · Informe 2 · Parte 07: Infraestructura, ambientes y redes

Trabajar esta parte como una tarea acotada. Leer primero [00_Indice_y_modo_de_trabajo.md](00_Indice_y_modo_de_trabajo.md) y aplicar las reglas de [01_Bases_y_estructura.md](01_Bases_y_estructura.md). Las partes son una división del plan de trabajo; **no sustituyen los títulos obligatorios del SD4**.

**Entradas y dependencias:** Partes 01–06; mantener correspondencia con cada componente lógico y con T-11. Ajustar recursos después del cálculo de 08.

**Resultado de esta tarea:** Mapeo lógico–físico, ambientes, despliegue híbrido y diseño de conectividad/segmentación con enlaces y ubicaciones definidos.

**Ubicación del contenido:** 4.2 Arquitectura física; vistas de detalle y referencias al T-11.

**Fuentes:** BA, BT, CAS, EX y REV. Las cinco fuentes originales y sus etiquetas se identifican en la parte 01. No usar esta división para omitir alguna fuente aplicable.

**Criterio de cierre:** aplicar el alcance de B/R/D/C/G definido en la parte 01; registrar ID → sección/figura/tabla/formulario → evidencia → estado real. Una casilla sólo se marca con evidencia existente. Dejar identificados bloqueos, supuestos y cambios que deban propagarse a otras partes. Esta tarea contiene **24 verificaciones originales**.

---

## 4.2 Arquitectura física

Debe permitir auditar el emplazamiento y recorrido de **cada componente lógico** y evaluar capacidad, conectividad, continuidad y despliegue. [EX §11; BA art. 16/T-7; BT caps. 3–10 y 15; CAS §§14–17; REV SD4.2]

### Mapeo, infraestructura y ambientes

La vista general debe descomponerse en vistas de detalle preparadas para explicar cada sitio y conexión.

- [ ] **F-01.** Preparar el mapeo completo esquema SD3 → componente lógico SD4.1 → despliegue SD4.2 → producto/equipo T-11, con nombre único, ubicación, ambiente y etapa. Incluir seguridad, datos, observabilidad, integración e innovaciones, no sólo módulos de negocio. [B · EX capítulo 4; BA T-11]
- [ ] **F-02.** Justificar el emplazamiento de cada componente por latencia, criticidad, conectividad, acoplamiento físico, volumen/transferencia, regulación y costo total de propiedad. Individualizar las excepciones a preferencia por servicios administrados. [B · BA art. 16.2; BT RT-03.05]
- [ ] **F-03.** Presentar la vista física híbrida y el detalle suficiente para identificar nube, red del recinto, pantalanes, varadero/surtidor, boyas y nodo local. Dividir figuras cuando su complejidad lo requiera, conforme a EX. Las fuentes no fijan un número de diagramas ni exigen uno separado por cada ubicación; pueden agruparse vistas si siguen siendo legibles y explicadas. [D · EX §4 y capítulo 4; CAS §17.4]
- [ ] **F-04.** En nube, mostrar proveedor/región, zonas, red virtual, subredes públicas/privadas, rutas, balanceadores, gateway, CDN/WAF/DDoS, cómputo, datos, colas, objetos, identidad, secretos, claves, respaldos y observabilidad. Declarar entrada/salida mediante NAT, endpoints privados u opción escogida y controles de acceso. [D · BT RT-03.04; REV SD4.2]
- [ ] **F-05.** Desplegar en **al menos dos zonas de disponibilidad** todo componente con alta disponibilidad; indicar cantidad, distribución, instancias/tareas y modo de balanceo/conmutación. No confundir multi-AZ con recuperación interregional. [B · BT RT-03.02]
- [ ] **F-06.** Detallar recursos contratados en nube por ambiente y función: CPU/memoria/capacidad, almacenamiento/IOPS, límites de servicio, cuotas, réplicas y políticas de escalado. Incluir herramientas transversales y servicios externos; evitar «servicios AWS» como listado genérico. [D · EX capítulo 4.2; BT RT-09.01]
- [ ] **F-07.** Diseñar los cinco ambientes: **Desarrollo, QA, Preproducción, Producción y Recuperación ante Desastres**; aislamiento de redes/cuentas/datos/credenciales, accesos y propósito. Asegurar habilitación de los cinco en H3, mes 6. BT RT-04.01 agrega DR al listado de cuatro del E-25. [B · BT §4.1 y RT-04.01; EX capítulo 4.2]
- [ ] **F-08.** Hacer Preproducción equivalente a Producción en topología, configuración y versiones, con volumen representativo; declarar y justificar diferencias. Usar datos sintéticos/anonimizados en no productivos, estado controlado y reconstrucción desde código. [B · BT RT-04.02 y RT-11.25]
- [ ] **F-09.** Sostener simultáneamente marcha blanca de Etapa 1 y desarrollo de Etapa 2 en meses 13–15; Etapa 1 en producción desde el mes 16; Etapa 1 en producción y marcha blanca de Etapa 2 en meses 19–20; ambos alcances en producción desde el mes 21. Garantizar fuente única para datos compartidos, evitar doble digitación y no rehacer la plataforma para Etapa 2. [B · BA arts. 15/17]
- [ ] **F-10.** Diseñar ampliación, mantenimiento y reemplazo sin caída de funciones críticas. Declarar puntos únicos de falla que subsistan —también accesos, energía, sensores, redes, equipos únicos y dependencias humanas—, impacto, justificación, contingencia y riesgo residual; reflejarlos en SD8. [B · BT RT-02.11 y RT-10.06; EX capítulo 4.2]

### Red del recinto, pantalanes y conectividad exterior

Las especificaciones deben responder a estructura flotante, cobertura irregular y ausencia de administración técnica local.

- [ ] **RED-01.** Diseñar la segregación efectiva exigida entre red de socios, administrativa, cámaras y operacional. Declarar el tratamiento seguro de instrumentación y administración técnica según el diseño elegido. Los seis segmentos del Informe 1 son una decisión previa a revisar; no constituyen un mínimo de seis redes ni hacen obligatoria una red de gestión fuera de banda. [B · CAS cap. 15, RT-03.24; REV SD4.2]
- [ ] **RED-02.** Definir VLAN/subredes, direccionamiento, enrutamiento, puertos/protocolos permitidos, reglas de firewall, acceso de administración y redes de sensores. No remitir esos datos al T-11 si realmente no los contiene; usar el anexo de red y citarlo correctamente. [D · REV SD4.2; EX capítulo 4.2]
- [ ] **RED-03.** Dibujar todos los puntos de entrada externos: dominios propuestos, puertos, servicios y propósito. Prohibir bases alcanzables desde Internet y exposición directa de servicios internos. Diseñar acceso remoto mediante ZTNA y postura del dispositivo. [B · BT RT-11.13 y RT-03.04/22]
- [ ] **RED-04.** Individualizar proveedor, tecnología y condiciones del enlace principal y respaldo, con caminos físicos y proveedores distintos, entradas separadas cuando corresponda, conmutación automática, tiempo de detección/cambio y prueba de independencia. No atribuir contratación o rutas verificadas sin evidencia. [B · BT RT-03.17; BA art. 16.4]
- [ ] **RED-05.** Nombrar y justificar proveedor de fibra y proveedor del respaldo LEO si se mantiene esa opción; verificar cobertura, terminal, energía, plan/servicio y aptitud para el sitio. Sustituir etiquetas «por contratar» que dejan sin concretar la oferta; distinguir proveedor seleccionado de contrato aún no firmado. [B · REV SD4.1/4.2; BT §1.5]
- [ ] **RED-06.** Dimensionar enlace cifrado privado/VPN entre marina y nube y enlaces por sitio, régimen normal/peak, baja capacidad y recuperación. Definir QoS si se adopta y su prueba sobre el respaldo; no afirmar que el marcado local garantiza priorización en toda una red satelital de terceros. [B · BT RT-03.20/21/24; REV SD4.1]
- [ ] **RED-07.** Especificar cobertura en **los cinco pantalanes y varadero**, ubicación/cantidad inicial de AP y antenas, zonas de sombra, solapamiento, densidad, roaming y autenticación corporativa por certificado/credencial; red de visitas separada. Justificar estimaciones y estudio de sitio comprometido. [B · CAS cap. 15, RT-03.24; BT RT-03.23]
- [ ] **RED-08.** Verificar cobertura con marea en rango completo, movimiento, oleaje, lluvia y dispositivos/perfiles reales. Definir criterio medible de aceptación, zonas/recorridos, número de dispositivos concurrentes y consecuencias de cobertura insuficiente. [D · CAS RT-03.24 y RT-13.08]
- [ ] **RED-09.** Diseñar transición fijo–flotante: trayecto, flexión, radios mínimos, holguras, lazos/cadenas o mecanismo seleccionado, alivio de tracción, conectores, estanqueidad, corrosión, protección galvánica y acceso a reemplazo. Indicar vida útil y reposición de cada elemento expuesto; no asumir que fibra elimina el problema mecánico. [D · CAS restricción 9 y §§16.2/17.4.4]
- [ ] **RED-10.** Mostrar torretas, concentradores/gateways, medidores y sensores por pantalán, alimentación, comunicaciones y gabinete protegido. Definir quién accede, mantiene y reemplaza equipos como servicio. [D · CAS §17.4.5; BT RT-03.18]
- [ ] **RED-11.** Integrar accesos existentes, 38 cámaras y grabador sin presumir cobertura visual de toda la extensión de pantalanes ni usar cámaras para seguir a los alumnos. Dimensionar retención de 6 meses; donde aplica RT-06.24, mantener al menos 30 días disponibles en línea y anteriores recuperables/auditables; separar almacenamiento/tráfico de video de los servicios críticos. [B · CAS RT-05.10 y restricción 3; BT RT-06.24]
- [ ] **RED-12.** Dibujar torre y coexistencia con radio marítima; dispositivos y canales de registro posterior seguro. Diferenciar radio de operación, enlace WAN satelital del recinto y canal de mensajes de armadores: tienen propósitos y capacidades distintos. [D · CAS restricción 4; §17.4.6]
- [ ] **RED-13.** Especificar integración meteorológica y avisos oficiales, verificación de la estación de 2011, adaptación o sustitución técnicamente fundada, estado de dato obsoleto y alarmas; no afirmar que la estación ya dispone de un protocolo no acreditado. [D · CAS RT-17.06; REV SD4.2]
- [ ] **RED-14.** Definir topología de boyas, embarcación de inspección y regreso a base, considerando 6 millas náuticas/22 km, ausencia de energía/datos/personal y acceso por mar favorable; incluir plazo real de instalación/mantención/reposición y falla prolongada por mal tiempo. [D · CAS RT-21.16 y §17.4.12]
