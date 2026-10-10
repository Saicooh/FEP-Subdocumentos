# SD4 · Informe 2 · Parte 11: Decisiones, supuestos y trazabilidad

Trabajar esta parte como una tarea acotada. Leer primero [00_Indice_y_modo_de_trabajo.md](00_Indice_y_modo_de_trabajo.md) y aplicar las reglas de [01_Bases_y_estructura.md](01_Bases_y_estructura.md). Las partes son una división del plan de trabajo; **no sustituyen los títulos obligatorios del SD4**.

**Entradas y dependencias:** Abrir el registro desde 02 y actualizarlo durante las demás tareas. Cerrar esta parte tras consolidar 01–10 y antes de 12–13.

**Resultado de esta tarea:** ADR y supuestos actualizados; las 22 decisiones cubiertas individualmente; cruces de códigos y trazabilidad con formularios/documentos vigentes.

**Ubicación del contenido:** Anexos/registros y formularios referenciados desde el cuerpo; conservar el índice obligatorio del SD4.

**Fuentes:** BA, BT, CAS, EX y REV. Las cinco fuentes originales y sus etiquetas se identifican en la parte 01. No usar esta división para omitir alguna fuente aplicable.

**Criterio de cierre:** aplicar el alcance de B/R/D/C/G definido en la parte 01; registrar ID → sección/figura/tabla/formulario → evidencia → estado real. Una casilla sólo se marca con evidencia existente. Dejar identificados bloqueos, supuestos y cambios que deban propagarse a otras partes. Esta tarea contiene **9 verificaciones originales**.

---

## Registro de decisiones, supuestos y trazabilidad que debe acompañar al SD4

Este contenido puede desarrollarse bajo subtítulos permitidos y en anexos, con síntesis analítica en el cuerpo. No debe crear capítulos del mismo nivel fuera del índice obligatorio. [BA arts. 19, 46–47 y 57; BT RT-02.04/§1.5; CAS §§16.1/17.1; EX; REV]

### Registro ADR

Cada decisión debe indicar una alternativa concreta y asumir sus consecuencias; la fase de validación no sustituye la elección.

- [ ] **ADR-01.** Mantener ADR fechado con alternativa escogida, alternativas descartadas y criterio de decisión: son los mínimos explícitos de RT-02.04. Relacionarlo con el requisito y, para supuestos del caso, con fundamento, impacto e instancia de validación de CAS §17.1. ID, responsable, estado, riesgos e hito pueden usarse para organizar el registro; no imponer una plantilla ampliada de quince campos como exigencia literal de las bases. [D · BT RT-02.04; CAS §17.1]
- [ ] **ADR-02.** Mantener el registro como entregable vivo versionado y gobernado por el Comité de Arquitectura; mostrar dependencias entre ADR y control de cambios. [B · BT RT-02.04; BA art. 71]
- [ ] **ADR-03.** Cerrar o reducir justificadamente los 18 estados LB-V observados, mostrando qué cambió. No basta con cambiarles la etiqueta: sensor, cantidades, regiones, tecnologías, HA, protocolos, firma y rol funcional deben quedar decididos y sustentados. [R · REV SD4.1; CAS §17.1]
- [ ] **ADR-04.** Llevar las 22 decisiones del caso al registro de supuestos compartido con SD3/SD5, con fundamento, impacto e instancia de validación. En SD4 debe constar su consecuencia arquitectónica o la referencia precisa al tratamiento vigente. [B · CAS §17.1; decisiones de §16.1]

La cobertura de las 22 decisiones debe comprobarse individualmente:

| Decisión del caso | Resultado mínimo a verificar en SD4 o referencia desarrollada |
|---|---|
| 1 | Estado de amarra: método elegido y grado de confianza. CAS admite combinación de declaración, observación e instrumentación; REV pide sensor, cantidad y piloto para cerrar DEC-01. No inferir un sensor obligatorio por amarra. |
| 2 | Sistema 2014: extracción, convivencia, migración, consulta histórica, retorno y ausencia de única operadora. |
| 3 | Consumo: medidores, atribución por amarra, muestreo, cobro, marco de traspaso y dato ambiental único. |
| 4 | Plan de navegación: datos, cierre, gracia/vencimiento, escalamiento y límites de responsabilidad. |
| 5 | Cierre de regreso: actor y evidencia sin dispositivo obligatorio a bordo. |
| 6 | Clase: alumno–bote–monitor, salida/cierre sin cámaras ni dispositivos prohibidos. |
| 7 | Retiro anticipado: propagación y regla segura de conflicto portería–escuela. |
| 8 | Salud: dato mínimo visible al monitor, autorización y registro de consulta. |
| 9 | Compatibilidad de puesto: criterios, excepciones y auditoría. |
| 10 | Lista de espera: regla de oferta y decisión societaria/comercial trazable. |
| 11 | Visitante que se va sin oficina: estadía, cobro/hecho facturable y recalada nocturna. |
| 12 | Izaje: registro seguro, validación y ficha disponible antes de maniobra. |
| 13 | Reprogramación de travelift por clima: restricciones y notificaciones. |
| 14 | Residuos por embarcación sin aplicación obligatoria para contratista. |
| 15 | Acreditación en portería: habilitación y trazabilidad efectiva. |
| 16 | Capacitación ambiental: evidencia, vigencia, responsable y renovación. |
| 17 | Mora: autorización formal fundada y ninguna barrera automática arbitraria. |
| 18 | Abandonadas: expediente completo y conservación probatoria. |
| 19 | Ocupación/identidad de boyas: método, energía/datos, actualidad y límites. |
| 20 | Tren de fondeo: identificación, inspección, periodicidad y disparador. |
| 21 | Mostrador offline con 90 zarpes: legajo ≤90 s y reconciliación. |
| 22 | Administrador funcional: titular propuesto, reemplazo, tareas y horas-persona/mes; gestión técnica como servicio. |

### Correspondencias de códigos que no deben perder obligaciones

El capítulo 15 del caso usa varios códigos cuya materia difiere de la fila del mismo código en BT. No renumerar silenciosamente las fuentes. Registrar documento + numeral + texto de obligación y relacionar ambos. Cubrir las dos obligaciones cuando son distintas y acumulables; consultar discrepancias reales. Ejemplos relevantes:

| Código usado en el caso | Materia del caso | Correspondencia adicional en BT |
|---|---|---|
| RT-03.13 | Sincronización ≤30 min tras 24 h | RT-03.12 sincronización y RT-03.13 funciones no disponibles. |
| RT-03.24 | Cobertura y segregación de redes | RT-03.23 cobertura y RT-03.24 QoS deseable. |
| RT-05.10 | Retenciones particulares | RT-05.07 retención; RT-05.10 catálogo/linaje deseable. |
| RT-06.01 | Gabinete mínimo | BT §6.1 proporcionalidad y RT-06.01 exclusividad del espacio según tipología. |
| RT-09.01 | Tiempos de procesos críticos | BT cap. 9 y RT-09.01 cálculo de capacidad. |
| RT-15.02 | Competencia/certificación sectorial | BT §15.2 certificación sectorial y RT-15.02 apagado de no productivos. |
| RT-16.14 | Firma electrónica | BT RT-16.17/18 firma/evidencia y RT-16.14 motor de reglas deseable. |
| RT-16.21 | Canales de notificación | BT RT-16.20–25 canales, plantillas y mensajería. |
| RT-16.30 | Portal público | BT RT-16.31–34 portal y RT-16.30 auditoría de exportación sensible. |
| RT-17.06 | Equipamiento/integraciones industriales | BT RT-17.06 periféricos móviles, cap. 8 y arquitectura de integración. |
| RT-21.06 | Horario de atención | BT RT-21.07 horario y RT-21.06 indicadores de atención. |

- [ ] **MAP-01.** Completar el cruce anterior para cualquier otra discrepancia hallada, sin fusionar obligaciones por compartir ID. [D · CAS cap. 15 y filas homónimas de BT]
- [ ] **MAP-02.** Alimentar T-12 con componente individualizado y versión, sección real de SD4 y evidencia/prueba/certificado. Distinguir cumplimiento de diseño de evidencia futura, parcial o no acreditada. No declarar «Sí» para una integración externa o decisión todavía indeterminada. [B · BT §1.5; BA T-12]
- [ ] **MAP-03.** Comprobar cobertura de los **374 RT en la matriz global**, asignando a SD4 sólo lo arquitectónico y señalando el desarrollo en los otros subdocumentos para el resto. No forzar la web corporativa, video, prototipo de Informe 3 o currículos completos dentro del SD4; tampoco usar su ubicación en otro documento para omitir controles que necesita el diseño. [B · BT §1.5 y anexo A; BA T-22]
- [ ] **MAP-04.** Mantener trazabilidad origen del caso → RF/RNF/regla → componente → despliegue/T-11 → paquete EDT/mes → riesgo → prueba → criterio de aceptación/operación. Toda referencia debe existir en la versión entregada; no citar secciones inexistentes ni páginas de una consolidación anterior. [B · CAS §17.1; EX §3]
- [ ] **MAP-05.** Para cada requisito obligatorio de arquitectura/continuidad/seguridad, aportar solución concreta y evidencia. «Cumplimos ISO», «alta disponibilidad» o «modo offline» sin implementación y verificación no cierra la obligación. [B · BT §1.5; BA arts. 4.3/58]
