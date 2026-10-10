# SD4 · Informe 2 · Parte 12: Cierre de observaciones del Informe 1

Trabajar esta parte como una tarea acotada. Leer primero [00_Indice_y_modo_de_trabajo.md](00_Indice_y_modo_de_trabajo.md) y aplicar las reglas de [01_Bases_y_estructura.md](01_Bases_y_estructura.md). Las partes son una división del plan de trabajo; **no sustituyen los títulos obligatorios del SD4**.

**Entradas y dependencias:** Entregables consolidados de 01–11 y revisión original completa. Si aparece una brecha, volver a su parte responsable.

**Resultado de esta tarea:** Tabla observación–respuesta–sección–evidencia, con cierre real de todas las observaciones aplicables y dependencias pendientes identificadas.

**Ubicación del contenido:** Tabla de respuesta y cambios incorporados en sus secciones reales de SD4/otros documentos.

**Fuentes:** REV completa, contrastada con BA, BT, CAS y EX. Las cinco fuentes originales y sus etiquetas se identifican en la parte 01. No usar esta división para omitir alguna fuente aplicable.

**Criterio de cierre:** aplicar el alcance de B/R/D/C/G definido en la parte 01; registrar ID → sección/figura/tabla/formulario → evidencia → estado real. Una casilla sólo se marca con evidencia existente. Dejar identificados bloqueos, supuestos y cambios que deban propagarse a otras partes. Esta tarea contiene **17 verificaciones originales**.

---

## Cierre específico de observaciones del Informe 1

El Informe 2 debe incorporar una tabla observación–respuesta–sección modificada. Para SD4, añadir criterio/evidencia de cierre y referencia vigente. Las filas siguientes indican grupos de observaciones que deben desagregarse si abarcan varias correcciones. [BA art. 46/T-22; REV General, SD4.1, SD4.2 y Consideraciones transversales]

- [ ] **REV-01.** Mostrar solución completa entendible y mapeada con el esquema/explicación del SD3; el esquema no puede existir sólo en el SD4. [R · REV SD4.1, esquema; EX capítulo 4]
- [ ] **REV-02.** Sustituir diagramas contradictorios con texto: PWA/Kotlin, OAuth 2.0/2.1, TOTP/SMS/Passkeys, REST/gRPC/túnel, AES-128/256, LoRaWAN decidido/por definir y umbral de sincronización. [R · REV SD4.1, contradicciones]
- [ ] **REV-03.** Resolver DEC-01: sensor, cantidad, ubicación, piloto y contingencia; no dejar «multifuente» como decisión suficiente. Resolver DEC-22 con una unidad de esfuerzo, responsable funcional propuesto y reemplazo. [R · REV SD4.1, Qué se espera]
- [ ] **REV-04.** Incorporar escenarios faltantes: 90 zarpes sin enlace/legajo ≤90 s, falla completa del nodo local y mensaje satelital que nunca llega. [R · REV SD4.1, escenarios faltantes]
- [ ] **REV-05.** Rehacer ADR con fechas, fundamentos, consecuencias y estados verificados; cerrar pendientes de base y vincular las 22 decisiones al registro de supuestos. [R · REV SD4.1, decisiones]
- [ ] **REV-06.** Corregir regiones incompatibles entre T-12 y SD4; retirar secundaria en México y «ambas en São Paulo» como solución de recuperación regional; estudiar amenazas sobre la pareja real y residencia de datos de menores. [R · REV SD4.2, regiones]
- [ ] **REV-07.** Rehacer diagrama físico auditable con VPC/red, subredes, zonas, balanceo, seguridad, nodo A/B, direccionamiento/segmentos, medidores/AP, accesos/cámaras, surtidor, boyas, estación y enlaces/proveedores. [R · REV SD4.2, Qué se espera]
- [ ] **REV-08.** Completar T-11 con ubicación, cantidad y justificación en formato de campos original, hardware real y características; cerrar los 41 componentes anteriores si se conservan y añadir los faltantes. No tratar «41» como total obligatorio si cambia la solución. [R · REV SD4.2, T-11]
- [ ] **REV-09.** Reducir el on-premise al gabinete apropiado; justificar cualquier grupo electrógeno, ATS, rack adicional, climatización N+1 o extinción. Cerrar carga eléctrica y autonomía con cálculos. [R · REV SD4.2, tipología on-premise]
- [ ] **REV-10.** Completar reversibilidad, portabilidad, RAID, hardening CIS/parches, herramienta IaC, HA local y proveedores seleccionados de fibra/LEO/firma. Resolver evidencia del socio de nube sin afirmar contratos/certificaciones inexistentes. [R · REV SD4.1/4.2, ausencias]
- [ ] **REV-11.** Completar plan de reposición costeable a 56 meses con vida útil y cantidades, incluyendo cableado en flexión; mantener montos exclusivamente en oferta económica. [R · REV SD4.2, reposición]
- [ ] **REV-12.** Revisar compatibilidad/soporte tecnológico y afirmaciones del Informe 1: paquetes disponibles en SO, mecanismo HA, requisitos kernel/VPN, soporte Android, alcance de QoS LEO, capacidad del canal satelital y disponibilidad de productos por región. Usar verificación oficial, no copiar las críticas como conclusiones técnicas actuales. [R · REV SD4.1, factibilidad cruzada]
- [ ] **REV-13.** Corregir dimensionamientos sin derivación o incoherentes: mensajes mensuales, lecturas crudas/agregación, crecimiento, margen, proyección de menores frente a apoderados y throughput efectivo de sincronización. [R · REV SD4.1, dimensionamiento]
- [ ] **REV-14.** Reubicar/repetir coordinadamente lo necesario en SD5: motor, paradigma/CAP por dominio, desempeño, volumen/calendario de migración, exportación/eliminación, retención y estándares de integración. No dejar contenidos que T-7/EX asignan al SD5 desarrollados sólo en SD4. [R · REV SD5; EX capítulo 5]
- [ ] **REV-15.** Corregir relaciones con SD13: IA sí/no y controles; innovaciones no confundidas con obligaciones; componentes, interfaces, EDT/mes y riesgos definidos. Mantener cobertura arquitectónica de las innovaciones sustituidas. [R · REV SD13; EX §8]
- [ ] **REV-16.** Cerrar observaciones generales de contenido: voz comercial, análisis además de listados, figuras reales explicadas, referencias cruzadas válidas, citas pertinentes y ausencia de marcadores/notas de asistente, duplicados o cifras supuestamente retiradas que siguen vigentes. [R · REV General; EX §§3/4/6/7]
- [ ] **REV-17.** No cerrar observaciones sólo con «corregido». Cada respuesta debe explicar el cambio concreto, dónde se desarrolla, evidencia del cierre y cualquier dependencia que aún impida acreditarlo. [R · BA art. 46; REV General]
