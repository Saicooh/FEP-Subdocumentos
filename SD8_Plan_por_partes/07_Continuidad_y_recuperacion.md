# Parte 07 · Continuidad del negocio y recuperación ante desastres

**Destino:** subtítulos bajo 8.2 y 8.3, con referencia al T-16 y al diseño de SD4/SD5. **Fuentes:** BA, T-7, Art. 20 y Art. 78; BTT, cap. 7, RT-10.01–10.08 y cap. 20; CASO, cap. 6, restricciones 1–10, parámetros de cap. 15 y 17.4–17.6; REV, SD4 y SD5.

## 1. BCP y análisis de impacto

El Plan de Continuidad del Negocio debe explicar cómo Panitao conserva sus procesos y registros ante indisponibilidad. El DRP describe la recuperación técnica que lo sostiene.

- [ ] [E] Incluir **BCP conforme a ISO 22301** y **continuidad TIC/DRP conforme a ISO/IEC 27031**. Explicar su aplicación, no sólo citar normas. Fuentes: BA, T-7, gestión de riesgos y Art. 20; BTT, RT-10.03–10.04.
- [ ] [E] Desarrollar análisis de impacto en el negocio, escenarios, procedimientos manuales de respaldo y criterios de activación. Fuente: BTT, RT-10.03.
- [ ] [E] Clasificar cada servicio como **crítico, alto, medio o bajo**, con fundamento en la consecuencia de su indisponibilidad. Fuente: BTT, RT-10.02.
- [ ] [A] Relacionar clasificación con personas en el agua, custodia, aviso de marejada, combustible, atención de visitantes, facturación y obligaciones ambientales. No clasificar toda función igual sin explicar impactos.
- [ ] [E] Alinear cada clasificación con Art. 78: disponibilidad mensual mínima **99,9 / 99,5 / 99,0 / 98,0 %**, respuesta máxima **15 min / 1 h / 4 h / 8 h** y resolución máxima **4 / 8 / 24 / 48 h**, respectivamente.
- [ ] [E] Medir la disponibilidad crítica sobre la **transacción de negocio de extremo a extremo**. No usar disponibilidad de la nube o del servidor como sustituto. Fuentes: BA, Art. 20; BTT, 1.7 y RT-10.01.
- [ ] [E] Comprometer para servicios críticos **RTO ≤ 4 horas** y **RPO ≤ 15 minutos**, salvo exigencia superior aplicable. Fuentes: BA, Art. 20; BTT, RT-07.04.
- [ ] [V] No interpretar RPO de 15 minutos como permiso para perder registros cuya operación desconectada exige conservar íntegramente: son situaciones distintas. Fuente: CASO, parámetros de operación y sincronización en cap. 15.

## 2. Desconexión y falla local: escenarios diferenciados

El recinto debe continuar sin enlace exterior; además hay que modelar la falla del propio borde. La segunda no se resuelve prometiendo la autonomía de la primera.

- [ ] [E] Describir continuidad del recinto durante **24 horas sin enlace exterior** para recepción, asignación de amarra, salida/regreso, preparación de zarpes, expendio de combustible y escuela. Fuente: CASO, cap. 15, operación desconectada.
- [ ] [E] Cubrir **12 horas fuera de cobertura** para dispositivos de pantalán, varadero y escuela, y **8 horas** para inspección de boyas, sin pérdida de registro. Fuente: CASO, cap. 15, operación desconectada.
- [ ] [E] Explicar registro local con integridad y sincronización automática sin intervención manual, en **no más de 30 minutos tras 24 horas de desconexión**, sin pérdida de los registros críticos señalados por el caso. Fuente: CASO, cap. 15, sincronización.
- [ ] [E] Declarar funciones no disponibles sin conexión y procedimiento manual que las suple. No prometer acceso inmediato a un servicio externo caído. Fuente: BTT, RT-03.13.
- [ ] [A] Modelar paso a paso mostrador con hasta **90 zarpes** sin enlace: antecedentes locales disponibles, preparación del legajo en **90 segundos**, límites de comunicación con autoridad, registro y reconciliación. La plataforma no otorga zarpe. Fuentes: CASO, RT-09.01 y decisión 21; REV, SD4.1.
- [ ] [A] Modelar falla del nodo de borde: detección, cambio a redundante, tareas preservadas, condición para respaldo manual si también falla la alternativa y recuperación. Fuente: REV, SD4.1; BTT, RT-03.14.
- [ ] [A] Diferenciar energía suficiente del sistema, autonomía de batería de dispositivo y autonomía sin Internet. No afirmar que 24 h sin enlace exige automáticamente un generador con 24 h de combustible. Fuentes: CASO, RT-06.01; REV, SD4.2.
- [ ] [A] Describir protección y recuperación de transacciones sin resolver por «última escritura gana» cuando eso pueda borrar retiro de menor, deuda o despacho. La regla concreta debe coincidir con SD4/SD5.
- [ ] [A] Para mensajes de navegación ausentes o tardíos, preservar alerta y acción humana coherentes con el compromiso de la marina y la radio, sin inferir automáticamente una emergencia o un regreso. Fuentes: CASO, decisiones 4–5 y 17.4; REV, SD4.1.

## 3. Procedimientos de contingencia de negocio

El procedimiento manual debe ser trazable y utilizase sólo en el alcance que corresponde. No puede reinstalar indefinidamente cuadernos como sistema oficial.

- [ ] [A] Para cada escenario prioritario, indicar activación, responsable y sustituto, secuencia segura, comunicación, registro alternativo, duración tolerada y condición de retorno.
- [ ] [A] Mantener coordinación por radio sin exigir interacción con dispositivos durante amarre o izaje. Fuente: CASO, restricciones 1 y 4.
- [ ] [A] Preservar certeza de salida, regreso y retiro anticipado de alumnos; proteger autorizaciones, salud y contactos de emergencia durante contingencia. Fuentes: CASO, decisiones 6–8 y restricción 14.
- [ ] [A] Definir alternativa frente a notificación masiva fallida y tratamiento de destinatarios sin acuse, manteniendo registro de llamada e instrucción. Fuente: CASO, RT-16.21.
- [ ] [A] Para cierre administrativo, enlazar con extracción/respaldo y conocimiento distribuido del sistema de 2014. La única operadora no puede ser el único recurso de la contingencia. Fuentes: CASO, cap. 5; REV, SD3 y SD5.
- [ ] [A] Describir captura, custodia e incorporación posterior de registros alternativos; comprobar que no se duplican cargos ni se pierden hechos de seguridad.
- [ ] [A] Declarar qué resuelve Synaptix como servicio y qué valida la marina funcionalmente. No asignar restauración técnica habitual a personal TI del CLIENTE, porque no existe. Fuentes: CASO, restricción 7 y 17.6.

## 4. DRP, replicación, conmutación y retorno

La recuperación debe usar el sitio secundario realmente ofertado y ser compatible con residencia y autorizaciones de tratamiento de datos.

- [ ] [E] Declarar modalidad **activo-activo o activo-pasivo** y justificarla frente a RTO y complejidad operacional. Fuente: BTT, RT-07.01.
- [ ] [E] Identificar sitios principal/secundario, distancia y **amenazas comunes**, demostrando separación suficiente para el evento analizado. Fuente: BTT, RT-07.02.
- [ ] [A] Reconciliar el par de regiones con la corrección solicitada en REV, SD4.2, y con la arquitectura actual. No conservar México como secundaria «temporal» por inercia ni tratar una región futura como habilitada.
- [ ] [E] Definir **replicación continua**, medición y alertamiento de su retraso. Declarar el umbral de alerta elegido y su relación con el RPO. Fuente: BTT, RT-07.03.
- [ ] [E] Documentar conmutación y automatizarla en la mayor medida posible. Articular ejecutor gestionado, autorización y validación funcional de acuerdo con la ausencia de TI local. Fuente: BTT, RT-07.05; CASO, 2.4 y criterio 25.
- [ ] [E] Documentar y probar **retorno al sitio principal**, con reconciliación de datos producidos durante contingencia. Fuente: BTT, RT-07.06.
- [ ] [A] Definir quién detecta, decide y ejecuta; qué ocurre con transacciones en curso y con dispositivos desconectados; cómo se valida el servicio completo y cuándo se comunica el retorno.
- [ ] [V] No llamar «automática» a toda conmutación como requisito literal: BTT, RT-07.08, lo considera deseable. La documentación y la automatización en la mayor medida posible sí son obligatorias.

## 5. Respaldo y restauración

La réplica no sustituye un respaldo recuperable: puede propagar corrupción o borrado. La restauración debe mantener evidencias y retenciones del caso.

- [ ] [E] Definir esquema **3-2-1-1-0**: tres copias, dos medios, una fuera de sitio, una inmutable o fuera de línea y cero errores de verificación. Fuentes: BA, Art. 20; BTT, RT-07.09.
- [ ] [E] Cifrar respaldos en reposo y tránsito y gestionar su clave de forma independiente de la infraestructura respaldada. Fuente: BTT, RT-07.10.
- [ ] [E] Proteger copias inmutables contra borrado y modificación incluso con credenciales administrativas comprometidas. Fuente: BTT, RT-07.11.
- [ ] [E] Declarar por dominio frecuencia, retención y tiempo estimado de restauración completa, compatibles con los plazos y tipos de evidencia del caso. Fuente: BTT, RT-07.13; CASO, cap. 15, retención.
- [ ] [A] Incluir los datos del borde y las operaciones no sincronizadas en la estrategia que les corresponda; no dar por protegida una transacción local sólo porque exista respaldo cloud.
- [ ] [A] Analizar restauración fallida, respaldo incompleto, clave inaccesible y restauración que reintroduzca datos eliminados o ignore retención probatoria. Vincular tratamiento con SD5.
- [ ] [E] Programar y documentar **prueba de restauración al menos mensual**, sobre muestra representativa, con tiempo efectivo medido. Fuente: BTT, RT-07.12.

## 6. Pruebas y validación de continuidad

En el Informe 2 se define el plan y la evidencia prevista. No se afirma que una prueba se ejecutó sin resultados disponibles.

- [ ] [E] Incluir recuperación ante desastres **antes del paso a producción** y pruebas en operación **al menos dos veces al año**, mediante conmutación real. Medir RTO/RPO, informar resultado y corregir brechas. Fuentes: BTT, cap. 20 y RT-07.07; BA, Art. 20.
- [ ] [E] Incluir resiliencia con inyección controlada de fallas **antes de cada paso a producción** y **al menos semestralmente durante operación**. Cubrir instancia, zona, dependencia externa, latencia y saturación de disco. Fuente: BTT, RT-10.07.
- [ ] [A] Añadir escenarios específicos de la arquitectura: 24 h sin enlace, reconexión, falla del borde, ventana de marejada y captura de registros críticos. Las pruebas deben referirse a los riesgos del T-16.
- [ ] [E] Articular pruebas de seguridad ofensiva **anuales y previas a cada paso a producción** por tercero independiente, con plan de remediación. Fuente: BA, Art. 21.3; BTT, RT-11.20.
- [ ] [A] Enlazar pruebas, responsables, calendario y criterios de salida con SD7 y SD9/T-13/T-17/T-18, sin duplicar instrucciones incompatibles.
- [ ] [E] Planificar mantenimientos fuera de ventanas críticas, con aviso mínimo de **10 días hábiles**, y cambios sin interrupción conforme al diseño. Fuentes: BA, Art. 20; BTT, RT-10.05–10.06; CASO, cap. 15.
- [ ] [V] No convertir simulacro anual de incidente, conmutación completamente automática o restauración granular en obligatorios adicionales: son deseables de BTT, RT-11.21, RT-07.08 y RT-07.14, salvo compromiso adoptado expresamente.

## 7. Cierre de esta parte

El BCP/DRP debe permitir seguir escenario → impacto → activación → operación degradada → recuperación → conciliación → retorno → prueba. Sus tiempos, sitios y responsables deben coincidir con la arquitectura y la planificación, sin suponer personal TI en la marina.
