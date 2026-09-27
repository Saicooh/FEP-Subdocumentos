# ARQUITECTURA DE SOFTWARE

## FORMULACIÓN Y EVALUACIÓN DE PROYECTOS

*Pontificia Universidad Católica de Valparaíso · Escuela de Informática*

**Taller:** Taller Formulación de Proyectos Informáticos  
**Código:** ICI-5444  
**Autor:** Antonio Moya Villegas — antonio.moya@pucv.cl  
**Versión:** v3.1.0 — 2026

## Introducción

### El recorrido

Vamos a construir un mismo razonamiento en diez pasos. Al final de este recorrido usted debería poder dibujar la arquitectura de su solución y defender por qué es esa y no otra.

| Paso | Tema | Contenido |
|---|---|---|
| 1 | Fundamentos | Qué es y qué no es arquitectura. Atributos de calidad y vistas. |
| 2 | Arquitectura lógica | Monolito, capas, microservicios, eventos y la capa de integración con terceros. |
| 3 | Arquitectura física | Modelo OSI, redes, data center, contenedores, datos y almacenamiento. |
| 4 | La nube | IaaS/PaaS/SaaS, regiones, serverless, orquestación, on-premise vs nube. |
| 5 | Atributos de calidad | Escalabilidad, disponibilidad, rendimiento y el nivel de servicio que se firma. |

### El recorrido · continuación 1

| Paso | Tema | Contenido |
|---|---|---|
| 6 | Continuidad | Activo-activo y activo-pasivo, sincronización entre sitios y respaldos. |
| 7 | Seguridad | Soluciones expuestas, red interna, home office y portales públicos. |
| 8 | Entrega | Ambientes de desarrollo, QA, preproducción y producción; CI/CD. |
| 9 | Tendencias | Plataformas, IA, arquitecturas de datos, FinOps, sostenibilidad. |
| 10 | Su propuesta | Cómo bajar todo lo anterior a la oferta técnico-económica. |

### Por qué esto importa en el curso

En esta asignatura ustedes son una empresa que responde a una licitación. La arquitectura es la bisagra entre lo que prometen y lo que cuesta.

| Define el alcance real | Determina el costo | Fija los riesgos | Es lo que se compara |
|---|---|---|---|
| Los módulos e integraciones que dibuje son los que después tendrá que construir, probar y cobrar. | Servidores, licencias, enlaces, respaldos y horas de operación salen del diagrama físico, no de la intuición. | Un punto único de falla o una dependencia externa mal evaluada es un riesgo que el evaluador va a buscar. | Cuando varias ofertas cumplen lo mínimo, gana la que fundamenta mejor sus decisiones técnicas. |
> **Resultado de Aprendizaje 1.** Construir la arquitectura lógica y física de la solución del caso, con estándares vigentes y las restricciones organizacionales, económicas y ambientales del contexto.

### Lo que se le pedirá en el Informe y Presentación 1

La pauta del curso es explícita sobre lo que debe aparecer. Esta clase entrega los parámetros para los tres ítems del centro.

| Ítem del informe | Qué se espera | ¿Lo cubre esta clase? |
| --- | --- | --- |
| La empresa | Quiénes son, capacidades y experiencia declarada. | No |
| El problema | Situación actual del mandante y necesidad a resolver. | No |
| Esquema de solución | Idea general de la solución propuesta. | Parcial |
| Alcance de la solución | Qué queda dentro y qué queda fuera del contrato. | Parcial |
| Arquitectura lógica | Módulos, interfaces e integraciones, trazables a las bases técnicas. | Sí |
| Arquitectura física | Servidores, redes, seguridad, tamaño de BD, uptime y tiempos de respuesta. | Sí |
| Innovaciones | Elementos diferenciadores y su justificación. | Sí |

> **Tiempo de presentación:** 15 minutos + 15 minutos de preguntas y discusión.

---

## Sección 1 · Fundamentos

- Qué es —y qué no es— la arquitectura de software
- De qué se hace cargo el arquitecto: módulos, responsabilidades, interacción, ubicación en el hardware
- Atributos de calidad: el modelo ISO/IEC 25010
- Las vistas de una arquitectura y la distinción lógica / física
- Cómo se documenta y se justifica una decisión arquitectónica

### El concepto

El concepto de arquitectura se usa de forma amplia y en campos muy distintos, por lo que su significado es algo… difuso.

| En construcción | En hardware | En una organización | En software |
| --- | --- | --- | --- |
| El arquitecto decide dónde<br>van los muros estructurales.<br>Después se puede cambiar<br>la pintura; mover un muro<br>cuesta. | Arquitectura de un<br>procesador: qué<br>componentes hay y cómo<br>se comunican entre sí. | Arquitectura empresarial:<br>cómo se relacionan<br>procesos, datos,<br>aplicaciones y tecnología. | Los elementos más<br>importantes del sistema y<br>sus relaciones: una visión<br>global. |

> En todos los casos aparece lo mismo: decisiones de estructura, tomadas temprano, que condicionan todo lo que viene después y son costosas de revertir.

### Definición

En el campo del software, la arquitectura identifica los elementos más importantes de un sistema, así como sus relaciones. Es decir, nos da una visión global del sistema.

En un sentido amplio, la Arquitectura del Software es el diseño de más alto nivel de la estructura de un sistema,

**programa o aplicación, y tiene la responsabilidad de:**

| Módulos | Responsabilidades | Interacción | Control y datos | Protocolos | Ubicación |
| --- | --- | --- | --- | --- | --- |
| Definir los<br>módulos<br>principales del<br>sistema. | Definir de qué se<br>hace cargo cada<br>uno de esos<br>módulos. | Definir cómo se<br>relacionan e<br>integran entre sí. | Definir el flujo de<br>control y el flujo<br>de datos. | Definir los<br>protocolos de<br>interacción y<br>comunicación. | Definir dónde se<br>ejecuta cada cosa<br>en el hardware. |

### No responde sólo a requisitos estructurales

Las arquitecturas de software no responden únicamente a requisitos estructurales: están relacionadas con aspectos de rendimiento, usabilidad, reutilización, restricciones económicas y tecnológicas, e incluso cuestiones estéticas.

| Rendimiento | Usabilidad | Reutilización |
| --- | --- | --- |
| Tiempos de respuesta y capacidad de<br>proceso. | Cómo se expone el sistema a quien lo<br>usa. | Qué se compra, qué se reutiliza y qué se<br>construye. |

| Restricciones económicas | Restricciones tecnológicas | Contexto y normativa |
| --- | --- | --- |
| Presupuesto de inversión y de operación<br>anual. | Plataformas, estándares y sistemas<br>heredados del mandante. | Ubicación de los datos, cumplimiento<br>legal, impacto ambiental. |

### El objetivo real

El objetivo principal de la Arquitectura del Software es aportar elementos que ayuden a la toma de decisiones y, al mismo tiempo, proporcionar conceptos y un lenguaje común que permitan la comunicación entre los equipos que participen en un proyecto.

| Decidir | Comunicar |
| --- | --- |
| ¿Compramos, arrendamos o construimos?<br>¿On-premise, nube o híbrido?<br>¿Un solo sistema o servicios separados?<br>¿Cuánta disponibilidad estamos dispuestos a pagar?<br>¿Qué se integra con los sistemas que ya tiene el mandante? | Al equipo de desarrollo: qué construir y con qué límites.<br>Al área de operaciones: qué van a tener que mantener.<br>Al mandante: qué recibe y con qué niveles de servicio.<br>Al evaluador de la licitación: por qué esta solución y no<br>otra.<br>A quien financia: en qué se gasta la inversión. |

### Tres cosas que se confunden

|   | Arquitectura | Diseño detallado | Infraestructura |
| --- | --- | --- | --- |
| Pregunta que responde | ¿Cuáles son las partes grandes y cómo se relacionan? | ¿Cómo se implementa cada parte por dentro? | ¿Sobre qué equipos y redes corre todo esto? |
| Nivel | Más alto nivel del sistema | Interior de un módulo o componente | Recursos físicos y de red |
| Artefactos típicos | Diagrama de componentes, de contexto, de despliegue, decisiones registradas | Diagrama de clases, de secuencia, modelo de datos detallado | Topología de red, inventario de servidores, esquema de respaldo |
| Quién decide | Arquitecto con el negocio | Equipo de desarrollo | Operaciones / infraestructura |
| Costo de cambiarlo | Alto: afecta a todo el proyecto | Medio: contenido en un módulo | Variable: alto on-premise, bajo en la nube |

> En su informe, la sección de arquitectura debe contener las tres, claramente separadas. Un diagrama de clases no es una arquitectura lógica y una lista de servidores no es una arquitectura física.

### Las decisiones son el producto

Una arquitectura no es un dibujo: es un conjunto de decisiones con consecuencias. Documentar la decisión vale más que documentar

**el dibujo.**

| Registro de decisión arquitectónica (ADR) | Ejemplo |
| --- | --- |
| Contexto | El mandante opera en dos regiones y exige que los datos personales permanezcan en Chile. |
| Decisión | Se despliega en nube pública con región en Chile; el respaldo se replica dentro del mismo país. |
| Alternativas evaluadas | (a) Data center propio del mandante, (b) nube pública con región extranjera, (c) esquema híbrido. |
| Fundamento | Menor inversión inicial, elasticidad ante la estacionalidad del negocio y cumplimiento de la normativa de datos personales. |
| Consecuencias | Costo mensual variable, dependencia del proveedor, necesidad de control de gasto desde el primer mes. |
| Referencia | Documentación del proveedor y normativa citada en norma APA 7.ª ed. |

> Tres o cuatro ADR bien escritos sostienen todo el capítulo de arquitectura de la oferta.

### Atributos de calidad · ISO/IEC 25010

Los atributos de calidad son los requisitos que no se ven en un caso de uso, pero que definen la arquitectura. El modelo ISO/IEC 25010:2023 los organiza en nueve características.

| Idoneidad funcional | Eficiencia de desempeño | Compatibilidad |
| --- | --- | --- |
| Completitud, corrección y pertinencia de lo<br>que el sistema hace. | Comportamiento temporal, uso de recursos,<br>capacidad. | Coexistencia con otros sistemas e<br>interoperabilidad. |

| Capacidad de interacción | Fiabilidad | Seguridad |
| --- | --- | --- |
| Aprendizaje, operabilidad, accesibilidad e<br>inclusión (antes: usabilidad). | Madurez, disponibilidad, tolerancia a fallos<br>y recuperabilidad. | Confidencialidad, integridad, no repudio,<br>autenticidad y resistencia. |

| Mantenibilidad | Flexibilidad | Seguridad operacional |
| --- | --- | --- |
| Modularidad, reutilización, analizabilidad,<br>modificabilidad, testeabilidad. | Adaptabilidad, instalabilidad,<br>reemplazabilidad y escalabilidad (antes:<br>portabilidad). | Comportamiento seguro ante fallas y<br>limitación del daño (característica nueva). |

### Los atributos que se compran y se venden

De las nueve características, hay cinco que casi siempre aparecen en las bases técnicas — y que se pagan.

| Atributo | Cómo se mide | Cómo se materializa en la arquitectura | Impacto en el costo |
| --- | --- | --- | --- |
| Rendimiento | Tiempo de respuesta (p95), transacciones por segundo | Caché, índices, balanceo, dimensionamiento de CPU/RAM | Medio |
| Disponibilidad | Uptime comprometido (99,5% / 99,9% / 99,99%) | Redundancia, múltiples zonas, failover automático | Alto |
| Escalabilidad | Usuarios concurrentes soportados sin degradación | Escalamiento horizontal, autoescalado, servicios sin estado | Medio |
| Seguridad | Controles implementados, resultado de pruebas | Segmentación de red, WAF, cifrado, gestión de identidades | Alto |
| Mantenibilidad | Tiempo medio de reparación, esfuerzo de cambio | Modularidad, contratos de interfaz claros, pruebas automatizadas | Se paga después |

> Regla práctica: cada nueve adicional de disponibilidad multiplica la complejidad y el costo de la arquitectura. No comprometa 99,99% si el caso no lo exige.

### Cómo se escribe un atributo de calidad

| Así NO se escribe | Así SÍ se escribe |
| --- | --- |
| «El sistema será rápido.»<br>«El sistema será altamente disponible.»<br>«El sistema será seguro.»<br>«El sistema soportará muchos usuarios.»<br>«La solución será escalable.» | «El 95% de las consultas de saldo responde en menos de<br>2 segundos con 500 usuarios concurrentes.»<br>«El servicio mantiene 99,9% de disponibilidad mensual<br>medido sobre el horario hábil.»<br>«Todo dato personal viaja y se almacena cifrado; el<br>acceso queda registrado y es auditable por 12 meses.»<br>«Ante un aumento de carga del 100%, el sistema agrega<br>instancias en menos de 5 minutos sin intervención<br>manual.» |

> Plantilla: ante [estímulo], en [condición de operación], el sistema [respuesta] medida en [métrica y valor]. Si no tiene número, no es un requisito: es una intención.

### Las vistas de una arquitectura

Ninguna vista muestra el sistema completo. Cada una responde una pregunta distinta y se dirige a un público distinto.

| Vista lógica | Vista de proceso | Vista de desarrollo | Vista física |
| --- | --- | --- | --- |
| Describe el modelo de objetos<br>y la funcionalidad.<br>Responde: ¿qué hace el<br>sistema y cómo se divide?<br>Público: usuario y analista. | Muestra la concurrencia y la<br>sincronía entre procesos.<br>Responde: ¿qué corre en<br>paralelo y cómo se coordina?<br>Público: integrador. | Describe la organización del<br>entorno de desarrollo.<br>Responde: ¿cómo se organiza<br>el código y los equipos?<br>Público: desarrollo. | Muestra la ubicación del<br>software en el hardware.<br>Responde: ¿dónde se ejecuta<br>cada cosa?<br>Público: operaciones. |

> +1 ESCENARIOS · Los casos de uso principales recorren y validan las cuatro vistas: si un escenario crítico no se puede trazar en todas, la arquitectura está incompleta.

### Arquitectura lógica vs. arquitectura física

| ARQUITECTURA LÓGICA | ARQUITECTURA FÍSICA |
| --- | --- |
| Organiza el software: módulos, componentes, capas,<br>servicios.<br>Muestra interfaces, integraciones y flujo de información.<br>Es independiente de la marca del servidor o del<br>proveedor de nube.<br>Se traza contra los requisitos de las bases técnicas.<br>Artefactos: diagrama de componentes, de contexto, de<br>módulos. | Organiza la ejecución: nodos, servidores, redes,<br>almacenamiento.<br>Muestra dónde se despliega cada componente lógico.<br>Depende de tecnología concreta, capacidad y ubicación<br>geográfica.<br>Se dimensiona con parámetros verificables (usuarios,<br>volumen, uptime).<br>Artefactos: diagrama de despliegue, topología de red,<br>inventario. |

> El puente entre ambas es una tabla de correspondencia: «el módulo de Facturación (lógico) se despliega en el clúster de aplicaciones, 2 instancias de 4 vCPU y 8 GB, detrás del balanceador (físico)».

### Recomendaciones para profundizar

*Sección 1 · Fundamentos*

1. **Modelo 4+1 de Kruchten** — Lea el artículo original «Architectural Blueprints: The 4+1 View Model» y aplique las cinco vistas a un sistema que ya conozca.
2. **ISO/IEC 25010:2023** — Revise las nueve características y sus subcaracterísticas en iso25000.com. Identifique las cinco que pesan en su caso.
3. **Registros de decisión (ADR)** — Busque plantillas de Architecture Decision Record y escriba tres ADR de su propio proyecto: contexto, alternativas, decisión, consecuencias.
4. **Modelo C4** — Ejemplo en c4model.com para diagramar el nivel 1 (contexto) y el nivel 2 (contenedores) de su solución con una herramienta gratuita.
5. **Escenarios de calidad** — Investigue el método ATAM y practique la plantilla estímulo – condición – respuesta – métrica con tres requisitos de su caso.

---

## Sección 2 · Arquitectura lógica

- Estilos y patrones: monolito, capas, microservicios, eventos
- Cliente-servidor, 3 capas y N capas: la familia clásica
- APIs, REST, API Gateway y los patrones de resiliencia
- Arquitectura basada en eventos y arquitecturas de datos distribuidos
- La capa de integración con servicios externos: estilos, contrato y resiliencia
- Cómo elegir un estilo con criterios explícitos
- Cuatro formas distintas de diagramar la misma arquitectura lógica

### Mapa de estilos arquitectónicos

No son opciones excluyentes ni una escalera de progreso. Son respuestas distintas a problemas distintos.

| Monolítico | Cliente-servidor | En capas (3 / N) |
| --- | --- | --- |
| Todo el código y las funcionalidades<br>acoplados en un solo paquete<br>desplegable. | Un cliente solicita, un servidor responde.<br>La forma más antigua de sistema<br>distribuido. | Presentación, lógica de negocio y datos,<br>separadas en niveles con<br>responsabilidades claras. |

| Microservicios | Basado en eventos | Serverless |
| --- | --- | --- |
| Servicios pequeños, autónomos y<br>desplegables por separado, que se<br>comunican por API. | Componentes desacoplados que<br>publican y consumen eventos a través<br>de un intermediario. | Funciones que se ejecutan por evento,<br>sin administrar servidores. Se paga por<br>uso. |

### Arquitectura monolítica

El término monolito describe al software en el que el código y las funcionalidades están acoplados en un solo paquete, lo cual funciona muy bien en ciertos escenarios.

**APLICACIÓN ÚNICA**

Interfaz de usuario Gestión de pedidos

**Base de datos única**

Facturación

una sola conexión

Inventario Reportes

| Despliegue único | Base de código compartida | Comunicación en proceso Base de datos |
| --- | --- | --- |
| Todo se publica como una sola unidad. | Un repositorio, una compilación. | Llamadas directas entre módulos, sin red de<br>por medio. |

### Monolito · ventajas y desventajas

| VENTAJAS | DESVENTAJAS |
| --- | --- |
| Simplicidad inicial: un proyecto, un despliegue, un<br>entorno.<br>Depuración directa: el error se sigue en una sola traza.<br>Pruebas de extremo a extremo sencillas.<br>Menor latencia: llamadas en memoria, no por red.<br>Transacciones simples: una sola base de datos, un solo<br>commit.<br>Menor costo de infraestructura y de operación. | Escalamiento limitado: se replica todo aunque sólo un<br>módulo esté saturado.<br>Acoplamiento fuerte: un cambio pequeño puede<br>propagarse.<br>Despliegues riesgosos: cada publicación afecta al sistema<br>completo.<br>Tecnología única: todo el sistema queda atado a un<br>lenguaje y versión.<br>Conflictos en equipos grandes trabajando sobre el<br>mismo código.<br>Al crecer, el costo de cada cambio aumenta. |

> Para la oferta: si propone un monolito, dígalo con seguridad y justifíquelo por tamaño del equipo, plazo y volumen esperado. Nadie descuenta puntaje por eso; sí lo descuentan por microservicios sin fundamento.

### El punto medio: monolito modular

La industria volvió sobre sus pasos: la recomendación más frecuente hoy es empezar con un monolito bien modularizado y extraer servicios sólo cuando exista una razón concreta.

| Un solo despliegue | Módulos con fronteras reales | Preparado para dividirse |
| --- | --- | --- |
| Se publica como una unidad: baja<br>complejidad operativa, sin<br>orquestadores ni mallas de servicio. | Cada módulo tiene su interfaz pública y<br>su propio esquema de datos; nadie<br>entra por la puerta trasera. | Cuando un módulo justifique su propio<br>ciclo de vida, se extrae con un costo<br>acotado. |

> Razones válidas para extraer un servicio: un módulo necesita escalar mucho más que el resto · un equipo distinto necesita liberar a su propio ritmo · el módulo requiere otra tecnología · el módulo tiene requisitos de seguridad o de cumplimiento distintos.

### Monolito · en la vida real

Dónde se usa hoy un monolito, y por qué en esos casos es la decisión correcta.

| Un sistema de ventas de una PyME | La gestión de un municipio pequeño | El primer producto de una startup |
| --- | --- | --- |
| Un local con tres cajas, un inventario y un<br>módulo de boletas, todo en un servidor.<br>Por qué encaja: la carga es conocida, el<br>equipo es de dos o tres personas y no hay<br>razón para repartir nada. | Permisos, patentes y atención de público<br>en una sola aplicación web.<br>Por qué encaja: presupuesto acotado, un<br>área de informática de pocas personas y<br>operación en horario hábil. | La versión inicial de casi todo producto<br>digital nace como un monolito y se divide<br>sólo cuando el crecimiento lo obliga.<br>Por qué encaja: hay que llegar rápido al<br>mercado y todavía no se sabe qué partes<br>van a crecer. |

> Regla que se repite en la industria: casi ningún sistema nace en microservicios. Nacen monolíticos y se dividen cuando el dolor lo justifica.

### Arquitectura cliente – servidor

| Elemento | Descripción |
|---|---|
| **Cliente pesado** (aplicación instalada) | Protocolo pesado. |
| **Servidor** | Recibe y procesa las solicitudes. |
| **Base de datos** | SQL remoto. |

**Se caracteriza por:**

- Clientes pesados, no estándar: hay que instalar y actualizar en cada equipo.
- Conexiones dedicadas a la base de datos, una por usuario.
- Bajo rendimiento y alto tráfico de red.
- Protocolos pesados y ejecución remota de sentencias SQL.
- Baja accesibilidad: sólo desde equipos habilitados.

### Cliente – servidor mejorada

| Elemento | Descripción |
|---|---|
| **Cliente pesado** | Aplicación instalada en el equipo del usuario. |
| **Base de datos + lógica de negocio** | Procedimientos almacenados. |

**Se caracteriza por:**

- Lógica de negocio dentro de la base de datos.
- Alta administración y baja escalabilidad.
- Clientes pesados, no estándar, con conexiones dedicadas.
- Baja flexibilidad: cambiar la regla implica tocar la base de datos.
- Mejora en rendimiento respecto del modelo anterior.
- Baja portabilidad: queda amarrada al motor y a su lenguaje propietario.

> Sigue existiendo en sistemas heredados. Si el caso del mandante incluye uno, aparecerá como restricción de integración.

### Cliente – servidor · en la vida real

Sigue vivo en sistemas antiguos que los proyectos actuales tienen que integrar o reemplazar.

| Sistemas contables de escritorio | Punto de venta de farmacia o supermercado | Sistemas clínicos y de laboratorio |
| --- | --- | --- |
| El software instalado en cada computador<br>de la oficina, conectado a la base de datos<br>del servidor de la sala.<br>Dónde se ve: contabilidad,<br>remuneraciones y facturación en<br>empresas medianas. | Cada caja es un cliente pesado que<br>conversa con el servidor de la tienda.<br>Dónde se ve: retail y farmacias. Sigue<br>siendo común porque debe funcionar<br>aunque se caiga Internet. | Aplicaciones instaladas que hablan directo<br>con la base de datos del establecimiento.<br>Dónde se ve: fichas clínicas antiguas y<br>equipos de laboratorio con software<br>propietario. |

> Para su caso: si el mandante tiene un sistema así, aparece como restricción de integración y probablemente como riesgo de migración.

### Arquitectura en 3 capas

Una aplicación de tres capas es aquella cuya funcionalidad puede ser segmentada en tres niveles lógicos.

**CAPA 1**

**CAPA 2**

**CAPA 3**

| Servicios de presentación | Servicios de negocio | Servicios de datos CAPA 3 |
| --- | --- | --- |
| navegador · app móvil · escritorio | reglas · validaciones · procesos | motor de BD · archivos · caché |

| Presentación | Negocio | Datos |
| --- | --- | --- |
| Obtiene la información del usuario, la envía<br>a los servicios de negocio, recibe los<br>resultados y los presenta. | Recibe la entrada de presentación,<br>interactúa con los servicios de datos y<br>ejecuta las operaciones para las que la<br>aplicación fue diseñada, y devuelve el<br>resultado. | Almacena, recupera y mantiene los datos, y<br>garantiza su integridad. |

### Capas (layers) y niveles (tiers)

| CAPAS · layers · lógico | NIVELES · tiers · físico |
| --- | --- |
| Es una división del software, no del hardware.<br>Presentación, negocio y datos pueden convivir en el mismo<br>servidor.<br>Se decide en el diseño del código.<br>Su objetivo es separar responsabilidades y facilitar el<br>mantenimiento.<br>Aparece en la arquitectura LÓGICA. | Es una división de la ejecución en máquinas o procesos<br>distintos.<br>Cada nivel puede escalarse, asegurarse y respaldarse por<br>separado.<br>Se decide en el despliegue.<br>Su objetivo es escalabilidad, aislamiento y seguridad.<br>Aparece en la arquitectura FÍSICA. |

> Una aplicación de 3 capas puede correr en 1 servidor (1 nivel), en 3 servidores (3 niveles) o en 30 contenedores. La cantidad de capas no determina la cantidad de máquinas: eso lo decide el dimensionamiento.

### Arquitectura N capas

La construcción de aplicaciones n-capas distribuidas ha emergido como la arquitectura predominante para aplicaciones multiplataforma en la mayor parte de las empresas.

| Cliente | WAF | Capa web | Caché | Capa de datos |
| --- | --- | --- | --- | --- |
| El modelo presenta algunas<br>Desarrollos paralelos: cada<br>Aplicaciones más robustas<br>Mantenimiento y soporte<br>más simple que modificar | desacopla<br>ventajas:<br>cada capa puede avanzar<br>gracias al encapsulamiento.<br>más sencillo: cambiar<br>un monolito. | Mensajería / cola asíncrona<br>procesos largos del ciclo petición-respuesta<br>por separado. • Mayor flexibilidad:<br>funcionalidad.<br>Alta escalabilidad:<br>un componente es<br>agregando hardware;<br>reescribir código. | se pueden añadir módulos<br>maneja más peticiones<br>el crecimiento es casi | con nueva<br>con el mismo rendimiento<br>casi lineal y no requiere |

### Capas y N capas · en la vida real

Es el estilo más frecuente en sistemas empresariales y el que probablemente propongan ustedes.

| La banca en línea | Un portal de trámites del Estado | Un sistema de matrícula universitaria |
| --- | --- | --- |
| Portal web y aplicación móvil, una capa de<br>servicios con las reglas del negocio, y el<br>sistema central con los datos.<br>Por qué encaja: separa el canal del<br>negocio, y el negocio de los datos que<br>exigen máxima protección. | Sitio público, capa de negocio con las<br>reglas del trámite, base de datos y una<br>capa de integración con otros servicios.<br>Por qué encaja: los canales cambian<br>seguido; las reglas y los datos, no. | Portal del estudiante, servicios de<br>matrícula y aranceles, base de datos<br>académica.<br>Por qué encaja: hay un peak enorme dos<br>veces al año que se resuelve agregando<br>servidores sólo en la capa web. |

> Detalle práctico: en los tres casos el peak se absorbe replicando la capa web y la de aplicación, sin tocar la base de datos. Ésa es la ventaja concreta de separar en capas.

### MVC y sus variantes

MVC no es una alternativa a las tres capas: es un patrón que organiza el interior de la capa de presentación.

| Componente | Función |
|---|---|
| **Vista** | Lo que ve el usuario. |
| **Controlador** | Interpreta la acción. |
| **Modelo** | Datos y reglas. |
| **Flujo** | El modelo actualiza la vista. |

| Patrón o enfoque | Descripción |
|---|---|
| **MVC** | Modelo–Vista–Controlador. Clásico en aplicaciones web del lado del servidor. |
| **MVVM** | Modelo–Vista–VistaModelo. Habitual en aplicaciones de escritorio y móviles con enlace de datos. |
| **Componentes** | Interfaces construidas como árbol de componentes con estado propio. Predominante en la web actual. |
| **BFF** | Backend for Frontend: una capa de servicio distinta para web y para móvil, ajustada a cada canal. |

### MVC · en la vida real

MVC no organiza el sistema completo: organiza el interior de la aplicación que el usuario ve.

| Aplicaciones web con marcos clásicos | Aplicaciones móviles | Interfaces web por componentes |
| --- | --- | --- |
| El controlador recibe la petición, pide<br>datos al modelo y elige la vista que se<br>devuelve.<br>Dónde se ve: la mayoría de los sistemas<br>de gestión construidos en la última<br>década. | La variante Modelo – Vista – VistaModelo,<br>con enlace de datos entre la pantalla y el<br>estado.<br>Dónde se ve: aplicaciones bancarias, de<br>delivery y de transporte. | El árbol de componentes con estado<br>propio reemplazó al MVC clásico en el<br>navegador.<br>Dónde se ve: portales de comercio<br>electrónico y paneles de administración. |

### Arquitectura de microservicios

La arquitectura de microservicios es un enfoque para el desarrollo de software que divide una aplicación en pequeños servicios independientes. Cada uno se ejecuta de forma autónoma y se comunica con los demás, por ejemplo a través de APIs.

| Una función de negocio | Despliegue independiente | Tecnología libre |
| --- | --- | --- |
| Cada servicio implementa una sola<br>capacidad del negocio: pedidos, pagos,<br>inventario, notificaciones. | Cada servicio se publica a producción sin<br>afectar a los demás. | Cada servicio puede escribirse en un<br>lenguaje distinto: se comunican por su API,<br>no por su código. |

| Acoplamiento flexible | Equipos pequeños | Requiere DevOps |
| --- | --- | --- |
| Se relacionan mediante contratos de API<br>estables, no mediante llamadas internas. | Un equipo dedicado puede construir y<br>operar cada servicio sin mucha coordinación<br>externa. | Es más compleja de compilar y administrar:<br>exige automatización, monitoreo y cultura<br>DevOps. |

### Microservicios · vista general

**Catálogo**

**BD propia**

**SERVICIOS**

**Web App**

**TRANSVERSALE**

**S**

**Pedidos**

**BD propia**

**API**

**Registro de servicios**

| Mobile App Web App | Gateway API |
| --- | --- |
|   | Balanceo |

| Notificaciones Catálogo Pedidos Pagos | BD propia | Seguridad S |
| --- | --- | --- |
| ⟶ red pública red privada |   |   |

> Cada servicio tiene su propio almacén de datos. Nadie consulta la base de datos de otro: si el servicio de Pedidos necesita el precio, se lo pide a Catálogo por su API. Esa regla es la que hace posible el despliegue independiente… y la que introduce la consistencia eventual.

### API · Application Programming Interface

Las API son mecanismos que permiten a dos componentes de software comunicarse entre sí mediante un conjunto de definiciones y protocolos.

| Elemento | Función |
|---|---|
| **Cliente** | Quien pide. |
| **API** | El contrato. |
| **Servicio** | Quien resuelve. |
| **Comunicación** | El cliente envía una petición y el servicio devuelve una respuesta a través de la API. |

| Componente | Qué contiene |
|---|---|
| **Endpoints** | Las URL donde la API recibe solicitudes. |
| **Métodos** | GET, POST, PUT, DELETE: la acción que se quiere realizar. |
| **Cabeceras** | Autenticación, tipo de contenido, versión y trazabilidad. |
| **Cuerpo** | Los datos que van y vuelven, normalmente en JSON o XML. |

### APIs REST

REST significa transferencia de estado representacional. Define un conjunto de operaciones que los clientes pueden usar para acceder a los datos del servidor. Clientes y servidores intercambian datos mediante HTTP.

| Método | Qué hace | Ejemplo |
| --- | --- | --- |
| GET | Recupera (o recibe) un recurso solicitado | GET /v1/productos/1024 |
| POST | Crea un recurso | POST /v1/pedidos |
| PUT | Actualiza un recurso | PUT /v1/productos/1024 |
| DELETE | Elimina un recurso | DELETE /v1/pedidos/88 |

**Anatomía de un endpoint:**

https://api.tienda.cl

/v1

/productos

/laptops

?precio_max=1000

**Base URL**

**Versión**

**Recurso**

**Sub-recurso**

**Parámetros**

> Versionar la API desde el día uno es una decisión arquitectónica: permite evolucionar sin romper a quien ya la consume.

### Otras formas de comunicar servicios

| REST / HTTP | GraphQL | gRPC |
| --- | --- | --- |
| Estándar de facto para integraciones<br>externas. Simple, universal, fácil de<br>documentar y de probar.<br>Use cuando: integra con terceros o con<br>sistemas del mandante. | El cliente declara exactamente qué datos<br>necesita, en una sola consulta.<br>Use cuando: hay muchos clientes distintos<br>con necesidades de datos muy diferentes. | Comunicación binaria de alto rendimiento<br>con contratos fuertemente tipados.<br>Use cuando: hay mucho tráfico entre<br>servicios internos y la latencia importa. |

| WebSocket / SSE | Webhooks | Colas y mensajería |
| --- | --- | --- |
| Canal permanente para enviar<br>información al cliente sin que la pida.<br>Use cuando: hay tableros en vivo, chat,<br>seguimiento o notificaciones. | El proveedor llama a una URL suya cuando<br>ocurre algo.<br>Use cuando: integra con servicios<br>externos de pago, mensajería o logística. | Comunicación asíncrona a través de un<br>intermediario que almacena el mensaje.<br>Use cuando: el proceso es largo o el<br>destino puede estar caído. |

### API Gateway

Un API Gateway actúa como intermediario entre el cliente de API y los servicios de backend, y presenta un único punto de entrada para todas las llamadas.

| Elemento | Función |
|---|---|
| **Clientes web y móvil** | Envían las llamadas a la API. |
| **API Gateway** | Recibe, autentica, aplica políticas, enruta y agrega resultados. |
| **Servicio A** | Servicio de backend. |
| **Servicio B** | Servicio de backend. |
| **Servicio C** | Servicio de backend. |

**Qué resuelve el gateway:** autenticación, límite de uso, enrutamiento, agregación, registro y trazas.

Recibe todas las llamadas dirigidas a los endpoints de la organización, las autentica, las procesa según las políticas definidas, las enruta al servicio correspondiente y devuelve el resultado agregado al cliente.

> **Cuidado:** el gateway concentra tráfico. Si no es redundante, se transforma en el punto único de falla de todo el sistema.

### Patrones de resiliencia

En un sistema distribuido, la falla parcial es lo normal. Estos patrones existen para que una falla no se propague.

| Registro de servicios | Balanceo de carga | Cortacircuitos | Reintento con espera |
| --- | --- | --- | --- |
| Directorio donde cada<br>instancia se anuncia al iniciar.<br>Permite encontrar servicios<br>sin direcciones fijas. | Reparte las peticiones entre<br>las instancias disponibles y<br>saca de rotación a las que no<br>responden. | Si un servicio falla<br>repetidamente, se deja de<br>llamar por un tiempo en vez<br>de acumular esperas. | Reintenta la operación con<br>intervalos crecientes, en vez<br>de golpear al servicio caído. |

| Tiempo límite | Compartimentos | Degradación elegante | Idempotencia |
| --- | --- | --- | --- |
| Toda llamada remota tiene<br>plazo máximo. Sin timeout,<br>una demora se convierte en<br>caída total. | Aísla recursos por servicio<br>para que la saturación de uno<br>no consuma los recursos de<br>los demás. | Ante la falla de un<br>componente secundario, el<br>sistema sigue operando con<br>funcionalidad reducida. | Repetir la misma operación no<br>produce efectos duplicados.<br>Imprescindible con reintentos. |

### Microservicios · lo que se gana y lo que se paga

| LO QUE SE GANA | LO QUE SE PAGA |
| --- | --- |
| Escalar sólo lo que está saturado.<br>Publicar a producción con frecuencia y bajo riesgo.<br>Equipos autónomos que avanzan en paralelo.<br>Tecnología adecuada a cada problema.<br>La falla de un servicio no derriba el sistema completo.<br>Reemplazar un servicio completo es viable. | Complejidad operativa: orquestación, despliegue,<br>monitoreo distribuido.<br>Latencia y fallas de red donde antes había una llamada en<br>memoria.<br>Transacciones distribuidas: se pierde el commit único.<br>Depuración difícil: un error cruza varios servicios.<br>Más infraestructura y por lo tanto más costo mensual.<br>Exige cultura DevOps y automatización desde el día uno. |

> Criterio honesto para su caso: si su equipo no puede automatizar despliegue, monitoreo y pruebas, los microservicios van a costar más de lo que aportan.

### Microservicios · en la vida real

Los casos donde los microservicios se justificaron tienen algo en común: escalas y frecuencias de cambio muy grandes.

| Plataformas de streaming de video | Comercio electrónico grande | Aplicaciones de transporte y delivery |
| --- | --- | --- |
| Catálogo, recomendaciones,<br>reproducción, facturación y perfiles, cada<br>uno como servicio independiente.<br>Por qué se justificó: la reproducción escala<br>miles de veces más que la facturación. | Búsqueda, carro, pagos, despacho e<br>inventario, con equipos distintos<br>publicando varias veces al día.<br>Por qué se justificó: en un evento de<br>descuentos el buscador y el carro se<br>saturan, el resto no. | Ubicación en tiempo real, asignación de<br>conductor, pagos y calificaciones,<br>separados y con tecnologías distintas.<br>Por qué se justificó: la ubicación exige<br>tiempo real; la facturación tolera minutos. |

> Contraste honesto para su caso: si su sistema no tiene una parte que crezca mucho más que las otras, ni varios equipos publicando en paralelo, los microservicios sólo agregan costo.

### Los datos en una arquitectura distribuida

Cuando cada servicio tiene su propia base de datos, se pierde la transacción única. Ese es el verdadero costo de los

**microservicios.**

| Consistencia eventual | Saga |
| --- | --- |
| Cada servicio es dueño de sus datos y Los datos quedan consistentes después<br>nadie más los toca directamente. Da un tiempo, no de inmediato. Hay que<br>autonomía, pero obliga a duplicar decidir si el negocio lo tolera.<br>información. | de Una transacción de negocio se<br>descompone en pasos locales, cada uno<br>con su operación de compensación si algo<br>falla. |

| CQRS | Vista materializada | Transacción outbox |
| --- | --- | --- |
| Separar el modelo de escritura del<br>modelo de lectura, para optimizar cada<br>uno por separado. | Copia de sólo lectura construida a partir<br>de los datos de varios servicios, para<br>consultas y reportes. | Guardar el evento en la misma<br>transacción que el dato, para que no se<br>pierda si el intermediario falla. |

### SOA y microservicios

|   | SOA (Service Oriented Architecture) | Microservicios |
| --- | --- | --- |
| Tamaño del servicio | Servicios grandes, alineados a procesos completos | Servicios pequeños, una capacidad de negocio cada uno |
| Comunicación | Bus de servicios empresarial (ESB) con lógica de enrutamiento y transformación | Comunicación directa por API o mensajería simple |
| Datos | Frecuentemente comparten base de datos | Cada servicio es dueño de sus datos |
| Gobierno | Centralizado, con un equipo de integración | Distribuido, cada equipo gobierna su servicio |
| Despliegue | Coordinado, por ventanas de cambio | Independiente y continuo |
| Dónde se encuentra | Grandes organizaciones, banca, sector público | Productos digitales, plataformas con alta frecuencia de cambio |

> Los microservicios son, en el fondo, una forma de SOA con gobierno distribuido y sin bus central.

### Arquitectura basada en eventos (EDA)

La arquitectura basada en eventos se basa en servicios pequeños y desacoplados que interactúan mediante la publicación, el consumo y el enrutamiento de eventos.

**Inventario**

consumidores

**Servicio de**

**Intermediario**

reaccionan al

**Pedidos**

**de mensajes**

**Facturación**

mismo evento

**(productor)**

**(broker)**

**Notificaciones**

emite: «pedido creado»

> El productor no sabe quién lo escucha ni cuántos son. Agregar un nuevo consumidor no obliga a modificar al productor: eso es el desacoplamiento, y es la razón por la que este estilo escala en cantidad de integraciones.

### EDA · beneficios y cuándo usarla

| Escalabilidad | Eficiencia | Desacoplamiento | Agilidad |
| --- | --- | --- | --- |
| Cada consumidor Agregar un<br>escala según su consumidor nuevo<br>propia carga, sin no obliga a tocar<br>arrastrar a los al productor.<br>demás. | El intermediario<br>actúa como búfer<br>elástico entre<br>servicios de<br>velocidades<br>distintas. | Productor y Si un consumidor<br>consumidor no se falla, el mensaje<br>conocen ni espera en la cola y<br>necesitan estar se procesa<br>activos al mismo después.<br>tiempo. | Nuevos procesos<br>de negocio se<br>construyen<br>escuchando<br>eventos que ya<br>existen. |

| Encaja bien cuando… Flexibilidad | Cuesta caro cuando… Resiliencia |
| --- | --- |
| Un mismo hecho de negocio dispara varias acciones<br>distintas.<br>Hay procesos largos que no deben bloquear al usuario.<br>Se integran muchos sistemas con disponibilidad variable.<br>Se necesita histórico de lo que ocurrió, no sólo el estado<br>actual. | El negocio exige respuesta inmediata y consistente.<br>El equipo no tiene experiencia operando colas y<br>reintentos.<br>No hay trazabilidad: seguir un flujo asíncrono sin<br>observabilidad es muy difícil.<br>Se usa para todo, incluso donde una llamada directa<br>bastaba. |

### Eventos · en la vida real

Un hecho de negocio ocurre una vez y desencadena varias acciones que no dependen entre sí.

| Una compra en línea | Transporte público y logística | Detección de fraude bancario |
| --- | --- | --- |
| Se emite «pedido pagado» y reaccionan:<br>inventario descuenta stock, bodega<br>prepara el despacho, contabilidad emite la<br>boleta y el cliente recibe un correo.<br>Ninguno de ellos necesita esperar a los<br>otros. | Cada lectura de posición o de tarjeta es un<br>evento que alimenta el tablero de control,<br>la facturación y el análisis posterior.<br>El mismo evento sirve a tres áreas<br>distintas. | Cada transacción se publica como evento:<br>un servicio la evalúa en tiempo real, otro<br>la registra y un tercero alimenta el reporte<br>regulatorio. |

> Señal de que su caso pide eventos: cuando en las bases aparece varias veces la frase «al ocurrir X, el sistema debe además…».

### Streaming, CQRS y event sourcing

| Event streaming | CQRS | Event sourcing |
| --- | --- | --- |
| El evento no se consume y se borra:<br>queda en un registro ordenado y<br>persistente que varios consumidores<br>pueden leer a su ritmo, incluso volver<br>atrás.<br>Habilita analítica en tiempo real y<br>reprocesos. | Separar el camino de escritura del<br>camino de lectura. Cada uno se modela<br>y se escala por separado.<br>Útil cuando el sistema lee mucho más<br>de lo que escribe, o cuando los reportes<br>ahogan la operación. | El estado no se guarda: se guarda la<br>secuencia completa de eventos que lo<br>produjeron, y el estado se reconstruye.<br>Da auditoría perfecta, pero complica las<br>consultas y las correcciones. |

> Advertencia para la oferta: estos tres patrones resuelven problemas reales, pero también son los que más se proponen sin necesidad. Si los incluye, tiene que poder explicar qué requisito del caso los exige.

### Arquitectura hexagonal y limpia

No es un estilo de despliegue sino de organización interna: mantener las reglas de negocio independientes de la tecnología que las rodea.

**adaptadores · infraestructura**

**Interfaz web**

**Base de datos**

**casos de uso**

**API externa**

**Proveedor de pago**

**DOMINIO**

**Mensajería**

**Almacenamiento**

> Beneficio concreto para su oferta: si el dominio no depende del proveedor, migrar de on-premise a nube — o cambiar de nube — deja de ser una reescritura y pasa a ser un cambio de adaptador.

### La capa de integración

Ninguna solución vive sola. La capa de integración es el conjunto de componentes cuya única responsabilidad es conversar con lo que está fuera de su sistema.

**ERP del mandante**

**CAPA DE**

| SU SISTEMA Módulos de negocio | INTEGRACIÓN adaptadores traducción resiliencia CAPA DE registro |
| --- | --- |
|   | Correo y SMS |

> Por qué se separa: el sistema externo cambia de versión, se cae, cambia de formato o cambia de proveedor. Si esa conversación está repartida por todo el código, cada cambio del tercero se convierte en un cambio en su sistema completo.

### Estilos de integración con terceros

| API síncrona (REST/SOAP) | Webhook / notificación | Cola / mensajería |
| --- | --- | --- |
| Usted llama y espera respuesta.<br>Use cuando: el usuario necesita el resultado<br>ahora (consultar stock, autorizar un pago).<br>Riesgo: si el tercero se demora, su sistema<br>se demora. | El tercero le llama a usted cuando ocurre<br>algo.<br>Use cuando: el resultado llega después<br>(confirmación de pago, estado de un envío).<br>Riesgo: hay que exponer un endpoint y<br>validar su origen. | Usted deja el mensaje y alguien lo procesa.<br>Use cuando: el proceso es largo o el destino<br>puede estar caído.<br>Riesgo: exige manejar orden, duplicados y<br>reintentos. |

| Archivo por lote | Replicación / CDC | Base de datos compartida |
| --- | --- | --- |
| Intercambio de archivos por SFTP en horario<br>fijo.<br>Use cuando: el mandante tiene sistemas<br>antiguos. Sigue siendo muy común en el<br>sector público.<br>Riesgo: latencia de horas y errores<br>silenciosos. | Los cambios de una base se propagan a<br>otra.<br>Use cuando: hay que alimentar reportería o<br>un sistema analítico.<br>Riesgo: acopla los modelos de datos de<br>ambos sistemas. | Su sistema consulta directamente la base<br>del otro.<br>Es un antipatrón: cualquier cambio de<br>esquema del tercero rompe su sistema, sin<br>aviso y sin contrato.<br>Evítelo, y si las bases lo exigen, declárelo<br>como riesgo. |

### Los terceros que suelen aparecer

Antes de dibujar, haga la lista. Cada integración tiene esfuerzo de desarrollo, ambiente de pruebas, costo por transacción y un dueño al otro lado del teléfono.

| Identidad | Medios de pago | Documento tributario | Firma electrónica |
| --- | --- | --- | --- |
| Autenticación de usuarios con<br>un proveedor externo o con el<br>directorio del mandante. | Pasarelas y bancos. Cobran<br>por transacción y exigen<br>certificación. | Emisión y validación de<br>documentos electrónicos ante<br>la autoridad. | Firma avanzada de<br>documentos y su verificación<br>posterior. |

| Notificaciones | ERP / sistemas del mandante | Georreferenciación | Logística y despacho |
| --- | --- | --- | --- |
| Correo, SMS y mensajería.<br>Cobran por mensaje enviado. | El sistema que ya existe y con<br>el que hay que convivir. Suele<br>ser el más difícil. | Mapas, direcciones y rutas.<br>Cobran por consulta. | Estados de envío, etiquetas,<br>seguimiento. |

### El contrato de integración

**Ocho preguntas que hay que responder por cada tercero antes de estimar el esfuerzo.**

| Pregunta | Por qué importa | Qué pasa si no lo pregunta |
| --- | --- | --- |
| ¿Qué protocolo y formato usa? | Define el trabajo de desarrollo y las bibliotecas necesarias. | Descubre a mitad de camino que es SOAP con firma XML. |
| ¿Cómo se autentica? | Certificados, tokens o llaves cambian el diseño y la operación. | Aparece un trámite de certificación de tres semanas. |
| ¿Hay ambiente de pruebas? | Sin sandbox no se puede desarrollar ni probar de verdad. | Se prueba en producción, con datos reales. |
| ¿Cuántas llamadas permite? | Los límites de uso condicionan el diseño y obligan a cachear. | El sistema falla en hora punta por exceso de llamadas. |
| ¿Qué disponibilidad ofrece? | Su SLA no puede ser mejor que el del tercero del que depende. | Compromete 99,9% apoyado en un servicio que ofrece 99%. |
| ¿Tiene costo por transacción? | Costo variable de operación: al flujo de caja. | Aparece con el primer mes de uso real. |
| ¿Cómo versiona su interfaz? | Cuánto aviso hay antes de un cambio que rompe. | Un día la integración deja de operar. |
| ¿Quién responde ante un problema? | Contraparte, canal y tiempos de respuesta. | Nadie responde y usted incumple. |

> Las respuestas van al informe: son supuestos declarados y, varias de ellas, riesgos con responsable asignado.

### Resiliencia frente al tercero

Regla: su sistema no puede caerse porque se cayó el de otro. Diseñe siempre el comportamiento ante la falla del tercero.

| Reintento con espera | Cortacircuitos |
| --- | --- |
| Toda llamada externa tiene plazo máximo, Reintentar con intervalos crecientes y un<br>siempre. Sin timeout, la demora del tercero máximo de intentos. Nunca reintentar<br>se transforma en caída suya. bucle inmediato. | Tras N fallas seguidas se deja de llamar por<br>en un tiempo y se responde de inmediato con<br>el modo alternativo. |

| Idempotencia | Cola de reintento | Modo degradado |
| --- | --- | --- |
| Cada operación lleva una clave única para<br>que un reintento no genere un pago o un<br>pedido duplicado. | Lo que no se pudo enviar queda en una<br>cola, y lo que falla definitivamente en una<br>cola de mensajes muertos, para revisión<br>humana. | Qué hace el sistema mientras tanto: aceptar<br>y procesar después, usar el último dato<br>conocido, o avisar con claridad al usuario. |

> En la defensa le van a preguntar: «¿y si la pasarela de pago está caída?». La respuesta correcta describe el modo degradado, el reintento y el aviso al usuario — no «no debería pasar».

### Seguridad de la integración

| Aspecto | Medida mínima esperada | Dónde se declara en la oferta |
| --- | --- | --- |
| Canal | Todo el tráfico cifrado con TLS vigente. Sin excepciones, tampoco en la red interna. | Arquitectura física y de seguridad |
| Autenticación mutua | Certificados de cliente o llaves rotadas periódicamente para servicio a servicio. | Ficha de integración |
| Autorización | Credenciales con el mínimo privilegio necesario y de uso exclusivo de esa integración. | Modelo de accesos |
| Integridad | Firma del mensaje cuando el tercero la ofrece, para verificar que no fue alterado. | Ficha de integración |
| Origen del webhook | Validar firma y lista de direcciones permitidas: un endpoint público es un blanco. | Arquitectura de seguridad |
| Secretos | Llaves y contraseñas en un almacén de secretos, nunca en el código ni en el repositorio. | Procedimiento de despliegue |
| Registro | Trazabilidad de cada llamada, sin escribir datos personales ni credenciales en los registros. | Plan de observabilidad |
| Datos personales | Enviar sólo lo necesario. El tercero que trata datos por usted es un encargado y requiere acuerdo. | Restricciones legales |

### Ficha de integración para el informe

Una ficha por cada sistema externo. Es la evidencia de que la integración está pensada, no supuesta.

| Campo | Ejemplo |
| --- | --- |
| Sistema externo | Pasarela de pago del banco recaudador |
| Requisito que lo justifica | RQ-08 · Pago en línea de la solicitud |
| Sentido del flujo | Saliente (autorización) y entrante (confirmación por webhook) |
| Estilo y protocolo | API REST sobre HTTPS + webhook firmado |
| Autenticación | Credenciales de cliente OAuth 2.0, rotación semestral |
| Volumen estimado | 1.200 transacciones diarias; peak de 90 por minuto |
| Disponibilidad del tercero | 99,5% mensual según su acuerdo publicado |
| Comportamiento ante falla | Reintento con espera creciente (3 intentos), cortacircuito a los 5 errores, modo degradado: la solicitud queda pendiente de pago |
| Ambiente de pruebas | Sandbox del proveedor, credenciales solicitadas en la semana 2 |
| Costo asociado | Comisión por transacción: va al flujo de caja como costo variable |
| Riesgo declarado | Dependencia de tercero; probabilidad media, impacto alto; mitigación: otro medio de pago |

### Hexagonal · en la vida real

Se nota cuando algo del entorno cambia: si el dominio está aislado, cambia sólo el adaptador.

| Cambiar de medio de pago | Migrar de on-premise a la nube | Reemplazar el motor de base de datos |
| --- | --- | --- |
| El sistema deja de usar una pasarela y<br>contrata otra.<br>Con el dominio aislado se escribe un<br>adaptador nuevo y el resto del sistema no<br>se toca. | El almacenamiento de archivos pasa de<br>una carpeta compartida a<br>almacenamiento de objetos.<br>Cambia el adaptador de archivos, no la<br>lógica del negocio. | El mandante decide dejar un motor<br>propietario por uno libre.<br>Si el acceso a datos está detrás de una<br>interfaz, la migración es acotada. |

> Argumento para la oferta: «el dominio no depende del proveedor; cambiar de pasarela, de nube o de motor implica sustituir un adaptador, no reescribir el sistema».

### Cómo elegir el estilo

| Criterio | Monolito / monolito modular | Microservicios | Basado en eventos |
| --- | --- | --- | --- |
| Tamaño del equipo | 1 a 10 personas | Varios equipos autónomos | Varios equipos |
| Plazo del proyecto | Corto: menos de 6 meses | Largo, con evolución continua | Medio a largo |
| Carga esperada | Predecible y acotada | Muy variable o muy alta | Picos e integraciones múltiples |
| Necesidad de escalar por partes | Baja | Alta | Alta |
| Frecuencia de cambio | Baja o media | Alta | Alta |
| Madurez DevOps requerida | Baja | Alta | Alta |
| Costo de infraestructura | Bajo | Alto | Medio-alto |
| Complejidad de operación | Baja | Alta | Alta |

> En la defensa le van a preguntar «¿por qué esta arquitectura?». La respuesta correcta nunca es «porque es moderna»: es «porque el caso exige X y esta opción lo resuelve con el menor costo total».

### No hay una sola forma de dibujarla

Existen muchas formas de diagramar una arquitectura lógica, y la elección depende del problema y de la solución. Éstos son cuatro estilos que funcionan bien en una oferta técnica.

| A · Actores en columnas, capas en filas | B · Bandas por capa, actores arriba |
| --- | --- |
| cada columna es un actor o proceso; cada fila, una capa | bandas de color por capa y líneas de flujo entre módulos |

| C · Capas con microservicios y stack lateral | D · Columnas verticales por capa |
| --- | --- |
| columna lateral con tecnologías y servicios externos | cliente · presentación · negocio · servicios · datos |

### Cuál estilo conviene

**El estilo no es un tema estético: determina qué se ve a primera vista y qué queda escondido.**

| Estilo | Qué destaca a primera vista | Cuándo conviene | Riesgo |
| --- | --- | --- | --- |
| A · Actores en columnas, capas en filas | Quién usa qué, y por qué capa pasa cada actor. | Casos con varios perfiles muy distintos y procesos separados: servicios públicos, utilities, salud. | Con muchos actores la lámina se vuelve ilegible: agrupe por proceso, no por persona. |
| B · Bandas por capa con actores arriba | El recorrido completo de arriba hacia abajo y las dependencias entre módulos. | Soluciones de tamaño medio con varios departamentos usando el mismo núcleo. | Las líneas de flujo se cruzan; use colores por flujo y una leyenda. |
| C · Capas con microservicios y stack lateral | La descomposición en servicios y la tecnología de cada capa. | Cuando la propuesta se apoya en microservicios y hay que mostrar el stack elegido. | Mezcla decisiones lógicas con tecnológicas: separe la columna de stack visualmente. |
| D · Columnas verticales por capa | La separación limpia cliente – presentación – negocio – servicios – datos. | Soluciones con muchas aplicaciones y APIs bien delimitadas; es la más fácil de leer. | Oculta quién usa qué: agregue flechas por actor con color. |

> Todas son correctas. Elija una, aplíquela de forma consistente y explíquela en 30 segundos al comenzar la presentación.

### Reglas para que el diagrama se entienda

| Una dirección de lectura | Agrupación explícita | Leyenda | Nombres de negocio |
| --- | --- | --- | --- |
| Izquierda a derecha o arriba<br>abajo, pero una sola. El lector<br>no debería tener que buscar<br>por dónde empezar. | Cajas o bandas que marquen<br>las capas y las zonas. Sin<br>agrupación, veinte<br>rectángulos son ruido. | Qué significa cada color, cada<br>tipo de línea y cada forma. Si<br>usa flechas de colores por<br>flujo, la leyenda es obligatoria. | «Módulo de Facturación», no<br>«MS-FACT-01». El diagrama<br>lógico lo tiene que entender el<br>mandante. |

| Un nivel por lámina | Máximo 15 a 20 elementos | Sistemas externos distinguibles | Coherencia con el resto |
| --- | --- | --- | --- |
| No mezcle módulos con clases<br>ni con servidores. Si necesita<br>bajar el detalle, haga otra<br>lámina. | Si no cabe, el problema no es<br>la lámina: es que el diagrama<br>está intentando decir dos<br>cosas a la vez. | Lo que no construye usted va<br>con otro color o fuera del<br>borde del sistema. Marca la<br>frontera del alcance. | Los nombres del diagrama<br>deben ser los mismos del<br>texto, de la matriz de<br>trazabilidad y del presupuesto. |

### Estilo A · actores en columnas, capas en filas

Columnas verticales por actor o proceso; bandas horizontales por capa técnica.

| Proceso 1 | Proceso 2 | Proceso 3 | Proceso 4 |
| --- | --- | --- | --- |
| quién<br>por<br>los<br>las<br>lo |   |   | Actores<br>Portales y aplicaciones<br>Lógica de negocio<br>Datos<br>Servicios de integración |

> Se lee así: la columna dice de quién es el proceso; la fila dice en qué capa está el componente. Ejemplo: «Lectura de medidores» tiene su aplicación móvil, su módulo de control, su base de datos y su servicio de integración.

### Estilo A · cuándo usarlo y qué cuidar

| Cuándo conviene | Qué cuidar |
| --- | --- |
| El caso tiene varios perfiles muy distintos que casi no se<br>cruzan: cliente, técnico en terreno, funcionario, call center.<br>Las bases técnicas están organizadas por proceso de<br>negocio.<br>Hay que mostrar que cada proceso tiene su propia cadena<br>completa, de la interfaz hasta los datos.<br>El mandante es una organización con áreas separadas y<br>quiere reconocer la suya en el diagrama. | Con más de cinco o seis columnas la lámina se vuelve<br>ilegible: agrupe por proceso, no por persona.<br>Las líneas que cruzan columnas se enredan: use pocas y<br>hágalas explícitas.<br>Es fácil terminar dibujando el organigrama en vez del<br>sistema.<br>Necesita una banda de título por capa a la izquierda; sin<br>ella, nadie entiende las filas. |

> Ejemplo real de este estilo: la arquitectura de una empresa sanitaria, con columnas para lectura de medidores, facturación, instalación y mantención, y atención de clientes.

### Estilo B · bandas por capa, actores arriba

Una banda de color por capa, con los actores en la parte superior. Las relaciones se dibujan como líneas de colores que cruzan las bandas, y cada color es un flujo de negocio distinto.

**Actores**

**Portales y aplicaciones**

**Módulos de negocio**

**Servicios**

**Bases de datos**

> las líneas de color son los flujos de negocio: cada color recorre una funcionalidad completa a través de las capas Obligatorio en este estilo: una leyenda que diga qué representa cada color de línea.

### Estilo C · capas con microservicios y stack lateral

Al centro, las capas del sistema, con la de microservicios desglosada en servicios y módulos. A los costados, dos columnas: el stack tecnológico y los servicios externos contratados.

| Hardware y software | Servicios externos |
| --- | --- |
| Capa de aplicación<br>Capa de microservicios<br>Capa de persistencia |   |

> Riesgo de este estilo: mezcla decisiones lógicas con decisiones tecnológicas. Separe visualmente las columnas laterales y diga en la presentación que son anexos, no parte de la arquitectura lógica.

### Estilo D · columnas verticales por capa

Una columna por capa, de izquierda a derecha, en el orden en que viaja una petición: cliente, presentación, negocio, servicios y datos. Las flechas de color indican qué actor recorre qué camino.

**Capa de**

**Capa de**

**Capa de**

**Capa de**

**Capa de**

**cliente**

**presentación**

**negocio (APIs)**

**servicios**

**datos**

> Es el estilo más legible y el más fácil de defender. Su límite: no muestra quién usa qué, así que hay que agregar flechas de color por actor y su leyenda.

### Los cuatro estilos, en una frase

| A · Actores en columnas | B · Bandas por capa | C · Capas con microservicios | D · Columnas por capa |
| --- | --- | --- | --- |
| Muestra quién usa qué.<br>Elíjalo si su caso tiene<br>perfiles muy distintos y<br>procesos separados. | Muestra el recorrido<br>completo y las<br>dependencias.<br>Elíjalo si varios<br>departamentos usan un<br>mismo núcleo. | Muestra la descomposición<br>en servicios y la tecnología.<br>Elíjalo si la propuesta se<br>apoya en microservicios. | Muestra la separación limpia<br>entre capas.<br>Elíjalo si quiere el diagrama<br>más legible y fácil de explicar. |

> No existe el estilo correcto: existe el estilo consistente. Elija uno, aplíquelo en todas las láminas y explíquelo en treinta segundos al abrir la presentación.

### Ejemplo de Trabajo de años anteriores

![Ejemplo de trabajo anterior (página 68)](imagenes/fep01-000.jpg)

### Ejemplo de Trabajo de años anteriores

![Ejemplo de trabajo anterior (página 69)](imagenes/fep01-001.jpg)

### Ejemplo de Trabajo de años anteriores

![Ejemplo de trabajo anterior (página 70)](imagenes/fep01-002.jpg)

### Ejemplo de Trabajo de años anteriores

![Ejemplo de trabajo anterior (página 71)](imagenes/fep01-003.png)

### Recomendaciones para profundizar

*Sección 2 · Arquitectura lógica*

1. **Monolito modular** — Lea sobre «modular monolith» y sobre el patrón strangler fig. Prepare el argumento de por qué su caso parte modular.
2. **Patrones de integración** — Revise el catálogo clásico de Enterprise Integration Patterns e identifique cuáles aplican a las integraciones de su caso.
3. **Diseño de APIs REST** — Estudie una guía de diseño de APIs y documente una de sus interfaces con OpenAPI, incluyendo versión y códigos de error.
4. **Saga y consistencia eventual** — Busque ejemplos del patrón saga con compensación y decida si su caso tolera consistencia eventual o no.
5. **Bosqueje su diagrama** — Elija uno de los cuatro estilos, dibuje su arquitectura lógica e intercámbiela con otro grupo: si no la entienden sin explicación, todavía no sirve.

---

## Sección 3 · Arquitectura física

- Las 7 capas del modelo OSI y dónde actúa cada componente de su arquitectura
- Topología on-premise: perímetro, DMZ, balanceo, servidores, datos y respaldo
- El data center: energía, climatización, seguridad física y niveles TIER
- Virtualización y contenedores: máquina virtual vs. contenedor
- Motor de base de datos, base de datos y almacenamiento: tres cosas distintas
- Dimensionamiento con parámetros verificables y costos CAPEX
- Master, worker e hipervisor: por qué se necesitan y en qué cantidad
- Los niveles RAID y cuántos discos hay que comprar para la capacidad prometida

### ¿Qué es la arquitectura física?

La vista física muestra la ubicación del software en el hardware. Responde una sola pregunta: ¿dónde se ejecuta cada cosa, y sobre qué se ejecuta?

| Nodos | Artefactos | Conexiones |
| --- | --- | --- |
| Equipos físicos o virtuales donde se<br>ejecuta software: servidores,<br>contenedores, dispositivos. | Lo que se despliega en cada nodo:<br>aplicaciones, servicios, bases de datos,<br>agentes. | Redes, protocolos, puertos y anchos de<br>banda entre nodos. |

| Ubicación | Capacidad | Redundancia |
| --- | --- | --- |
| Dónde están físicamente esos nodos: sala<br>del mandante, data center, región de<br>nube. | Cuánto puede procesar cada nodo: CPU,<br>memoria, disco, entrada/salida. | Qué está duplicado, qué no lo está y qué<br>pasa cuando algo falla. |

### Las 7 capas del modelo OSI

El modelo OSI describe la comunicación en red como siete capas, cada una con una responsabilidad acotada. Cada capa usa los servicios de la de abajo y presta servicio a la de arriba.

| # | Capa | De qué se hace responsable | Unidad | Ejemplos |
| --- | --- | --- | --- | --- |
| 7 | Aplicación | Expone el servicio al software: define el significado de la conversación. | Datos | HTTP/HTTPS, DNS, SMTP, FTP, gRPC |
| 6 | Presentación | Formato, codificación, compresión y cifrado del contenido. | Datos | TLS, JSON/XML, UTF-8, JPEG |
| 5 | Sesión | Establece, mantiene y cierra el diálogo entre dos extremos. | Datos | Sesiones TLS, RPC, NetBIOS |
| 4 | Transporte | Entrega extremo a extremo: puertos, fiabilidad y control de flujo. | Segmento | TCP, UDP, QUIC, puertos 80/443/1433 |
| 3 | Red | Direccionamiento lógico y enrutamiento entre redes distintas. | Paquete | IP, ICMP, enrutadores, subredes, NAT |
| 2 | Enlace de datos | Entrega dentro del mismo segmento físico y detección de errores. | Trama | Ethernet, MAC, VLAN, switches |
| 1 | Física | Transmisión de bits por el medio: señales, conectores, cableado. | Bit | Cobre, fibra, Wi-Fi, patch panel |

> Regla mnemotécnica de abajo hacia arriba: Física, Enlace, Red, Transporte, Sesión, Presentación, Aplicación.

### Su arquitectura, mapeada sobre OSI

Cada componente de la arquitectura física actúa en una capa determinada. Saber cuál explica qué puede hacer ese componente… y qué no.

WAF · API Gateway · balanceador de capa 7 · CDN · Entiende URLs, cabeceras y contenido. Puede enrutar por ruta, bloquear

**7 · Aplicación**

servidor web

inyección SQL y limitar por usuario. Aquí se cifra y se descifra. Decidir dónde termina el TLS es una decisión de

**6 · Presentación**

Terminación TLS · certificados · compresión

arquitectura y de seguridad.

Sesiones de usuario · sesiones persistentes en el Aquí aparece el problema del estado: si la sesión vive en el nodo, no puede

**5 · Sesión**

balanceador

escalar horizontalmente.

Balanceador de capa 4 · grupos de seguridad · reglas por Sólo ve IP y puerto: es más rápido, pero no puede decidir según el

**4 · Transporte**

puerto

contenido de la petición.

**3 · Red**

Enrutadores · firewall perimetral · VPN · subredes · NAT Aquí se hace la segmentación de red: quién puede alcanzar a quién.

**2 · Enlace**

Switches · VLAN · agregación de enlaces

Separación lógica dentro del mismo cableado. Relevante on-premise. Redundancia de camino físico: dos proveedores distintos, no dos contratos

**1 · Física**

Cableado · fibra · enlaces del proveedor · energía

con el mismo.

### Para qué le sirve OSI en la oferta

| Ordenar el diagrama físico | Elegir el balanceo correcto |
| --- | --- |
| Dibuje de abajo hacia arriba: enlaces, red y segmentación,<br>transporte, y recién arriba el balanceo y la aplicación. El diagrama se<br>vuelve legible y demuestra criterio. | Capa 4 reparte por IP y puerto: rápido y barato. Capa 7 lee la<br>petición: puede enrutar por ruta, hacer despliegue progresivo y<br>aplicar reglas por usuario. Cuesta más. |

| Ubicar cada control de seguridad | Diagnosticar y dimensionar |
| --- | --- |
| Firewall en capa 3-4, WAF en capa 7, cifrado en capa 6,<br>segmentación en capa 2-3. Defensa en profundidad significa<br>exactamente esto: un control por capa. | Ante un problema, se descarta capa por capa. Y la latencia total es la<br>suma de lo que aporta cada capa: enlace, enrutamiento, TLS y<br>proceso de la aplicación. |

Redacción tipo para el informe: «El balanceador opera en capa 7 para permitir enrutamiento por ruta y despliegue progresivo; el filtrado por

puerto se resuelve en capa 4 mediante grupos de seguridad, y la segmentación entre subredes en capa 3.»

### Del diagrama lógico al de despliegue

La arquitectura física no se inventa: se deriva. Cada componente lógico tiene que aterrizar en algún nodo, y esa correspondencia se declara.

| Componente lógico | Nodo de despliegue | Dimensionamiento | Redundancia |
| --- | --- | --- | --- |
| Portal web de clientes | Servidores web (granja) | 2 × 2 vCPU / 4 GB | Activo-activo tras balanceador |
| Módulo de pedidos | Servidores de aplicación | 2 × 4 vCPU / 8 GB | Activo-activo |
| Módulo de facturación | Servidores de aplicación | 1 × 4 vCPU / 8 GB | Activo-pasivo |
| Base de datos transaccional | Clúster de base de datos | 2 × 8 vCPU / 32 GB / 500 GB SSD | Réplica sincrónica + failover |
| Almacén de documentos | Almacenamiento de objetos | 2 TB con crecimiento de 40 GB/mes | Replicado |
| Integración con el ERP del mandante | Servidor de integración | 1 × 2 vCPU / 4 GB | Reintento y cola de respaldo |

> Los valores del ejemplo son ilustrativos: en su informe cada cifra debe derivarse del volumen de operación declarado en las bases.

### Topología clásica on-premise

**ZONA**

**Usuarios · Internet**

el tráfico llega desde fuera

**PÚBLICA**

**Firewall perimetral**

filtra y publica sólo lo necesario

**Balanceador de carga / proxy inverso**

**DMZ**

reparte, corta TLS, saca nodos caídos

**Servidores web ×2**

capa de presentación

**RED INTERNA**

**Servidores de aplicación ×2**

lógica de negocio

**Clúster de base de datos (activo + réplica)**

datos transaccionales

**ZONA DE**

**Almacenamiento SAN + Respaldo**

persistencia y recuperación

**DATOS**

### Segmentación de la red

La regla básica: cada zona sólo puede conversar con la siguiente. Nunca se publica una base de datos a Internet.

| DMZ | Red de aplicación |
| --- | --- |
| Sólo se exponen los puertos 80 y 443 Zona intermedia donde viven proxy<br>hacia Internet. Todo lo demás está inverso, balanceador y WAF. No guarda<br>cerrado por defecto. datos sensibles. | Subred privada, sin acceso directo desde<br>Internet. Sólo acepta tráfico desde la capa<br>web. |

| Red de datos | Red de gestión | Acceso remoto |
| --- | --- | --- |
| Máximo aislamiento. Sólo acepta<br>conexiones desde la capa de aplicación,<br>en el puerto del motor. | Segmento separado para administración,<br>monitoreo y respaldo. Acceso restringido<br>y auditado. | VPN o bastión con doble factor. Nunca<br>administración expuesta directamente a<br>Internet. |

> Defensa en profundidad: si un atacante supera una capa, todavía tiene otra por delante. En su oferta esto se traduce en equipos concretos (firewall, WAF) y en reglas declaradas, no en la frase «la solución será segura».

### Las zonas de red, en un diagrama

Cada zona es un anillo. El tráfico sólo puede avanzar hacia el anillo siguiente, nunca saltarse uno.

**menos**

**INTERNET**

sin control: todo lo que llega es sospechoso

**cualquiera, no confiable**

**confianza**

**ZONA PÚBLICA · perímetro**

firewall perimetral + protección DDoS

**sólo puertos 80 y 443 expuestos**

**DMZ · zona desmilitarizada**

no guarda datos sensibles; publica servicios

**proxy inverso, balanceador, WAF**

**RED DE APLICACIÓN**

sin salida directa a Internet; sólo acepta a la

**servidores de aplicación**

**RED DE DATOS**

máximo aislamiento; sólo acepta a la capa de

**más**

| protección confianza menos más | bases de datos y almacenamiento proxy inverso, balanceador, WAF sólo puertos 80 y 443 expuestos DMZ · zona desmilitarizada ZONA PÚBLICA · perímetro cualquiera, no confiable servidores de aplicación |
| --- | --- |
| Regla única: | cada zona sólo conversa con la siguiente, y nunca al revés por iniciativa propia. |

### El data center

Cuando la solución vive en instalaciones del mandante, la infraestructura de soporte también es parte de la arquitectura y del costo.

**Energía**

**Climatización**

**Seguridad física**

Alimentación redundante, UPS y grupo

Temperatura y humedad controladas, con

Control de acceso, cámaras, detección y

electrógeno. Sin energía no hay

redundancia. El calor es la principal causa de

extinción de incendios, registro de ingreso.

disponibilidad.

falla.

**Conectividad**

**Espacio y racks**

**Operación**

Enlaces redundantes con proveedores

Gabinetes, piso técnico, pasillos fríos y

Personal, turnos, monitoreo, mantenimiento

distintos y cableado estructurado certificado.

calientes, capacidad de crecimiento.

preventivo y contratos de soporte.

| Nivel TIER | Redundancia | Disponibilidad aproximada | Inactividad anual estimada |
| --- | --- | --- | --- |
| TIER I | Sin redundancia | 99,671% | ≈ 28,8 horas |
| TIER II | Componentes redundantes | 99,741% | ≈ 22,0 horas |
| TIER III | Mantenimiento sin detener el servicio | 99,982% | ≈ 1,6 horas |
| TIER IV | Tolerante a fallas, todo duplicado | 99,995% | ≈ 0,4 horas |

### Del servidor físico a la virtualización

La evolución ha sido pasar de servidores físicos en un data center, a servidores virtuales en ese mismo data center, a servidores virtuales en la nube, a contenedores dentro de servidores virtuales, y ahora a informática sin servidor.

**1**

**2**

**3**

**4**

| Servidor físico 1 | Virtualización 2 | Contenedores 3 | Serverless 4 |
| --- | --- | --- | --- |
| Una aplicación por equipo.<br>Uso típico del hardware: 10 a<br>20%. Máximo aislamiento,<br>máximo desperdicio. | Un hipervisor divide un<br>equipo físico en varias<br>máquinas virtuales, cada una<br>con su sistema operativo. | Varias aplicaciones<br>comparten el mismo sistema<br>operativo, aisladas entre sí.<br>Arrancan en segundos. | Ni siquiera se administra el<br>servidor: se despliega la<br>función y la plataforma<br>resuelve el resto. |

> Cada escalón reduce el desperdicio de capacidad y la carga de administración, y aumenta la dependencia de la plataforma que hay debajo.

### ¿Qué es un contenedor?

Un paquete de software estándar — el contenedor — agrupa el código de una aplicación con sus bibliotecas y archivos de configuración, junto con las dependencias necesarias para que se ejecute. En esencia, virtualiza el sistema operativo a nivel de aplicación.

| El problema que resuelve | Lo que aporta |
| --- | --- |
| «En mi máquina funciona»: la aplicación se comporta<br>distinto al cambiar de entorno.<br>Las diferencias vienen de versiones de bibliotecas y de<br>configuración del sistema.<br>Cada paso — desarrollo, pruebas, producción — exige<br>ajustes manuales.<br>El despliegue depende de documentación que siempre está<br>desactualizada. | Infraestructura ligera e inmutable para empaquetar e<br>implementar.<br>La misma imagen corre en el portátil del desarrollador y en<br>producción.<br>Arranque en segundos y consumo muy inferior al de una<br>máquina virtual.<br>Permite mover la aplicación entre entornos sin cambios, o<br>con cambios mínimos. |

### Máquina virtual vs. contenedor

**MÁQUINAS VIRTUALES**

**CONTENEDORES**

| App | App |
| --- | --- |
| bibliotecas | bibliotecas |

**App**

**App**

**Sistema operativo**

**Sistema operativo**

**invitado**

**invitado**

**bibliotecas**

**bibliotecas**

**Hipervisor**

**Motor de contenedores**

**Sistema operativo anfitrión**

**Sistema operativo**

**Hardware**

**Hardware**

> La máquina virtual virtualiza el hardware y carga un sistema operativo completo por instancia. El contenedor virtualiza el sistema operativo: menos peso, arranque más rápido, menor aislamiento.

### Dimensionar: de la demanda al hardware

Dimensionar no es elegir un servidor grande: es una cadena de razonamiento que parte del negocio y termina en

**una cifra defendible.**

1. Usuarios

2. Concurrencia

3. Operaciones

4. Recursos

5. Capacidad

6. Holgura

% simultáneo en hora transacciones por CPU, RAM, E/S por

+ crecimiento y

totales y activos

nodos necesarios

punta

segundo

transacción

redundancia

**Ejemplo trabajado:**

| Paso | Dato o supuesto | Resultado |
| --- | --- | --- |
| Usuarios registrados declarados en las bases | 12.000 | — |
| Usuarios activos en hora punta (supuesto: 10%) | 1.200 concurrentes | — |
| Operaciones por usuario por minuto (supuesto: 4) | 4.800 op/min | 80 operaciones por segundo |
| Capacidad medida por instancia de aplicación | 35 op/s | 3 instancias |
| Holgura de crecimiento (30%) y tolerancia a fallas (N+1) | — | 4 instancias de aplicación |

### Parámetros de dimensionamiento

| Recurso | Qué determina la cifra | Señal de que quedó corto | Cómo se declara en la oferta |
| --- | --- | --- | --- |
| CPU (vCPU) | Operaciones por segundo y complejidad del procesamiento | Uso sostenido sobre 70%, tiempos de respuesta que suben | N.º de vCPU por nodo y cantidad de nodos |
| Memoria (RAM) | Sesiones activas, caché en memoria, tamaño del conjunto de trabajo | Uso de intercambio en disco, reinicios por falta de memoria | GB por nodo |
| Almacenamiento | Volumen inicial + crecimiento mensual × horizonte + retención | Alertas de espacio, respaldos que no caben | GB o TB, con la tasa de crecimiento |
| Rendimiento de disco | Operaciones de entrada/salida por segundo del motor de datos | Esperas de disco, consultas lentas sin causa aparente | IOPS y tipo de disco (SSD/NVMe) |
| Red | Tamaño medio de respuesta × operaciones por segundo | Saturación del enlace en hora punta | Mbps por enlace y redundancia |
| Licencias | Núcleos, usuarios nominados o instancias, según el fabricante | Costo que aparece después de la adjudicación | Modelo y cantidad, con su costo anual |

> Todo supuesto se declara. «Se estima un 10% de concurrencia en hora punta, según el patrón de uso descrito en las bases» es defendible; una cifra sin origen no lo es.

### Dimensionamiento de la base de datos

| Tecnología | Tamaño | Uptime |
| --- | --- | --- |
| Relacional para transacciones,<br>documental para datos flexibles, clave-<br>valor para caché, columnar para analítica.<br>Justifique la elección con el tipo de dato<br>del caso. | Registros iniciales × tamaño medio de fila<br>+ índices + crecimiento mensual ×<br>horizonte de evaluación + margen.<br>Declare la fórmula, no sólo el número. | Disponibilidad comprometida y esquema<br>que la sostiene: réplica sincrónica, failover<br>automático, ventana de mantenimiento<br>acordada. |

| Tiempos de respuesta | Retención y purga | Respaldo y recuperación |
| --- | --- | --- |
| Meta por tipo de consulta, medida en<br>percentil 95. Diferencie consulta<br>transaccional de reporte. | Cuánto tiempo se conserva cada tipo de<br>dato, qué se archiva y qué se elimina.<br>Impacta directamente en el tamaño. | Frecuencia, tipo (completo/incremental),<br>destino, y sobre todo: tiempo que toma<br>restaurar. Un respaldo que nunca se<br>probó no es un respaldo. |

> Regla 3-2-1 de respaldo: tres copias de los datos, en dos medios distintos, con una fuera del sitio. Es un estándar citable y barato de justificar en la oferta.

### Motor, base de datos y almacenamiento

**Tres cosas distintas, tres decisiones distintas y tres líneas distintas en el presupuesto.**

| Motor de base de datos | Base de datos | Almacenamiento (storage) |
| --- | --- | --- |
| El SOFTWARE que administra los datos:<br>recibe consultas, controla concurrencia,<br>garantiza integridad, gestiona respaldos y<br>seguridad.<br>Es un producto: tiene versión, licencia,<br>requisitos de hardware y ciclo de soporte.<br>En el presupuesto: licencia y mantención<br>anual, o costo del servicio gestionado. | El CONJUNTO DE DATOS y su estructura:<br>tablas, índices, relaciones, vistas y<br>procedimientos, que el motor administra.<br>Es lo que usted diseña: modelo, volumen,<br>crecimiento, retención.<br>En el presupuesto: no cuesta por sí misma,<br>pero determina el tamaño del<br>almacenamiento y la capacidad del motor. | El MEDIO FÍSICO O LÓGICO donde quedan<br>escritos los bytes: discos, cabina, volumen<br>en la nube, almacenamiento de objetos.<br>Se caracteriza por capacidad, velocidad<br>(IOPS y latencia), durabilidad y<br>disponibilidad.<br>En el presupuesto: precio por GB al mes o<br>inversión en cabina, más el respaldo. |

> Analogía: el motor es el bibliotecario, la base de datos es el catálogo y la colección ordenada, y el almacenamiento son las estanterías y el edificio.

### Motores más usados y cuándo elegir cada uno

| Motor | Tipo | Licencia | Fortaleza | Cuándo elegirlo |
| --- | --- | --- | --- | --- |
| PostgreSQL | Relacional | Libre | Muy completo, extensible, soporta JSON y datos geográficos | Opción por defecto para un sistema transaccional nuevo |
| MySQL / MariaDB | Relacional | Libre | Simple, muy difundido, enorme comunidad | Aplicaciones web de complejidad moderada |
| SQL Server | Relacional | Propietaria | Integración con el ecosistema Microsoft y herramientas de BI | El mandante ya opera con tecnología Microsoft |
| Oracle Database | Relacional | Propietaria | Muy robusto en cargas grandes; fuerte en banca y sector público | Ya existe la plataforma y el personal; la licencia es cara |
| MongoDB | Documental | Mixta | Esquema flexible, escalado horizontal natural | Datos semiestructurados o de forma variable |
| Redis | Clave-valor | Mixta | En memoria, latencia de microsegundos | Caché, sesiones y colas, no como almacén principal |
| Elasticsearch / OpenSearch | Búsqueda | Mixta | Búsqueda de texto y análisis de registros | Buscador del portal y centralización de logs |
| SQLite | Embebido | Libre | Sin servidor, un solo archivo | Aplicaciones locales o de escritorio; nunca multiusuario |

> Advertencia de costo: en los motores propietarios la licencia se cuenta por núcleo o por usuario. Duplicar servidores para alta disponibilidad puede duplicar la licencia.

### Tipos de almacenamiento

| Tipo | Qué es | Se usa para | Ventaja | Límite |
| --- | --- | --- | --- | --- |
| Bloque | Un disco crudo que el sistema operativo formatea y monta (SAN, volumen en la nube). | Bases de datos, sistemas de archivos de los servidores, máquinas virtuales. | Latencia mínima y control total del formato. | Se conecta a un solo servidor a la vez; caro por GB. |
| Archivo | Un sistema de archivos compartido en red, con carpetas y permisos (NAS, NFS/SMB). | Documentos compartidos entre varios servidores, archivos de aplicación comunes. | Varios servidores lo montan al mismo tiempo. | Menor rendimiento; no escala indefinidamente. |
| Objeto | Cada archivo es un objeto con metadatos, accesible por API HTTP. | Documentos escaneados, imágenes, respaldos, archivos estáticos del portal. | Capacidad prácticamente ilimitada, muy barato, durabilidad altísima. | No se monta como disco; no sirve para bases de datos. |

> Regla práctica para su oferta: la base de datos va en almacenamiento de bloque con SSD y una cifra de IOPS declarada. Los documentos y las imágenes van en almacenamiento de objetos, no dentro de la base de datos: guardar archivos en la base multiplica su tamaño, encarece la licencia del motor y hace lentos los respaldos.

### El costo real de una solución on -premise

El servidor es la parte visible. El costo total incluye todo lo que hay que comprar, mantener y renovar durante el horizonte de evaluación.

| Categoría | Ítems típicos | Naturaleza |
| --- | --- | --- |
| Hardware | Servidores, almacenamiento, switches, firewall, UPS, racks | Inversión (CAPEX) |
| Software base | Sistemas operativos, virtualización, motor de base de datos, respaldo | Inversión + mantención anual |
| Instalación | Habilitación de sala, cableado, energía, climatización, puesta en marcha | Inversión (CAPEX) |
| Operación | Personal de operaciones, turnos, monitoreo, soporte del fabricante | Costo anual (OPEX) |
| Conectividad | Enlaces, redundancia de proveedor, direcciones IP, certificados | Costo anual (OPEX) |
| Energía y espacio | Consumo eléctrico, climatización, arriendo del espacio | Costo anual (OPEX) |
| Renovación | Reemplazo de hardware al final de su vida útil (3 a 5 años) | Reinversión en el flujo |

> Todos estos ítems se van a repetir en el flujo de caja del proyecto. Levantarlos ahora evita rehacer la evaluación económica después.

### Cómo se dibuja una arquitectura física

Si el diagrama lógico responde «de qué partes se compone», el físico responde «dónde corre y cuánto aguanta». Debe permitir dos lecturas: la de fallas y la de costos.

| Zonas de red visibles | Nodos con su capacidad | Redundancia explícita |
| --- | --- | --- |
| Cajas que agrupen Internet, borde, subred<br>pública, subred de aplicación y subred de<br>datos. La segmentación se ve de un<br>vistazo. | Cada nodo con su dimensionamiento<br>anotado: «2 × 4 vCPU / 8 GB». Sin cifras es<br>un dibujo, no una arquitectura. | Qué está duplicado y en cuántas zonas. Lo<br>que aparece una sola vez es un punto<br>único de falla. |

| Protocolos y puertos | Nombres de servicio | Frontera del alcance |
| --- | --- | --- |
| En las líneas importantes: HTTPS 443, el<br>puerto del motor de datos, el túnel IPsec. | Si es nube, el nombre del producto: no<br>«balanceador» sino «Application Load<br>Balancer». Es lo que después se cotiza. | Qué provee usted, qué es del mandante y<br>qué es de un tercero. Tres colores bastan,<br>con su leyenda. |

> Prueba rápida: si al mirar su diagrama físico no puede señalar con el dedo qué componente falla primero ni cuál es el más caro del mes, todavía le falta información.

### Cuándo on-premise sigue siendo la respuesta correcta

| Normativa o contrato | Latencia física | Carga estable y predecible |
| --- | --- | --- |
| El mandante está obligado a mantener los<br>datos en instalaciones propias o dentro de<br>un perímetro determinado. | El sistema controla equipos, planta<br>industrial o procesos que no toleran la<br>latencia de una red externa. | Sin picos ni estacionalidad, la elasticidad<br>de la nube no aporta y el costo mensual<br>termina siendo mayor. |

| Inversión ya realizada | Conectividad limitada | Integración con equipamiento |
| --- | --- | --- |
| El mandante tiene data center vigente,<br>licencias y personal. Migrar sería destruir<br>valor. | La operación está en una zona sin enlace<br>confiable: depender de Internet sería el<br>mayor riesgo del proyecto. | El sistema debe conversar con hardware<br>específico que sólo está disponible en la<br>red local. |

> Lo que el evaluador castiga no es elegir on-premise ni elegir nube: es no haber comparado. La decisión debe salir de un cuadro con criterios explícitos.

### Tres piezas que hay que entender antes

En cualquier inventario de infraestructura moderna va a leer «Master», «Worker» e «hipervisor». Son tres cosas de niveles distintos, y confundirlas lleva a dimensionar mal.

| Hipervisor | Nodo Master (manager) | Nodo Worker |
| --- | --- | --- |
| Software que parte un servidor físico en<br>varias máquinas virtuales.<br>NIVEL: entre el hardware y el sistema<br>operativo.<br>Ejemplos: VMware ESXi, Proxmox, Hyper-<br>V, KVM. | Máquina virtual que decide QUÉ se<br>ejecuta y DÓNDE. Guarda el estado del<br>clúster.<br>NIVEL: plano de control del orquestador.<br>Ejemplo: Docker Swarm manager,<br>Kubernetes control plane. | Máquina virtual que EJECUTA los<br>contenedores. Aporta la capacidad real de<br>cómputo.<br>NIVEL: plano de trabajo del orquestador.<br>Ejemplo: Docker Swarm worker,<br>Kubernetes node. |

> El hipervisor crea las máquinas virtuales; el orquestador reparte contenedores entre esas máquinas virtuales. Son dos repartos distintos, uno sobre el otro.

### Plano de control y plano de trabajo

El orquestador separa dos responsabilidades: decidir y ejecutar. Esa separación es la razón de que existan dos tipos de nodo.

**PLANO DE CONTROL · nodos Master**

**PLANO DE TRABAJO · nodos Worker**

**Master 1**

**Master 2**

**Master 3**

**Worker 1**

**Worker 2**

**Worker 3**

| contenedores Worker 1 | contenedores Worker 2 | contenedores Worker 3 |
| --- | --- | --- |
| Mantienen el estado deseado del clúster Ejecutan<br>Deciden en qué nodo corre cada contenedor Aportan la CPU<br>Se ponen de acuerdo entre sí por consenso (Raft) Se agregan<br>Exponen la API de administración No participan | los contenedores de la<br>y la memoria que consume<br>o se quitan para escalar horizontalmente<br>del consenso: su caída no | aplicación<br>el sistema<br>afecta al clúster |

> El master decide y no trabaja. El worker trabaja y no decide. Por eso se dimensionan distinto: el master necesita poca memoria y disco rápido; el worker necesita CPU y memoria.

### Qué hace exactamente un nodo Master

| Guarda el estado deseado | Programa los contenedores | Reconcilia |
| --- | --- | --- |
| Qué servicios deben existir, con cuántas<br>réplicas, en qué red y con qué<br>configuración. Es la «verdad» del clúster. | Elige en qué worker corre cada réplica,<br>según recursos libres, etiquetas y reglas<br>de reparto. | Compara continuamente lo que hay con lo<br>que debería haber. Si un contenedor<br>muere, lo vuelve a levantar en otro nodo. |

| Mantiene el consenso | Expone la API y la red | Gestiona secretos y certificados |
| --- | --- | --- |
| Los masters replican el estado entre ellos<br>con el algoritmo Raft. Uno es líder; el<br>resto lo sigue y lo reemplaza si cae. | Recibe los comandos de administración y<br>publica la red interna del clúster y el<br>enrutamiento entre servicios. | Guarda contraseñas y claves cifradas y<br>rota los certificados internos entre nodos. |

> Consecuencia de dimensionamiento: el master no necesita mucha memoria (16 GB en el caso), pero sí disco rápido y baja latencia de red, porque el consenso escribe en disco en cada cambio. En producción se recomienda no ejecutar carga de la aplicación en los masters.

### Qué hace exactamente un nodo Worker

| Ejecuta contenedores | Reporta su estado | Aporta la capacidad |
| --- | --- | --- |
| Recibe la orden del master y levanta los<br>contenedores asignados, con sus límites<br>de CPU y memoria. | Informa periódicamente cuánto recurso<br>tiene libre y si sus contenedores están<br>sanos. | La suma de vCPU y RAM de los workers es<br>la capacidad real del sistema. Los masters<br>no cuentan para eso. |

| Escala horizontalmente | Es reemplazable | No guarda estado |
| --- | --- | --- |
| Cuando la carga crece, se agregan<br>workers. No hay que reconfigurar la<br>aplicación. | Si un worker cae, el master reprograma<br>sus contenedores en los que quedan. Por<br>eso deben sobrar recursos. | Todo lo que deba persistir va a la base de<br>datos o al almacenamiento compartido,<br>nunca al disco local del worker. |

> Regla de capacidad: si tiene 3 workers y quiere sobrevivir a la caída de uno, cada worker no puede pasar del 66% de uso. Ese margen se cotiza, no se improvisa.

### ¿Por qué tres masters, y no uno ni dos?

Los masters se ponen de acuerdo por consenso: sólo pueden decidir si hay quórum, es decir, si está disponible más de la mitad de ellos. Quórum = parte entera de (N ÷ 2) + 1.

| N.º de masters | Quórum necesario | Fallas que tolera | Veredicto |
| --- | --- | --- | --- |
| 1 | 1 | 0 | Punto único de falla del plano de control |
| 2 | 2 | 0 | Peor que uno: hay dos equipos que pueden romperlo |
| 3 | 2 | 1 | Mínimo razonable en producción |
| 4 | 3 | 1 | Un equipo más, sin ganar tolerancia: no se justifica |
| 5 | 3 | 2 | Para clústeres grandes o repartidos en dos salas |
| 7 | 4 | 3 | Máximo práctico: más masters hacen el consenso más lento |

> Siempre un número impar, y tres es el primero que tolera una falla. Ése es el «por qué 3» que se lee en todos los documentos de arquitectura: no es superstición, es aritmética del quórum.

### El quórum, en un diagrama

**1 master · quórum 1**

**2 masters · quórum 2**

**3 masters · quórum 2**

**Master 1**

**Master 1**

**Master 2**

**Master 1 Master 2 Master 3**

**CAÍDO**

**CAÍDO**

**activo**

**CAÍDO**

**activo**

**activo**

| Quedan 0 de 1 < quórum 1 1 master · quórum 1 | Queda 1 de 2 < quórum 2 | Quedan 2 de 3 ≥ quórum 2 3 masters · quórum 2 |
| --- | --- | --- |
| Cae el único master: nadie puede reprogramar Cae<br>nada. Clúster | uno de dos: queda 1 y el quórum exige 2. Cae<br>bloqueado. Sigue | uno de tres: quedan 2 y el quórum exige 2.<br>operando. |

> Sin quórum el clúster no se cae: lo que ya está corriendo sigue corriendo, pero nadie puede desplegar, escalar ni recuperar un servicio caído.

### ¿Y cuántos workers?

El número de masters lo fija el quórum. El número de workers lo fija la capacidad más el margen para sobrevivir a la caída de uno.

| Paso | Cómo se obtiene | Ejemplo trabajado |
| --- | --- | --- |
| 1. Demanda de recursos | Suma de CPU y memoria que piden todos los contenedores en hora punta | 48 vCPU y 84 GB solicitados |
| 2. Capacidad por worker | Recursos de la máquina virtual menos lo que consume el sistema operativo | 8 vCPU y 32 GB, útiles ≈ 7 vCPU y 28 GB |
| 3. Workers mínimos | Demanda ÷ capacidad útil, redondeado hacia arriba | 48 ÷ 7 ≈ 7 … limitado por memoria: 84 ÷ 28 = 3 |
| 4. Margen por falla (N+1) | Un worker más, para absorber la caída de cualquiera | 3 + 1 = 4 nodos si se quiere tolerancia plena |
| 5. Ajuste por presupuesto | Se acepta operar degradado tras una falla y se deja el mínimo | 3 workers, con 66% de uso máximo |

> La configuración habitual es 3 workers, uno por servidor físico. No es casualidad: así la caída de un servidor se lleva un solo worker, y los dos que quedan deben poder absorber su carga.

### ¿Por qué se necesita un hipervisor?

Un clúster típico pide entre 6 y 14 nodos. Los servidores físicos que se compran son 1, 2 o 3. El hipervisor es lo que hace

**posible esa diferencia.**

| Sistemas operativos distintos | Aislamiento de fallas |
| --- | --- |
| Un clúster necesita al menos 3 masters. Es habitual que convivan Oracle Linux,<br>Comprar 3 servidores físicos sólo para el Rocky Linux y Windows Server en la<br>plano de control sería absurdo: se crean misma solución. No pueden coexistir en<br>como máquinas virtuales. un mismo sistema operativo: exigen<br>máquinas separadas. | Un núcleo que se cuelga o una<br>actualización que sale mal afectan a una<br>máquina virtual, no a todo el servidor. |

| Límites de recursos por nodo | Movilidad y respaldo | Aprovechamiento del hardware |
| --- | --- | --- |
| Se fija cuánta CPU, memoria y disco<br>puede usar cada nodo. Sin eso, un<br>proceso desbocado se lleva el equipo<br>completo. | Una máquina virtual se mueve a otro<br>servidor, se clona para pruebas y se<br>respalda completa. Un servidor físico no. | Un servidor físico dedicado a una función<br>se usa al 10-20%. Con varias máquinas<br>virtuales encima se llega al 60-70%. |

> Costo asociado: el hipervisor se licencia (por socket o por núcleo en los productos comerciales) y consume del orden de un 10% de la CPU y la memoria del equipo. Ambas cosas se cotizan.

### Cuándo sí y cuándo no se cotiza un hipervisor

| Se cotiza como línea aparte | No se cotiza como línea aparte |
| --- | --- |
| Solución on-premise con servidores propios del mandante.<br>Producto comercial: VMware vSphere, Microsoft Hyper-V<br>con System Center, Nutanix.<br>Se licencia por socket o por núcleo físico, con soporte<br>anual.<br>Hay que sumar además la consola de administración y el<br>respaldo de máquinas virtuales.<br>Alternativas libres: Proxmox VE, KVM/oVirt, XCP-ng. Sin<br>licencia, con soporte opcional pagado. | Nube pública: el hipervisor es del proveedor y está incluido<br>en el precio por hora de la instancia.<br>Servicios de contenedores gestionados: ni siquiera se ve la<br>máquina virtual.<br>Servidores dedicados en arriendo con hipervisor incluido<br>en el contrato.<br>Nodos físicos dedicados (bare metal) donde cada nodo del<br>clúster es un equipo completo: no hay virtualización.<br>Contenedores directamente sobre el sistema operativo del<br>servidor, sin capa intermedia. |

> Error frecuente en las ofertas: cotizar instancias de nube y además licencias de virtualización. Se está pagando dos veces lo mismo.

### Las capas, de abajo hacia arriba

Cada capa toma el recurso de la de abajo y lo reparte entre varios consumidores de la de arriba. Hay dos repartos superpuestos: el del hipervisor y el del orquestador.

Frontend, Server, Processor, Workflow: lo que realmente ejecuta

**Contenedores · servicios de la plataforma**

negocio Reparte los contenedores entre los nodos. Aquí actúan masters y

**Docker Swarm · orquestador**

workers

**Motor de contenedores**

Aísla procesos dentro de un mismo sistema operativo

Los nodos del clúster: masters, workers, base de datos y servicios

**Máquinas virtuales · un sistema operativo cada una**

especiales Reparte CPU, memoria y disco del servidor entre las máquinas

**Hipervisor**

virtuales

**Arreglo RAID**

Convierte discos sueltos en un volumen tolerante a fallas

**Servidores físicos**

CPU, memoria, discos, tarjetas de red, fuentes, energía y sala

> Cada capa se puede cambiar sin tocar las de arriba: ése es el valor de la separación, y también la razón de que haya tantas piezas que cotizar.

### RAID: qué es y qué no es

RAID — arreglo redundante de discos independientes — combina varios discos físicos para que el sistema operativo vea un solo volumen, más rápido, más grande o más tolerante a fallas.

| Qué resuelve | Las tres palancas |
| --- | --- |
| Que la rotura de un disco no detenga el sistema ni destruya los<br>datos, y que varios discos trabajando juntos den más velocidad. | División en franjas (striping) para velocidad, espejo (mirroring) para<br>redundancia y paridad para redundancia barata. |

| Siempre hay un costo | Lo que NO resuelve |
| --- | --- |
| La redundancia se paga en capacidad: parte de los discos comprados<br>no almacena datos útiles. Ese factor entra en la cotización. | Borrado accidental, corrupción lógica, cifrado por ransomware,<br>incendio de la sala. Para eso está el respaldo, que es otra cosa. |

> Frase para el informe: «El arreglo RAID protege la continuidad ante falla de un disco; la protección ante pérdida lógica de datos se resuelve con la política de respaldo descrita en el punto X.»

### RAID 0 · división en franjas (striping)

**Disco 1**

**Disco 2**

**El archivo se parte en bloques y se reparten entre los discos**

**A1**

**A2**

**A3**

**A4**

**A5**

**A6**

| Aspecto | RAID 0 |
| --- | --- |
| Discos mínimos | 2 |
| Capacidad útil | 100% de la capacidad comprada |
| Tolera fallas | Ninguna: si muere un disco, se pierde todo el volumen |
| Velocidad de lectura | Muy alta: los discos trabajan en paralelo |
| Velocidad de escritura | Muy alta |
| Riesgo real | Con 2 discos, la probabilidad de falla del conjunto es el doble que la de uno solo |
| Cuándo usarlo | Datos temporales, caché, espacio de trabajo que se puede volver a generar |

> Regla: RAID 0 aumenta el rendimiento y aumenta el riesgo. Nunca para datos que no se puedan volver a producir.

### RAID 1 · espejo (mirroring)

**Disco 1**

**Disco 2 (espejo)**

**Cada bloque se escribe idéntico en los dos discos**

**A1**

**A1**

**A2**

**A2**

**A3**

**A3**

| Aspecto | RAID 1 |
| --- | --- |
| Discos mínimos | 2 |
| Capacidad útil | 50% de la capacidad comprada: 2 discos de 1 TB dan 1 TB útil |
| Tolera fallas | 1 disco. El sistema sigue funcionando sin interrupción |
| Velocidad de lectura | Buena: se puede leer de cualquiera de los dos |
| Velocidad de escritura | Igual a la de un disco solo: hay que escribir dos veces |
| Reconstrucción | Simple y rápida: se copia el disco sano al de reemplazo |
| Cuándo usarlo | Disco de arranque del sistema operativo y del hipervisor: es la regla del caso |

> Por eso el documento dice «la máquina física debe estar en RAID 1»: se refiere a los discos desde donde arranca el servidor, no al almacenamiento de datos.

### RAID 5 · franjas con paridad distribuida

**Disco 1**

**Disco 2**

**Disco 3**

**Ap, Bp, Cp = bloques de paridad, repartidos**

**A1**

**A2**

**Ap**

**B1**

**Bp**

**B2**

Si muere el disco 2, el bloque A2 se recalcula con A1 y Ap. El

volumen sigue disponible, pero degradado.

**Cp**

**C1**

**C2**

| Aspecto | RAID 5 |
| --- | --- |
| Discos mínimos | 3 |
| Capacidad útil | (N − 1) discos: con 5 discos de 1 TB quedan 4 TB útiles |
| Tolera fallas | 1 disco |
| Penalización de escritura | Cada escritura implica 4 operaciones de disco: leer dato, leer paridad, escribir dato, escribir paridad |
| Riesgo de reconstrucción | Con discos grandes puede tardar horas o días, con el arreglo degradado y sin margen |
| Cuándo usarlo | Archivos y datos de lectura predominante, con discos de capacidad moderada |

### RAID 6 · doble paridad

**Disco 1**

**Disco 2**

**Disco 3**

**Disco 4**

**A1**

**A2**

**Ap**

**Aq**

**Bq**

**B1**

**B2**

**Bp**

Dos bloques de paridad independientes por franja: p y q. Se puede reconstruir aunque falten dos discos.

| Aspecto | RAID 6 |
| --- | --- |
| Discos mínimos | 4 |
| Capacidad útil | (N − 2) discos: con 6 discos de 1 TB quedan 4 TB útiles |
| Tolera fallas | 2 discos simultáneos |
| Penalización de escritura | 6 operaciones por escritura: es el más lento para escribir |
| Ventaja clave | Sobrevive a que falle un segundo disco mientras se reconstruye el primero |
| Cuándo usarlo | Arreglos grandes de discos de alta capacidad, con datos de lectura predominante |

### RAID 10 · espejo y franjas combinados

RAID 1 + 0: primero se forman parejas en espejo, y después los datos se reparten en franjas entre esas parejas.

**ESPEJO 1**

**ESPEJO 2**

**Disco 1**

**Disco 2**

**Disco 3**

**Disco 4**

Se puede perder

**A1**

**A1**

**A2**

**A2**

franjas

un disco de cada espejo sin perder

**A3**

**A3**

**A4**

**A4**

el volumen

| Aspecto | RAID 10 |
| --- | --- |
| Discos mínimos | 4, y siempre un número par |
| Capacidad útil | 50% de la capacidad comprada |
| Tolera fallas | Hasta la mitad del arreglo (1 por espejo); 2 del mismo espejo lo destruyen |
| Velocidad de escritura | La mejor de todos: no hay que calcular paridad |
| Reconstrucción | Rápida y de bajo riesgo: se copia el disco espejo, sin recalcular el arreglo |
| Cuándo usarlo | Bases de datos, máquinas virtuales y carga de escritura intensa: la regla del caso |

### Los niveles RAID, comparados

| Nivel | Discos mín. | Capacidad útil | Tolera | Escritura | Factor de compra | Uso típico |
| --- | --- | --- | --- | --- | --- | --- |
| RAID 0 | 2 | 100% | 0 discos | Muy rápida | ×1,0 | Datos temporales |
| RAID 1 | 2 | 50% | 1 disco | Normal | ×2,0 | Disco de arranque |
| RAID 5 | 3 | (N−1)/N | 1 disco | Lenta (4 E/S) | ×1,25 a ×1,5 | Archivos, lectura |
| RAID 6 | 4 | (N−2)/N | 2 discos | Muy lenta (6 E/S) | ×1,3 a ×1,5 | Arreglos grandes |
| RAID 10 | 4 | 50% | 1 por espejo | La más rápida | ×2,0 | Bases de datos, VM |
| RAID 50 | 6 | (N−g)/N | 1 por grupo | Media | ×1,2 a ×1,4 | Arreglos grandes mixtos |
| RAID 60 | 8 | (N−2g)/N | 2 por grupo | Lenta | ×1,3 a ×1,5 | Archivo masivo |

> El «factor de compra» es la cifra que se lleva al presupuesto: capacidad útil requerida × factor = capacidad bruta que hay que comprar. En RAID 10 se compra el doble.

### El disco de reserva (hot spare) y la reconstrucción

Un disco de reserva es un disco instalado, encendido y sin usar, que el controlador incorpora automáticamente cuando otro falla.

1. Operación normal

Todos los discos sanos. El spare espera sin datos.

2. Falla un disco

El arreglo queda degradado: sigue funcionando, pero sin redundancia.

3. Entra el spare

El controlador lo incorpora en segundos, sin intervención humana.

4. Reconstrucción

Se recalculan o se copian los datos al spare. Horas, con el arreglo más lento.

5. Redundancia restaurada

El arreglo vuelve a tolerar una falla. Se reemplaza el disco muerto y pasa a ser el nuevo spare.

> Sin spare, la ventana de riesgo dura desde que falla el disco hasta que alguien va físicamente al data center a cambiarlo: pueden ser días. Con spare, dura minutos. Un disco adicional es barato comparado con perder el arreglo.

### Tres reglas de disco de un documento real, explicadas

**Un documento de arquitectura real fija estas tres reglas de disco. Ninguna es arbitraria.**

**«La máquina física debe estar en RAID 1»**

Se refiere a los discos desde donde arranca el servidor: sistema operativo e hipervisor. Con dos discos en espejo, si uno muere el equipo sigue arrancado y

encendido. Es poco espacio, así que perder el 50% no importa; y no se justifica calcular paridad para eso.

**«El storage debe ser 5 discos SSD iguales, como mínimo, en RAID 10, más spare»**

Los datos y las máquinas virtuales escriben mucho: RAID 10 es el único nivel sin penalización de paridad. Iguales, porque en un arreglo todos los discos se usan

al tamaño del más pequeño. SSD, por los IOPS que exige la base de datos. Y el spare, para que la reconstrucción empiece sola.

**«Cada disco debe tener la mitad de la capacidad total»**

> Es la consecuencia directa del 50% de RAID 10: cuatro discos de C/2 en espejo y franjas dan exactamente C de capacidad útil. El quinto disco, del mismo tamaño, es el de reserva.

### Por qué «la mitad de la capacidad total»

**Supongamos que su solución necesita 8 TB de capacidad útil para datos y archivos.**

| Paso | Valor | Por qué |
| --- | --- | --- |
| Capacidad útil requerida | 8 TB | Sale del dimensionamiento: volumen inicial + crecimiento × horizonte + retención |
| Nivel elegido | RAID 10 | Escritura intensiva de base de datos y máquinas virtuales |
| Capacidad útil de RAID 10 | 50% | La mitad de los discos guarda la copia espejo |
| Tamaño de cada disco | 8 TB ÷ 2 = 4 TB | «La mitad de la capacidad total»: cada disco es de C/2 |
| Discos del arreglo | 4 discos de 4 TB | Dos espejos de 4 TB, en franjas: 4 + 4 = 8 TB útiles |
| Disco de reserva | +1 disco de 4 TB | El «más spare» que pide la regla |
| Se compran | 5 discos SSD de 4 TB | 20 TB brutos para 8 TB útiles: factor de compra ×2,5 |

> Ese factor ×2,5 es lo que hay que llevar al presupuesto. Cotizar 8 TB de discos cuando el diseño exige 20 TB brutos es el error de costeo más caro del dimensionamiento de almacenamiento.

### Cabina compartida o discos en cada servidor

Con un clúster de tres servidores es posible no usar almacenamiento externo, pero entonces cada máquina debe tener capacidad total: el espacio a comprar se triplica.

**Con cabina de almacenamiento externa**

**Con discos en cada servidor**

- Un solo arreglo compartido por los tres servidores.

- Cada equipo lleva su propio arreglo completo.

- 8 TB útiles → 5 discos de 4 TB → 20 TB brutos, una sola

- 8 TB útiles × 3 equipos → 15 discos de 4 TB → 60 TB

vez.

brutos.

- Los tres equipos ven el mismo volumen: cualquier

- No hay cabina que comprar ni red de almacenamiento

máquina virtual arranca en cualquiera.

que instalar.

- Costo adicional: la cabina, sus controladoras

- La replicación entre servidores la hace el software, no el

redundantes y la red de almacenamiento.

hardware.

- Riesgo: la cabina pasa a ser el punto único de falla si no

- Factor de compra efectivo: ×7,5 sobre la capacidad útil.

es redundante.

> Comparar estas dos alternativas con cifras — y no con adjetivos — es exactamente lo que se espera de la evaluación técnico-económica de su oferta.

### Lista de verificación para su oferta

**1**

**2**

| Inventario de nodos 1 | Totales sumados 2 |
| --- | --- |
| ¿Hay una tabla con nombre, función, sistema operativo, vCPU, RAM y<br>disco de cada máquina?<br>3 | ¿Están sumados los vCPU, la memoria y el disco, y esa suma se conecta<br>con el hardware cotizado?<br>4 |

| Cantidad justificada 3 | Distribución justificada 4 |
| --- | --- |
| ¿Se explica por qué tres masters, cuántos workers y por qué esa<br>cantidad?<br>5 | ¿Se dice qué máquina virtual va en qué servidor físico, y por qué esa<br>repartición?<br>6 |

| Hipervisor decidido 5 | Nivel RAID por volumen 6 |
| --- | --- |
| ¿Se declara cuál se usará, con qué licenciamiento, y se reservó su<br>consumo de recursos? | ¿Se indica RAID 1 para el arranque y el nivel elegido para los datos, con<br>su razón? |

### Lista de verificación para su oferta · continuación 1

**7**

**8**

| Factor de compra aplicado 7 | Disco de reserva 8 |
| --- | --- |
| ¿La capacidad bruta cotizada corresponde a la útil requerida<br>multiplicada por el factor del nivel RAID?<br>9 | ¿Está considerado el spare y su costo, o se asume que alguien irá a<br>cambiar el disco a tiempo?<br>10 |

| Prueba de falla 9 | RAID y respaldo separados 10 |
| --- | --- |
| ¿Hay una tabla de «qué pasa si cae un servidor», con los puntos únicos<br>de falla declarados? | ¿Queda claro que el RAID no es el respaldo, y hay una política de<br>respaldo aparte? |

### Recomendaciones para profundizar

*Sección 3 · Arquitectura física y dimensionamiento*

1. **Modelo OSI aplicado** — Repase las siete capas y ubique en cada una los equipos y servicios que aparecerán en su arquitectura física. Complete la cadena usuarios → concurrencia → transacciones por segundo → nodos para su caso, y súmela en un inventario de máquinas.
2. **Dimensionamiento** — Lea cómo funciona el algoritmo Raft y verifique por qué el número de nodos de control siempre es impar.
3. **Quórum y consenso** — Instale Proxmox VE o VirtualBox y cree tres máquinas virtuales. Observe cuánta memoria consume el hipervisor por sí solo. Levante un Docker Swarm de tres nodos, apague uno y compruebe qué pasa con el quórum y con los contenedores. Calcule, para la capacidad útil de su caso, cuántos discos y de qué tamaño hay que comprar en RAID 1, RAID 5, RAID 6 y RAID 10.

---

## Sección 4 · La nube

- Las cinco características esenciales del cloud computing
- IaaS, PaaS y SaaS: quién administra qué, y todos los demás *aaS
- Modelos de despliegue, regiones, zonas de disponibilidad y redes virtuales
- Una aplicación de tres capas desplegada en la nube, componente por componente
- Serverless, orquestación de contenedores y la comparación honesta con on-premise
- Catálogo de servicios AWS y Azure, y arquitecturas físicas de referencia
- Máquina virtual, contenedores, Fargate y funciones: diferencias, costos y cuándo usar cada uno

### Aplicaciones en la nube

El desarrollo de aplicaciones nativas de la nube es un enfoque que permite compilar, ejecutar y mejorar aplicaciones en función de técnicas y tecnologías reconocidas para el Cloud Computing. Estas arquitecturas están diseñadas para ofrecer escalabilidad, resiliencia y agilidad operativa.

**Cinco características esenciales de un servicio de cloud computing:**

**1**

**2**

**3**

**4**

**5**

| Autoservicio bajo demanda 1 | Amplio acceso a la red 2 | Recursos compartidos 3 | Elasticidad 4 | Servicio medido 5 |
| --- | --- | --- | --- | --- |
| El cliente contrata sólo<br>los servicios que<br>requiere y cuando los<br>necesita, sin mayor<br>interacción con el<br>prestador. | Los servicios quedan<br>disponibles<br>ampliamente, acorde a<br>las reglas de acceso que<br>se definan. | Los recursos del<br>prestador se agrupan<br>para servir a múltiples<br>clientes, asignándose<br>de forma dinámica. | Las capacidades se<br>asignan y se retiran de<br>forma elástica, a<br>menudo automática,<br>respondiendo a la<br>demanda. | Se mide el consumo en<br>un punto apropiado del<br>servicio, permitiendo al<br>cliente consumir sólo lo<br>que necesita. |

### IaaS · PaaS · SaaS · ¿quién administra qué?

| On-premise | IaaS | PaaS | SaaS |
| --- | --- | --- | --- |
| usted Aplicaciones<br>usted Datos<br>usted Tiempo de ejecución<br>usted Middleware<br>usted Sistema operativo<br>usted Virtualización<br>usted Servidores<br>usted Almacenamiento<br>usted Red<br>usted lo administra<br>Cada columna hacia la derecha reduce trabajo de operación | usted<br>usted<br>usted<br>usted<br>usted<br>proveedor<br>proveedor<br>proveedor<br>proveedor<br>proveedor su equipo<br>y aumenta la dependencia del proveedor. | usted<br>usted<br>proveedor<br>proveedor<br>proveedor<br>proveedor<br>proveedor<br>proveedor<br>proveedor<br>proveedor lo administra el proveedor | proveedor<br>proveedor<br>proveedor<br>proveedor<br>proveedor<br>proveedor<br>proveedor<br>proveedor<br>proveedor<br>de nube |

### Las tres familias, en detalle

| IaaS · Infraestructura como servicio | PaaS · Plataforma como servicio | SaaS · Software como servicio |
| --- | --- | --- |
| Pone a disposición del cliente el uso de la<br>infraestructura informática — capacidad de<br>cómputo, espacio de disco y bases de datos,<br>entre otros — como un servicio.<br>En vez de adquirir servidores, espacio de<br>data center o equipos de red, el cliente<br>externaliza buscando ahorro en la inversión<br>en sistemas TI. La factura se calcula según<br>los recursos consumidos: pago por uso.<br>Ejemplo típico: máquinas virtuales, discos,<br>redes virtuales. | Es básicamente un ambiente de desarrollo<br>donde se pueden crear otras aplicaciones<br>que hagan uso de las características del<br>Cloud Computing.<br>El modelo permite a los usuarios crear<br>aplicaciones de software utilizando<br>herramientas suministradas por el<br>proveedor, sin administrar el sistema<br>operativo ni el servidor de aplicaciones.<br>Ejemplo típico: plataformas de despliegue<br>de aplicaciones, bases de datos gestionadas. | Consiste en la entrega de aplicaciones como<br>servicio: el proveedor ofrece licencias de su<br>aplicación a los clientes para su uso bajo<br>demanda.<br>El proveedor puede tener la aplicación<br>instalada en sus propios servidores web,<br>permitiendo el acceso mediante navegador,<br>o entregarla para su instalación,<br>desactivándose al terminar el contrato.<br>Ejemplo típico: correo, gestión documental,<br>CRM, ERP en línea. |

### Otros servicios en la nube

| FaaS | DBaaS | IDaaS | SECaaS |
| --- | --- | --- | --- |
| Function as a Service: permite<br>ejecutar pequeñas tareas sin<br>necesidad de preocuparse por<br>la infraestructura informática. | Database as a Service: modelo<br>que permite gestionar bases<br>de datos en la nube de forma<br>escalable. | Identity as a Service:<br>soluciones de autenticación y<br>gestión de identidades para<br>aplicaciones en la nube. | Security as a Service:<br>soluciones de seguridad para<br>prevenir amenazas, detectar<br>intrusiones y recuperar<br>sistemas vulnerados. |

| iPaaS | MBaaS | CaaS | DaaS |
| --- | --- | --- | --- |
| Integration Platform as a<br>Service: permite integrar<br>aplicaciones y simplificar el<br>flujo de información entre<br>datos de distintas fuentes. | Mobile as a Service:<br>soluciones de infraestructura<br>TI orientadas específicamente<br>a aplicaciones móviles. | Container as a Service:<br>ejecución y orquestación de<br>contenedores sin administrar<br>los nodos que los soportan. | Desktop as a Service:<br>escritorios virtuales<br>entregados como servicio,<br>útiles cuando el mandante<br>tiene teletrabajo o terceros. |

### Cuándo conviene contratar cada servicio

Cada sigla resuelve un problema concreto. La pregunta correcta no es «¿qué es?», sino «¿en qué situación de mi caso me sirve?».

| Servicio | Situación concreta en la que conviene contratarlo | Qué se evita construir |
| --- | --- | --- |
| IaaS | El mandante exige un software heredado que se instala en el servidor, o usted necesita control total del sistema operativo. | Comprar, instalar y renovar hardware |
| PaaS | Hay que publicar un portal web y el equipo no tiene a nadie que administre servidores. | Administrar el servidor de aplicaciones |
| SaaS | El caso pide correo, firma de documentos o gestión documental: nada de eso hay que construirlo. | Desarrollar y operar esa funcionalidad |
| FaaS | Cada vez que llega un archivo hay que procesarlo. Ocurre pocas veces al día y no justifica un servidor encendido. | Un servidor esperando el archivo |
| DBaaS | Se necesita una base de datos con respaldo, réplica y parches al día, y no hay un administrador de bases de datos en el equipo. | Instalar y operar el motor |
| IDaaS | Los usuarios deben entrar con una identidad ya existente, o se exige doble factor sin construirlo. | El módulo de autenticación completo |
| SECaaS | Se necesita protección contra ataques y monitoreo de seguridad sin montar un equipo dedicado. | Un centro de operaciones de seguridad |

### Cuándo conviene contratar cada servicio · continuación 1

| Servicio | Situación concreta en la que conviene contratarlo | Qué se evita construir |
| --- | --- | --- |
| iPaaS | Hay que integrar cinco sistemas del mandante con formatos distintos y poco tiempo de desarrollo. | Escribir cada integración a mano |
| CaaS | Se quiere desplegar contenedores sin administrar los servidores que los ejecutan. | Instalar y operar el clúster |
| DaaS | Personal externo o en teletrabajo debe acceder a aplicaciones internas desde equipos que no controla la organización. | Entregar y administrar equipos |

### Cómo se decide entre construir y contratar

Contratar un servicio no siempre es más barato, pero casi siempre es más rápido. La decisión se toma con cuatro criterios.

| ¿Es parte del valor del negocio? | ¿Tiene el equipo la capacidad? | ¿Cuánto cuesta a cinco años? | ¿Qué dependencia genera? |
| --- | --- | --- | --- |
| Si la funcionalidad es lo que<br>distingue su propuesta,<br>constrúyala. Si es un servicio<br>de apoyo — correo, firma,<br>mapas — contrátela. | Operar un motor de base de<br>datos, un clúster o un<br>sistema de identidad exige<br>perfiles que quizás no están<br>en el proyecto. | Compare el gasto mensual<br>del servicio contra las horas<br>de construcción, más las de<br>operación durante todo el<br>horizonte. | Contratar traslada el riesgo<br>operativo, pero crea<br>dependencia de un tercero:<br>hay que declararla y tener<br>plan alternativo. |

> En la oferta, cada servicio contratado se declara con su función, su costo mensual y su acuerdo de nivel de servicio. Un servicio de tercero sin SLA declarado es un riesgo sin evaluar.

### Modelos de despliegue

| Nube pública | Nube privada | Nube híbrida | Multinube |
| --- | --- | --- | --- |
| Infraestructura de un<br>proveedor, compartida entre<br>muchos clientes.<br>+ Sin inversión inicial,<br>elasticidad inmediata,<br>catálogo enorme.<br>− Menor control, costo<br>variable, dependencia del<br>proveedor. | Infraestructura dedicada a una<br>sola organización, propia o<br>alojada.<br>+ Control total, cumplimiento<br>más simple de acreditar.<br>− Inversión alta, elasticidad<br>limitada, requiere equipo<br>propio. | Combina ambas: lo sensible o<br>estable queda dentro, lo<br>elástico va afuera.<br>+ Flexibilidad y<br>aprovechamiento de la<br>inversión existente.<br>− Complejidad de red,<br>identidades y operación<br>duplicada. | Más de un proveedor público,<br>por resiliencia o por evitar<br>dependencia.<br>+ Reduce el riesgo de<br>proveedor único.<br>− Duplica el aprendizaje, los<br>contratos y las herramientas. |

> En el informe declare el modelo elegido y las razones. «Nube híbrida: la base de datos con información personal permanece en el data center del mandante; el portal público se despliega en nube pública con autoescalado» es una decisión defendible.

### La geografía de la nube

| Región | Zona de disponibilidad | Punto de presencia / borde |
| --- | --- | --- |
| Ubicación geográfica donde el proveedor<br>agrupa sus centros de datos.<br>Determina la latencia de acceso y el<br>cumplimiento de las regulaciones de<br>residencia de datos.<br>Decisión de la oferta: en qué país quedan<br>los datos. | Centros de datos físicamente separados<br>dentro de una misma región, con energía y<br>red independientes.<br>Proporcionan alta disponibilidad y<br>tolerancia a fallos al permitir replicar<br>recursos en ubicaciones aisladas.<br>Decisión de la oferta: en cuántas zonas se<br>despliega. | Nodos distribuidos cerca del usuario final,<br>usados por las redes de distribución de<br>contenido.<br>Reducen la latencia percibida entregando<br>contenido estático desde el punto más<br>cercano.<br>Decisión de la oferta: si se usa CDN y para<br>qué contenido. |

> Una aplicación desplegada en una sola zona de disponibilidad no tiene alta disponibilidad, aunque esté en la nube. La redundancia hay que diseñarla y hay que pagarla: no viene incluida por el hecho de contratar un proveedor.

### La red virtual

Los mismos principios de segmentación de la arquitectura on-premise se aplican en la nube, con otros nombres.

| Elemento en la nube | Función | Equivalente on-premise |
| --- | --- | --- |
| Red virtual privada (VPC) | Red virtual aislada donde se despliegan los recursos. Da control sobre direcciones IP, subredes y rutas. | La red interna de la organización |
| Subred pública | Aloja los recursos con acceso a Internet: pasarelas de salida y balanceadores. | La DMZ |
| Subred privada | Aloja los servidores de aplicación y las bases de datos. Sin acceso directo desde Internet. | Red interna y zona de datos |
| Pasarela NAT | Permite que los recursos en subred privada salgan a Internet para actualizarse, sin ser alcanzables desde fuera. | Proxy de salida |
| Grupo de seguridad | Reglas de tráfico permitido a nivel de instancia: puertos, protocolos y orígenes. | Firewall de host |
| Firewall de aplicación web | Protege contra vulnerabilidades comunes de la capa de aplicación, como inyección SQL y XSS. | WAF perimetral |

### Ejemplo · aplicación de tres capas en la nube

**Usuarios → DNS → Red de distribución de contenido (CDN) → Firewall de aplicación web (WAF)**

**REGIÓN**

**Balanceador de carga (distribuye entre zonas)**

| Zona de disponibilidad 1 | Zona de disponibilidad 2 |
| --- | --- |
| Subred web · instancias + autoescalado | Subred web · instancias + autoescalado |

| Subred aplicación · instancias + autoescalado Subred datos · base de datos gestionada Subred web · instancias + autoescalado | Subred aplicación · instancias + autoescalado Subred datos · base de datos gestionada Subred web · instancias + autoescalado |
| --- | --- |
| réplica + failover<br>Almacenamiento de objetos · Caché en memoria · Respaldo | gestionado · Monitoreo y alertas |

### Los componentes del ejemplo

| Componente | Función | Por qué está en la arquitectura |
| --- | --- | --- |
| Protección DDoS | Protege de ataques de denegación de servicio. | Primera defensa de la disponibilidad. |
| DNS gestionado | Dirige el tráfico a distintos destinos según el dominio solicitado. | Resolución de nombres y enrutamiento por dominio. |
| Firewall de aplicación web | Filtra tráfico malicioso antes de que llegue a los servidores. | Protege contra inyección SQL, XSS y el OWASP Top 10. |
| Red de distribución de contenido | Caché global de contenido estático cerca del usuario. | Baja latencia y menos carga en los servidores de origen. |
| Balanceador de carga | Distribuye el tráfico entrante entre múltiples instancias. | Disponibilidad, comprobaciones de estado y terminación TLS. |
| Grupo de autoescalado | Ajusta la cantidad de instancias según la demanda. | Rendimiento en el máximo y ahorro en las horas de baja demanda. |
| Base de datos gestionada | Motor relacional administrado, con réplica en otra zona. | Respaldo automático, parches y conmutación ante fallas. |
| Caché en memoria | Almacena en memoria los datos más consultados. | Baja la carga de la base y la latencia. |
| Almacenamiento de objetos | Archivos estáticos, documentos y respaldos. | Escala sin límite y bajo costo por GB. |
| Monitoreo y alertas | Métricas, registros y alarmas de los recursos. | Sin esto no se puede cumplir un SLA. |

### Arquitectura sin servidores · serverless

La informática serverless está totalmente gestionada: nunca se reservan explícitamente instancias de servidor. Cada ejecución de una función podría correr en una instancia de cómputo diferente, de forma transparente para el código.

| De qué nos podemos olvidar | Cómo funciona |
| --- | --- |
| Aprovisionar servidores.<br>Mantenerlos y gestionarlos.<br>Escalar la aplicación ante aumentos de demanda.<br>Preocuparnos de la disponibilidad y la tolerancia a fallos. | En lugar de programar una aplicación completa, se escribe<br>una función: código más metadatos (sus disparadores y<br>enlaces con otros sistemas).<br>La plataforma programa la ejecución y escala el número de<br>instancias según la tasa de eventos entrantes.<br>Encaja muy bien con cargas de trabajo que responden a<br>eventos entrantes. |

> Modelo de cobro: se paga únicamente cuando se está ejecutando el código. Si no hay ejecuciones activas, no se cobra. Si el código corre una vez al día durante 2 minutos, se factura 1 ejecución y 2 minutos de cómputo.

### Serverless · cuándo conviene y cuándo no

| Conviene cuando… | No conviene cuando… |
| --- | --- |
| La carga es intermitente o muy variable: se paga sólo el uso<br>real.<br>El proceso es corto y se dispara por un evento (un archivo<br>que llega, un mensaje en cola, una hora del día).<br>Se quiere partir sin costo fijo de infraestructura.<br>Son tareas de apoyo: notificaciones, transformación de<br>archivos, integraciones puntuales. | Hay carga alta y constante: a partir de cierto volumen sale<br>más caro que instancias reservadas.<br>El proceso es largo: las plataformas imponen un tiempo<br>máximo de ejecución.<br>La latencia de la primera invocación importa: el arranque<br>en frío puede agregar cientos de milisegundos.<br>Se necesita portabilidad: es el modelo con mayor<br>dependencia del proveedor. |

> Todos los grandes operadores ofrecen funciones sin servidor. Lo relevante para la oferta no es la marca, sino declarar qué componentes serán serverless y por qué.

### Administrar contenedores · por qué

Un contenedor resuelve el empaquetado de una aplicación. El problema aparece cuando hay muchos, en varios servidores, cambiando todo el tiempo.

| Lo que hay que resolver a mano | Lo que resuelve la orquestación |
| --- | --- |
| ¿En qué servidor levanto cada contenedor y con qué<br>recursos?<br>Si el contenedor muere de madrugada, ¿quién lo levanta?<br>Si el servidor completo se cae, ¿a dónde se mueve su<br>carga?<br>¿Cómo encuentra un servicio la dirección de otro si cambia<br>en cada arranque?<br>¿Cómo publico una versión nueva sin cortar el servicio?<br>¿Cómo agrego capacidad en el peak y la retiro después? | Programación automática según recursos disponibles.<br>Reinicio automático del contenedor y reubicación si cae<br>el nodo.<br>Nombres estables de servicio y balanceo interno.<br>Despliegue progresivo con reversión automática.<br>Escalado por métricas, hacia arriba y hacia abajo.<br>Configuración y secretos separados de la imagen. |

> En una palabra: la orquestación convierte un conjunto de servidores en una sola capacidad de cómputo donde uno declara «quiero tres réplicas de este servicio» y el sistema se encarga del resto.

### Orquestación de contenedores

Un contenedor aislado resuelve el empaquetado. Cuando hay decenas de contenedores en varios servidores, aparece el problema de coordinarlos: eso es la orquestación.

| Programación | Autorreparación | Escalado |
| --- | --- | --- |
| Decide en qué nodo se ejecuta cada<br>contenedor según los recursos disponibles. | Si un contenedor muere, lo levanta de<br>nuevo. Si un nodo cae, redistribuye la carga. | Aumenta o reduce las réplicas según<br>métricas de uso, de forma automática. |

| Descubrimiento | Despliegue progresivo | Configuración y secretos |
| --- | --- | --- |
| Cada servicio tiene un nombre estable; no<br>hay que conocer direcciones IP. | Publica una versión nueva de forma gradual<br>y revierte si algo falla. | Separa la configuración y las credenciales de<br>la imagen del contenedor. |

> Para la oferta: proponer orquestación exige declarar quién opera el clúster. Un servicio gestionado por el proveedor traslada esa carga; un clúster propio agrega perfiles y horas al presupuesto.

### Ciclo de vida y seguridad de las imágenes

Administrar contenedores no es sólo ejecutarlos: es gobernar el ciclo de vida de las imágenes que se ejecutan.

| Registro de imágenes | Versionado | Imagen base mínima |
| --- | --- | --- |
| Repositorio privado donde se publican las<br>imágenes construidas. Es el equivalente al<br>almacén de artefactos: sin él no hay<br>trazabilidad de qué está corriendo. | Cada imagen se etiqueta con una versión<br>inmutable. Nunca desplegar la etiqueta<br>«latest» en producción: no se sabe qué se<br>está ejecutando. | Mientras menos trae la imagen, menos<br>vulnerabilidades tiene y más rápido arranca.<br>Nada de herramientas de depuración en<br>producción. |

| Análisis de vulnerabilidades | Sin secretos adentro | Límites de recursos |
| --- | --- | --- |
| Escaneo automático de la imagen en cada<br>construcción y de forma periódica: una<br>imagen segura hoy no lo es en tres meses. | Contraseñas y llaves se inyectan en tiempo<br>de ejecución desde el almacén de secretos,<br>nunca se hornean en la imagen. | Cada contenedor declara CPU y memoria<br>máxima. Sin límites, un contenedor con fuga<br>de memoria arrastra a todo el nodo. |

> Para la oferta: comprometer «imágenes versionadas, escaneadas en cada construcción y con límites de recursos declarados» es concreto, verificable y cuesta muy poco ofrecerlo.

### ¿Necesita usted un orquestador?

Hay una escalera de opciones. Suba sólo hasta donde el caso lo justifique: cada peldaño agrega capacidad y agrega

| QUÉ ES | CUÁNDO SE JUSTIFICA |
| --- | --- |
| Aplicación desplegada directamente en el servidor<br>1 Sin contenedores<br>servicio gestionado. | o 1-2 componentes, despliegues poco frecuentes,<br>equipo pequeño. |

El proveedor ejecuta el contenedor: usted entrega la Hasta ~10 servicios. Cubre la mayoría de los

**2**

**Contenedores gestionados**

imagen y declara réplicas.

proyectos de este curso.

Clúster administrado por el proveedor; usted opera Muchos servicios, despliegues frecuentes, necesidad

**3**

**Orquestador gestionado**

sólo las cargas.

de control fino.

Clúster instalado y operado por su equipo, on-

Exigencia de datos en sitio o requisitos que ningún

**4**

**Orquestador propio**

premise o en máquinas virtuales.

servicio gestionado cubre.

> Proponer el peldaño 4 en un proyecto de cuatro meses con cinco personas es, casi siempre, un riesgo mal evaluado.

### On-premise vs. nube · comparación honesta

| Criterio | On-premise | Nube pública |
| --- | --- | --- |
| Inversión inicial | Alta: hardware, licencias, habilitación | Baja o nula |
| Costo mensual | Predecible y relativamente fijo | Variable: depende del consumo |
| Tiempo de puesta en marcha | Semanas o meses (compra, envío, instalación) | Minutos u horas |
| Elasticidad ante picos | Se dimensiona para el máximo y se desperdicia el resto del año | Se ajusta automáticamente |
| Control y personalización | Total | Limitado a lo que ofrece el proveedor |
| Residencia de los datos | Donde el mandante decida | Donde existan regiones disponibles |
| Equipo requerido | Operaciones, redes, respaldo, seguridad | Menos operación, más arquitectura y control de gasto |
| Dependencia del proveedor | Baja | Alta si se usan servicios propietarios |
| Renovación tecnológica | Reinversión cada 3 a 5 años | Incluida en el servicio |
| Continuidad ante desastre | Exige un segundo sitio, con su costo | Replicación entre zonas y regiones |

### CAPEX, OPEX y el costo total

La decisión no se juega en el precio de una máquina: se juega en la forma del flujo de caja a lo largo del horizonte

**de evaluación.**

| On-premise · perfil CAPEX | Nube · perfil OPEX |
| --- | --- |
| Desembolso grande en el año 0 y reinversión al final<br>de la vida útil.<br>Se deprecia: genera escudo tributario, hay que<br>reflejarlo en el flujo.<br>Costos anuales relativamente estables y predecibles.<br>Capacidad ociosa comprada por adelantado: se paga el<br>máximo todo el año.<br>Riesgo: quedar corto obliga a una compra no<br>presupuestada. | Sin desembolso inicial relevante: la inversión se<br>traslada a gasto mensual.<br>No se deprecia: es gasto del ejercicio, con otro efecto<br>tributario.<br>Costo variable con el uso: puede crecer más rápido<br>que los ingresos.<br>Se paga sólo la capacidad utilizada, si se configura bien<br>el autoescalado.<br>Riesgo: gasto que se dispara sin control y sin nadie que<br>lo mire. |

> Compare siempre el costo total sobre el mismo horizonte que usará en la evaluación económica — típicamente 5 años — e incluya reinversión, licencias, personal y crecimiento de la demanda en ambos escenarios.

### Los costos de la nube que se olvidan

| Salida de datos | Ambientes no productivos | Licencias sobre la nube | Soporte del proveedor |
| --- | --- | --- | --- |
| Subir datos suele ser gratis;<br>sacarlos, no. En soluciones<br>con mucho contenido o con<br>respaldo hacia afuera, este<br>ítem sorprende. | Desarrollo, pruebas y<br>capacitación también<br>consumen. Suelen sumar<br>entre 30% y 50% del ambiente<br>productivo si no se apagan. | El motor de base de datos o el<br>sistema operativo pueden<br>facturarse aparte del<br>cómputo. | El plan de soporte con<br>tiempos de respuesta<br>comprometidos es un<br>porcentaje del gasto mensual. |

| Sobredimensionamiento | Respaldo y retención | Observabilidad | Transferencia entre zonas |
| --- | --- | --- | --- |
| Instancias grandes «por si<br>acaso» y recursos que<br>quedaron encendidos sin uso.<br>El desperdicio típico es alto. | Guardar copias por años tiene<br>costo acumulativo: el<br>almacenamiento crece todos<br>los meses y nunca baja solo. | Registros y métricas se cobran<br>por volumen ingerido y por<br>tiempo de retención. Se<br>dispara con facilidad. | El tráfico entre zonas de<br>disponibilidad también se<br>factura: la alta disponibilidad<br>tiene costo de red. |

### Del concepto al nombre del servicio

En el diagrama lógico se nombra la función. En el diagrama físico y en la cotización aparece el producto. Estas

**cuatro láminas son el diccionario entre ambos.**

| Primero la función | Después el producto | Y siempre el porqué |
| --- | --- | --- |
| «Necesito distribuir el tráfico entre varias<br>instancias y sacar de rotación las que no<br>responden.» Eso es lo que va en la<br>arquitectura lógica. | «Application Load Balancer» en AWS,<br>«Application Gateway» en Azure. Eso es lo<br>que va en el diagrama físico y en la<br>cotización. | «Se elige capa 7 porque el enrutamiento<br>por ruta y el despliegue progresivo son<br>requisitos del caso.» Eso es lo que da<br>puntaje. |

Advertencia importante: los nombres comerciales cambian, se renombran y se descontinúan. En el informe, escriba siempre la función

> primero y el producto como ejemplo — «balanceador de carga de capa 7 (por ejemplo, AWS Application Load Balancer)» —. Así la propuesta sigue siendo válida aunque el proveedor cambie el nombre, y no queda amarrada a un solo fabricante.

### Catálogo 1 · red, entrega y perímetro

| Función | AWS | Azure | Equivalente on-premise |
| --- | --- | --- | --- |
| DNS y enrutamiento por dominio | Route 53 | Azure DNS + Traffic Manager | Servidor DNS propio (BIND, Windows DNS) |
| Red virtual aislada | VPC (Virtual Private Cloud) | Virtual Network (VNet) | La red interna y sus VLAN |
| Subred pública | Public subnet + Internet Gateway | Subnet con IP pública | La DMZ |
| Subred privada | Private subnet | Subnet privada | La red interna de aplicaciones y datos |
| Salida a Internet desde red privada | NAT Gateway | Azure NAT Gateway | Proxy de salida |
| Red de distribución de contenido | CloudFront | Azure Front Door | Caché inverso propio (Varnish, Nginx) |
| Balanceador de capa 7 (HTTP) | Application Load Balancer (ALB) | Application Gateway | Proxy inverso / balanceador de aplicación |
| Balanceador de capa 4 (TCP/UDP) | Network Load Balancer (NLB) | Azure Load Balancer | Balanceador de red (F5, HAProxy) |
| Firewall de aplicación web | AWS WAF | Azure Web Application Firewall | WAF perimetral en appliance |
| Protección contra denegación de servicio | AWS Shield | Azure DDoS Protection | Servicio de mitigación del proveedor de enlace |
| Reglas de tráfico por instancia | Security Groups | Network Security Groups (NSG) | Reglas de firewall de host |
| Firewall de red gestionado | AWS Network Firewall | Azure Firewall | Firewall perimetral (appliance) |

### Catálogo 2 · cómputo y contenedores

| Función | AWS | Azure | Comentario para la oferta |
| --- | --- | --- | --- |
| Máquina virtual | EC2 | Azure Virtual Machines | Control total; usted administra el sistema operativo y su ciclo de parches. |
| Grupo de escalado automático | Auto Scaling Group | Virtual Machine Scale Sets | Es lo que convierte un servidor en una capa elástica. |
| Orquestador de contenedores | EKS (Elastic Kubernetes Service) | AKS (Azure Kubernetes Service) | Estándar de facto; el plano de control lo opera el proveedor. |
| Orquestador propio del proveedor | ECS (Elastic Container Service) | — | Más simple que Kubernetes y suficiente para muchas soluciones. |
| Contenedores sin administrar servidores | AWS Fargate | Azure Container Apps | Se despliega el contenedor y no existe un nodo que mantener. |
| Contenedor suelto por tarea | ECS Task / Fargate task | Azure Container Instances (ACI) | Ideal para procesos puntuales o tareas programadas. |
| Aplicación web gestionada (PaaS) | AWS App Runner / Elastic Beanstalk | Azure App Service | El camino más corto para publicar una aplicación web. |
| Funciones sin servidor | AWS Lambda | Azure Functions | Se ejecuta por evento; se paga por invocación y por tiempo. |
|   |   |   |   |
| Registro de imágenes | ECR (Elastic Container Registry) | Azure Container Registry | Imprescindible si usa contenedores: es donde vive el artefacto. |
| Procesamiento por lotes | AWS Batch | Azure Batch | Para cargas masivas programadas, no para atención en línea. |

### Catálogo 3 · datos, almacenamiento y observabilidad

| Función | AWS | Azure | Equivalente on-premise |
| --- | --- | --- | --- |
| Base de datos relacional gestionada | RDS (PostgreSQL, MySQL, SQL Server) | Azure Database for PostgreSQL / SQL Database | Motor instalado en un servidor propio |
| Base de datos documental / NoSQL | DynamoDB / DocumentDB | Cosmos DB | MongoDB autogestionado |
| Caché en memoria | ElastiCache (Redis) | Azure Cache for Redis | Redis o Memcached instalado |
| Almacenamiento de objetos | S3 (bucket) | Azure Blob Storage (contenedor) | Servidor de archivos o almacenamiento de objetos propio |
| Almacenamiento de bloque | EBS (Elastic Block Store) | Azure Managed Disks | Discos de la SAN |
| Sistema de archivos compartido | EFS (Elastic File System) | Azure Files | NAS con NFS o SMB |
| Respaldo gestionado | AWS Backup | Azure Backup | Software de respaldo y librería de cintas |
| Métricas, registros y alarmas | CloudWatch | Azure Monitor + Log Analytics | Zabbix, Nagios, ELK autogestionado |
| Trazas distribuidas | AWS X-Ray | Application Insights | Instrumentación propia |
| Mensajería / colas | SQS y SNS | Azure Service Bus / Event Grid | RabbitMQ o ActiveMQ instalado |
| Flujo de eventos | Kinesis / MSK | Azure Event Hubs | Kafka autogestionado |

### Catálogo 4 · conectividad híbrida, identidad y secretos

| Función | AWS | Azure | Alternativa abierta o propia |
| --- | --- | --- | --- |
| Túnel permanente entre sitios | Site-to-Site VPN | VPN Gateway (site-to-site) | IPsec en appliance propio, o WireGuard entre extremos |
| Enlace dedicado con el data center | Direct Connect | ExpressRoute | Enlace punto a punto contratado al proveedor de red |
| Acceso remoto de personas | AWS Client VPN | VPN Gateway (point-to-site) | WireGuard, OpenVPN, o acceso Zero Trust de un tercero |
| Acceso administrativo sin exponer puertos | Systems Manager Session Manager | Azure Bastion | Servidor bastión propio con doble factor |
| Conexión privada a servicios gestionados | PrivateLink / VPC Endpoints | Azure Private Link | No aplica: es propio de la nube |
| Interconexión de redes virtuales | VPC Peering / Transit Gateway | VNet Peering / Virtual WAN | Enrutamiento entre VLAN |
| Identidad y permisos de la plataforma | IAM | Microsoft Entra ID + RBAC | Directorio corporativo (LDAP, Active Directory) |
| Identidad de los usuarios de la aplicación | Cognito | Microsoft Entra External ID | Proveedor de identidad propio o de un tercero |
| Almacén de secretos | Secrets Manager / Parameter Store | Azure Key Vault | HashiCorp Vault autogestionado |
| Certificados TLS | AWS Certificate Manager | Azure Key Vault (certificados) | Let's Encrypt con renovación automatizada |

> WireGuard es un protocolo de VPN de código abierto, muy liviano y rápido, integrado al núcleo de Linux. Es una opción legítima y de bajo costo para unir el data center con la nube cuando no se justifica un enlace dedicado.

### Antes de comparar · las cinco palabras

Cinco términos que se usan como sinónimos y no lo son. Fijarlos ahora evita la confusión en todo lo que sigue.

| Término | Qué es exactamente | Ejemplo |
| --- | --- | --- |
| Máquina virtual | Un computador simulado por software, con su propio sistema operativo completo. Usted lo enciende, lo configura, lo actualiza y lo apaga. Es un servidor, sólo que no es de metal. | EC2 · Azure Virtual Machines |
| Contenedor | Un paquete con la aplicación y sus dependencias, que se ejecuta aislado sobre un sistema operativo compartido. No trae sistema operativo propio: por eso pesa e inicia mucho menos que una máquina virtual. | Una imagen de contenedor |
| Contenedores gestionados | Un orquestador operado por el proveedor que coordina muchos contenedores. Ojo: los servidores donde corren esos contenedores — los nodos — siguen siendo suyos y hay que dimensionarlos y parcharlos. | EKS · AKS |
| Contenedores sin servidor | El mismo contenedor, pero sin nodos: usted declara cuánta CPU y memoria necesita cada tarea y el proveedor se encarga de dónde se ejecuta. No hay servidor que administrar. | AWS Fargate · Azure Container Apps |
| Serverless | No es un producto: es un modelo de consumo. Significa que no se aprovisiona ni se administra ningún servidor, que la plataforma escala sola y que se paga sólo por lo que se usa. | Un modelo, no un servicio |

### ¿«Funciones» es lo mismo que «serverless»?

No. Serverless es el paraguas — un modelo de consumo —; las funciones son sólo una de las formas que toma ese

**modelo, y no la única.**

**SERVERLESS · modelo de consumo: sin aprovisionar servidores, escalado automático, pago por uso real**

| Funciones (FaaS) SERVERLESS · modelo de consumo: sin aprovisionar servidores, escalado automático, pago por uso real | Contenedores sin servidor | Bases de datos sin servidor | Otros servicios gestionados |
| --- | --- | --- | --- |
| Código que se ejecuta por evento<br>y termina.<br>Lambda · Azure Functions | Su contenedor, sin nodos que<br>administrar.<br>Fargate · Container Apps | El motor escala solo y se cobra<br>por uso.<br>Aurora Serverless · Cosmos DB | Colas, almacenamiento de<br>objetos, notificaciones.<br>SQS · S3 · Event Grid |

Entonces: toda función es serverless, pero no todo lo serverless son funciones. Fargate también es serverless — no hay servidor que administrar —

y sin embargo ejecuta contenedores, no funciones.

> Y la contraparte: los contenedores gestionados (EKS, AKS) NO son serverless, porque los nodos siguen siendo responsabilidad suya, aunque el plano de control lo opere el proveedor.

### Cuatro modelos de cómputo · quién administra qué

**Máquina virtual**

**Contenedores gestionados Contenedores sin servidor**

**Funciones**

| (EC2 · Azure VM) Máquina virtual | (EKS · AKS) | (Fargate · Container Apps) (Lambda · Azure Functions) |
| --- | --- | --- |
| usted Código de la aplicación<br>Imagen o paquete de<br>usted<br>despliegue<br>usted Escalado<br>Runtime y servidor de<br>usted<br>aplicación<br>usted Sistema operativo y parches<br>usted Nodos y clúster<br>Hardware, red y<br>proveedor<br>virtualización<br>usted compartido | usted<br>usted<br>compartido<br>usted<br>usted<br>compartido<br>proveedor | usted usted<br>usted compartido<br>proveedor proveedor<br>usted proveedor<br>proveedor proveedor<br>proveedor proveedor<br>proveedor proveedor<br>proveedor |

> Hacia la derecha desaparece trabajo de operación — y con él, horas del presupuesto —; a cambio aumenta la dependencia de la plataforma y bajan las opciones de configuración fina.

### Los cuatro modelos, comparados

|   | Máquina virtual | Contenedores gestionados | Contenedores sin servidor | Funciones serverless |
| --- | --- | --- | --- | --- |
| Qué entrega usted | Un servidor que administra | Imágenes + un clúster con nodos | Sólo la imagen y su tamaño | Sólo el código de la función |
| Quién parchea el SO | Usted | Usted (los nodos) | El proveedor | El proveedor |
| Tiempo de arranque | Minutos | Segundos con nodo libre | Decenas de segundos | Milisegundos |
| Granularidad de escalado | Por instancia completa | Por réplica | Por tarea | Por invocación |
| Límite de duración | Ninguno | Ninguno | Ninguno | 15 min en Lambda |
| Procesos de larga duración | Sí | Sí | Sí | No |
| Costo con carga constante | El más bajo (con reserva) | Bajo si el clúster está bien lleno | Medio-alto | Alto a partir de cierto volumen |
| Costo con carga intermitente | Alto: se paga apagado o encendido | Alto: el nodo sigue encendido | Bajo | El más bajo; cero si no hay uso |
| Complejidad de operación | Alta | La más alta | Media | Baja |
| Dependencia del proveedor | Baja | Baja: Kubernetes es portable | Media | Alta |

### Máquina virtual vs. hosting de contenedores

| MÁQUINA VIRTUAL · EC2 / Azure VM | CONTENEDORES GESTIONADOS · EKS / AKS |
| --- | --- |
| + Control total: sistema operativo, versiones, agentes,<br>configuración de red.<br>+ Es lo único viable para software heredado o que exige<br>instalación en el servidor.<br>+ Con instancias reservadas es el costo por hora más bajo<br>del mercado.<br>+ Modelo mental conocido: se parece a un servidor físico.<br>− Usted parchea, actualiza y endurece el sistema operativo:<br>son horas de operación todos los meses.<br>− Escala por instancia completa: se paga capacidad ociosa.<br>− Arranque en minutos: no responde bien a picos súbitos.<br>− « Servidores mascota»: cada uno termina con su propia<br>configuración irrepetible. | + Portabilidad real: la misma imagen corre en cualquier<br>nube y on-premise.<br>+ Densidad: varios servicios comparten un nodo, se<br>aprovecha mejor el hardware.<br>+ Autorreparación, despliegue progresivo y escalado por<br>réplica, incorporados.<br>+ El plano de control lo opera el proveedor.<br>− Los nodos siguen siendo suyos: hay que dimensionarlos,<br>parcharlos y actualizarlos.<br>− Curva de aprendizaje alta; exige un equipo que sepa<br>operarlo.<br>− Costo fijo del clúster aunque esté poco usado.<br>− Es la opción con mayor complejidad operativa de las<br>cuatro. |

> Regla: el orquestador se justifica por la cantidad de servicios y la frecuencia de despliegue, no por la cantidad de usuarios.

### Fargate vs. funciones serverless

| CONTENEDORES SIN SERVIDOR · Fargate / Container Apps | FUNCIONES · Lambda / Azure Functions |
| --- | --- |
| + Desaparecen los nodos: no hay servidor que dimensionar,<br>parchear ni escalar.<br>+ Se sigue desplegando una imagen de contenedor: no hay<br>que reescribir la aplicación.<br>+ Sin límite de tiempo de ejecución: sirve para procesos<br>largos y para servicios permanentes.<br>+ Aislamiento por tarea: cada tarea tiene su propio<br>entorno.<br>− Costo por vCPU y por GB de memoria mientras la tarea<br>está viva: con carga constante sale más caro que una<br>instancia reservada.<br>− El arranque de una tarea toma decenas de segundos: no<br>absorbe un pico instantáneo.<br>− Menos control fino sobre el nodo (versión del núcleo,<br>agentes, discos locales). | + Se paga sólo por invocación y por tiempo de ejecución: si<br>no hay uso, no hay costo.<br>+ Escala de cero a miles de ejecuciones sin configurar nada.<br>+ Cero operación: no hay servidor, ni nodo, ni contenedor<br>que mantener.<br>+ Ideal para tareas por evento: un archivo que llega, un<br>mensaje en cola, una hora programada.<br>− Límite de duración por invocación (15 minutos en<br>Lambda) y de memoria.<br>− Arranque en frío: la primera invocación agrega latencia.<br>− Obliga a diseñar por eventos y sin estado: no todo<br>software se puede llevar ahí.<br>− Es el modelo con mayor dependencia del proveedor. |

> Fargate es el punto medio: elimina la administración de servidores sin obligar a rediseñar la aplicación por eventos.

### Cómo se cobra cada modelo

La unidad de cobro es lo que determina si el costo de su solución es fijo, semifijo o proporcional al uso.

| Modelo | Unidad de cobro | Mínimo facturable | Se paga cuando está ocioso | Forma del costo |
| --- | --- | --- | --- | --- |
| Máquina virtual | Por hora de instancia encendida (o descuento por reserva de 1 a 3 años) | Por segundo, con mínimo de 1 minuto | Sí, mientras esté encendida | Prácticamente fijo |
| Contenedores gestionados | Por hora de los nodos + tarifa fija del plano de control del clúster | La del nodo subyacente | Sí: los nodos siguen encendidos | Fijo por nodo |
| Contenedores sin servidor | Por vCPU-hora y por GB-hora mientras la tarea está en ejecución | Por segundo, con mínimo de 1 minuto por tarea | No, si la tarea se detiene | Según tiempo activo |
| Funciones | Por invocación + por GB-segundo de ejecución | Del orden del milisegundo | No: sin uso, costo cero | Según el uso real |

> Consecuencia para la evaluación económica: con carga estable, la máquina virtual reservada suele ganar; con carga intermitente o estacional, las funciones ganan por lejos; y en el medio, los contenedores sin servidor. Modele los tres escenarios antes de decidir.

### Cómo elegir el modelo de cómputo

**Cinco preguntas, en este orden. La primera que responda «sí» determina el modelo.**

No hay alternativa: necesita

1 ¿El software exige instalarse en el servidor, o es un sistema heredado?

**Máquina virtual**

el sistema operativo completo.

| 2 | Funciones serverless Máquina virtual |
| --- | --- |
| ¿Tiene muchos servicios, varios equipos y despliegues frecuentes, con<br>3<br>gente que sepa operar un clúster?<br>¿Quiere contenedores sin administrar servidores, con procesos que<br>4<br>corren de forma continua? | La complejidad se paga con<br>Contenedores gestionados<br>capacidad de operación.<br>El punto medio: sin nodos,<br>Contenedores sin servidor<br>límite de duración. |

Ninguna de las anteriores: es una aplicación web común, de tamaño

Aplicación web gestionada (PaaS) Es el caso más frecuente en

**5**

**o contenedores sin servidor esta asignatura.**

moderado.

### Arquitectura de referencia · primero los conceptos

Antes de poner nombres de productos, hay que saber qué elementos se necesitan y para qué.

| Caché en el borde | Filtrado de aplicación |
| --- | --- |
| Región · red virtual privada<br>Distribuidor de carga entre zonas, con cifrado y control de salud | Monitoreo y alertas |

**Registro de imágenes**

**Zona de disponibilidad 1**

**Zona de disponibilidad 2**

| Subred pública · salida a Internet Subred privada · cómputo Subred privada · datos | Subred pública · salida a Internet Subred privada · cómputo Subred privada · datos |
| --- | --- |
| ⟷ Túnel cifrado o enlace dedicado | data center del mandante |

### Qué hace cada elemento y por qué está

| Elemento conceptual | Para qué está | Qué pasa si no está |
| --- | --- | --- |
| Resolución de dominio | Traduce el nombre del sitio a una dirección y puede desviar el tráfico a otro sitio si el principal falla. | No hay forma de conmutar rápido ante una caída |
| Caché en el borde | Entrega el contenido estático desde el punto más cercano al usuario. | Toda la carga llega al origen y la latencia sube |
| Filtrado de aplicación | Bloquea ataques conocidos antes de que lleguen al sistema. | El portal queda expuesto a ataques automatizados |
| Red virtual privada | Aísla los recursos y permite separarlos en subredes con reglas distintas. | Todo queda en la misma red: no hay segmentación |
| Subred pública | Aloja lo que necesita hablar con Internet: salida a la red y punto de entrada. | Los servidores quedarían expuestos directamente |
| Subred privada de cómputo | Aloja la aplicación, sin dirección pública. | La aplicación sería alcanzable desde Internet |
| Subred privada de datos | Aloja la base de datos, que sólo acepta a la capa de aplicación. | La base de datos quedaría expuesta |
| Distribuidor de carga | Reparte el tráfico entre zonas y saca de rotación lo que no responde. | Una instancia caída seguiría recibiendo usuarios |

### Qué hace cada elemento y por qué está · continuación 1

| Elemento conceptual | Para qué está | Qué pasa si no está |
| --- | --- | --- |
| Dos zonas de disponibilidad | Permite que la caída de un centro de datos no detenga el servicio. | El compromiso de disponibilidad no se sostiene |
| Almacén de objetos | Guarda documentos, imágenes y respaldos a bajo costo. | Todo terminaría dentro de la base de datos |
| Monitoreo y alertas | Avisa cuando algo se degrada, antes de que reclame el usuario. | No se puede cumplir ningún acuerdo de servicio |
| Almacén de secretos | Guarda credenciales y llaves fuera del código. | Las contraseñas terminan en el repositorio |

### Arquitectura física de referencia · AWS

**Usuarios**

**Route 53**

**CloudFront**

**AWS WAF**

**Internet**

**DNS**

**CDN**

**+ Shield**

**S3 Bucket**

**Región AWS · VPC 10.0.0.0/16**

**estáticos, documentos y**

**respaldos**

**Application Load Balancer · capa 7, multi-AZ, terminación TLS**

**CloudWatch**

**métricas, logs y alarmas**

**Zona de disponibilidad A**

**Zona de disponibilidad B**

| Public subnet · NAT Gateway Private subnet · aplicación ECS Fargate / EKS | Public subnet · NAT Gateway Private subnet · aplicación ECS Fargate / EKS |
| --- | --- |
|   | Secrets Manager |

| Private subnet · datos RDS + ElastiCache | Private subnet · datos RDS + ElastiCache |
| --- | --- |
| RDS Multi-AZ: réplica en espera en la segunda zona,<br>⟷ Site-to-Site VPN o Direct Connect Data | IAM<br>identidad y permisos<br>zona, con failover automático<br>center del mandante |

### La misma arquitectura, traducida a Azure

Cuando se comparan proveedores, la traducción prueba que la comparación es equivalente.

| Componente de la arquitectura | AWS | Azure |
| --- | --- | --- |
| Resolución de dominio y enrutamiento | Route 53 | Azure DNS + Traffic Manager |
| Entrega de contenido en el borde | CloudFront | Azure Front Door |
| Protección de aplicación y DDoS | AWS WAF + AWS Shield | Azure WAF + Azure DDoS Protection |
| Red virtual privada | VPC + public / private subnets | Virtual Network + subnets |
| Salida a Internet desde subred privada | NAT Gateway | Azure NAT Gateway |
| Balanceo de capa 7 | Application Load Balancer | Application Gateway |
| Cómputo de la aplicación | ECS Fargate o EKS | Azure Container Apps o AKS |
| Base de datos relacional con réplica | RDS Multi-AZ | Azure Database, zona redundante |
| Caché en memoria | ElastiCache for Redis | Azure Cache for Redis |
| Almacenamiento de objetos | S3 Bucket | Azure Blob Storage |
| Observabilidad | CloudWatch + X-Ray | Azure Monitor + App Insights |
| Secretos y certificados | Secrets Manager + ACM | Azure Key Vault |
| Enlace con el data center | Site-to-Site VPN / Direct Connect | VPN Gateway / ExpressRoute |

### Arquitectura híbrida · unir la nube con el data center

**DATA CENTER DEL MANDANTE**

**NUBE · VPC / VNet**

**Site-to-Site VPN (IPsec)**

**Firewall perimetral**

**VPN Gateway**

**Enlace dedicado**

**Sistemas heredados / ERP**

**Aplicación (subred privada)**

**Direct Connect / ExpressRoute**

**WireGuard**

**Base de datos primaria**

**Réplica de lectura / respaldo**

**(túnel liviano, código abierto)**

| Opción | Cómo funciona | Banda y latencia | Costo | Cuándo elegirla |
| --- | --- | --- | --- | --- |
| Site-to-Site VPN | Túnel IPsec cifrado sobre Internet, entre el firewall del mandante y la pasarela de la nube. | Depende del enlace a Internet; latencia variable. | Bajo | La opción por defecto: rápida de habilitar y suficiente para la mayoría. |
| Enlace dedicado | Circuito privado contratado que no pasa por Internet. | Garantizado y con latencia estable. | Alto y con plazo de instalación | Replicación continua de datos, volúmenes grandes o exigencia contractual. |
| WireGuard | Túnel de código abierto, muy liviano, montado sobre servidores propios en ambos extremos. | Buen rendimiento; depende del enlace y del equipo. | Muy bajo | Presupuesto acotado, o acceso remoto de personas al ambiente de la nube. |

### Cómo declarar todo esto en la oferta

No basta con listar servicios. Cada línea debe decir qué función cumple, qué producto la implementa y por qué se eligió.

| Función en la arquitectura | Servicio propuesto | Justificación | Costo estimado |
| --- | --- | --- | --- |
| Entrega de contenido estático y caché en el borde | CloudFront (AWS) | El portal atiende a todo el país; reduce latencia y descarga los servidores. | Por GB transferido y por solicitud |
| Protección de la aplicación web | AWS WAF con reglas OWASP | Requisito RQ-14 de seguridad; el portal está expuesto a Internet. | Fija + por millón de solicitudes |
| Cómputo de la aplicación | ECS Fargate, 2 a 6 tareas | Sin administración de servidores; la carga variable no justifica un clúster. | Por vCPU-hora y GB-hora |
| Base de datos transaccional | RDS PostgreSQL Multi-AZ | Motor libre, réplica en segunda zona para cumplir el 99,9% comprometido. | Por hora de instancia + disco |
| Documentos y respaldos | S3 con política de retención | Muchos documentos escaneados; el GB cuesta mucho menos que en la base. | Por GB almacenado y por solicitud |
| Observabilidad | CloudWatch con alarmas | Sin detección temprana no es posible cumplir el SLA ofrecido. | Por métrica, por GB y por alarma |
| Enlace con el data center | Site-to-Site VPN | El ERP sigue en el data center; el volumen no justifica enlace dedicado. | Por hora de conexión + tráfico |

### Recomendaciones para profundizar

*Sección 4 · La nube*

1. **Calculadora de costos** — Use la calculadora pública del proveedor y arme la estimación mensual de su solución. Guarde el enlace: es evidencia para el informe.
2. **Marco de buena arquitectura** — Lea el Well-Architected Framework del proveedor que elija y revise su diseño contra sus pilares.
3. **Arquitecturas de referencia** — Descargue dos diagramas de referencia oficiales de una aplicación web de tres capas y compárelos con el suyo.
4. **Modelos de cómputo** — Profundice en Fargate, Azure Container Apps y las funciones sin servidor: límites, arranque en frío y modelo de cobro exacto.
5. **Nivel gratuito** — Cree una cuenta con capa gratuita y despliegue una aplicación mínima. Es la única forma de entender de verdad la operación.

---

## Sección 5 · Atributos de calidad

- Escalabilidad: vertical, horizontal y elasticidad
- Alta disponibilidad, balanceo de carga y los «nueves» del uptime
- Rendimiento, observabilidad y detección temprana de errores
- El compromiso de nivel de servicio: SLA, SLO y SLI

### Escalabilidad

Este concepto se refiere a la capacidad y configuración que tiene la arquitectura de un sistema de darle servicio a un número creciente de usuarios sin perder sus características de performance originales.

Idealmente, una arquitectura tendría que poder darle servicio a un número creciente de usuarios simplemente agregando más equipos o servidores de aplicación a la solución, con el mínimo impacto posible en cuanto a las funcionalidades desarrolladas.

| Escalamiento vertical | Escalamiento horizontal | Elasticidad |
| --- | --- | --- |
| Agregar más recursos al mismo equipo:<br>más procesadores, más memoria. | Agregar más nodos a la solución,<br>repartiendo la carga entre ellos. | Que ese ajuste ocurra solo, hacia arriba<br>y hacia abajo, según la demanda real. |

### Escalamiento vertical · scaling up

Consiste en añadir más recursos de hardware en el mismo equipo: en general, adicionando más procesadores y memoria.

- Es fácil de aplicar: no exige cambios en la aplicación.

- Puede llegar a ser un método costoso: el precio no

crece de forma lineal con la capacidad.

**1 servidor**

- No evita el problema de tener un único punto de falla:

**1 servidor**

si el servidor queda fuera de servicio, no importa

**2 vCPU / 8 GB**

**16 vCPU**

más CPU

**64 GB**

cuántos recursos tenga, dejará de proveer servicio.

más RAM

- Tiene un techo físico: llega un momento en que no

existe un equipo más grande.

> Sirve como primera respuesta y para bases de datos que no se reparten con facilidad. No sirve como estrategia de disponibilidad.

### Escalamiento horizontal · scaling out

Significa agregar más nodos a la solución. Esto se puede lograr utilizando equipos de bajo costo.

- Por lo general es más económico: varios

**Balanceador de carga**

equipos modestos en vez de uno muy grande.

- Le permite a la solución tener capacidad de

| nodo | nodo | nodo | nodo | nodo |
| --- | --- | --- | --- | --- |
|   |   |   |   | cae, el resto de la arquitectura se adapta<br>para repartir la carga en los N-1 servidores<br>restantes.<br>Exige que la aplicación no guarde estado en<br>el nodo: la sesión debe vivir en un almacén<br>compartido.<br>La base de datos no siempre acompaña:<br>repartirla es un problema aparte. |

en

> Consecuencia para la arquitectura lógica: si quiere escalar horizontalmente, la aplicación tiene que ser «sin estado». Esa decisión se toma al diseñar el software, no al comprar el servidor.

### Elasticidad y autoescalado

La elasticidad es escalabilidad automática y en ambos sentidos: crecer cuando hay demanda y — sobre todo —

**decrecer cuando no la hay.**

| Disparadores | Límites | Tiempo de reacción | Efecto económico |
| --- | --- | --- | --- |
| Métricas que gatillan el<br>ajuste: uso de CPU, cantidad<br>de peticiones en cola,<br>latencia observada, o una<br>programación horaria<br>conocida. | Mínimo y máximo de<br>instancias. El mínimo protege<br>la disponibilidad; el máximo<br>protege el presupuesto. | Desde que sube la carga<br>hasta que la instancia nueva<br>atiende tráfico pasan<br>minutos. Si el pico es más<br>rápido, hay que anticiparlo. | Se dimensiona para la carga<br>habitual y no para el peak<br>anual. Ese ahorro es el<br>argumento central a favor de<br>la nube. |

> Ejemplo para su oferta: «El sistema opera con 2 instancias en régimen normal y escala hasta 8 cuando el uso de CPU supera el 65% durante 3 minutos. El costo se estima sobre un promedio de 3 instancias, con el peak de matrícula modelado por separado.»

### Balanceo de carga de trabajo

Esta característica se basa en que la configuración de la arquitectura asegure que cada equipo o servidor de aplicaciones tenga una carga de trabajo justa: que compartan todo el trabajo de forma equitativa y que no haya un único servidor con carga muy alta mientras el resto se encuentra ocioso.

| Reparto por turnos | Menor cantidad de conexiones | Comprobación de estado | Sesiones pegajosas |
| --- | --- | --- | --- |
| Cada petición va al siguiente<br>nodo de la lista. Simple y<br>suficiente cuando los nodos<br>son iguales. | Envía la petición al nodo que<br>tiene menos conexiones<br>activas. Mejor cuando las<br>peticiones duran distinto. | El balanceador consulta<br>periódicamente a cada nodo<br>y saca de rotación al que no<br>responde. Esta es la parte<br>que da disponibilidad. | Mantener a un usuario en el<br>mismo nodo. Resuelve el<br>estado, pero rompe el<br>reparto equitativo: mejor<br>sacar la sesión del nodo. |

> Capa 4 o capa 7: un balanceador de capa 4 reparte por IP y puerto — rápido y barato —; uno de capa 7 lee la petición y puede enrutar por ruta o por cabecera. Y él mismo puede fallar: en una arquitectura seria va redundado o es un servicio gestionado con disponibilidad comprometida.

### Alta disponibilidad

El propósito principal de tener múltiples servidores en una arquitectura lleva al concepto de poder soportar alta disponibilidad del sistema: si alguno de los equipos deja de ofrecer servicio por cualquier razón, el sistema debe continuar dando servicio por medio de los servidores restantes.

Es decir, si un servidor deja de funcionar, las solicitudes de un usuario tienen que ser redireccionadas a los servidores restantes sin tener ningún tipo de interrupción en el servicio ni requerir ningún tipo de acción.

| Disponibilidad | Uptime | Downtime |
| --- | --- | --- |
| Grado en que una aplicación o servicio<br>está disponible cuándo y cómo los<br>usuarios esperan. Se mide por la<br>percepción del usuario final. | Cantidad de tiempo que un sistema,<br>servidor o dispositivo trabaja sin<br>interrupciones. | Concepto opuesto: el tiempo durante el<br>cual el sistema no está operativo o está<br>inaccesible. |

### Lo que hay que examinar

| Inactividad NO planificada | Inactividad PLANIFICADA |
| --- | --- |
| Fallos del servidor: hardware, sistema operativo,<br>aplicación.<br>Fallos de datos: fallas en el almacenamiento, errores<br>humanos, fallos del sitio.<br>Corte de energía o de climatización.<br>Pérdida del enlace de comunicaciones.<br>Incidentes de seguridad.<br>Cuatro características de una solución de alta disponibilidad: | Cambios en el sistema: actualizaciones, parches,<br>nuevas versiones.<br>Cambios de datos: migraciones, reorganización,<br>cargas masivas.<br>Mantenimiento preventivo de hardware.<br>Planificar la inactividad puede ser muy complejo,<br>especialmente en empresas que soportan usuarios<br>en múltiples zonas horarias. |

| Recuperación | Operación continua | Detección de errores |
| --- | --- | --- |
| Hardware y software fiables, Capacidad de restaurar en el<br>incluida la base de datos. tiempo que exige el SLA. | Mantener el acceso a los<br>datos incluso durante el<br>mantenimiento. | Descubrir el problema rápido:<br>si demora 90 minutos, el SLA<br>ya se incumplió. |

### Los «nueves» de la disponibilidad

| Disponibilidad | Caída al año | Caída al mes | Caída al día | Qué arquitectura lo sostiene |
| --- | --- | --- | --- | --- |
| 90% | 36,5 días | 73 hrs | 2,4 hrs | Un servidor, sin redundancia |
| 95% | 18,3 días | 36,5 hrs | 1,2 hrs | Un servidor con respaldo manual |
| 98% | 7,3 días | 14,6 hrs | 28,8 min | Respaldo diario y soporte en horario hábil |
| 99% | 3,7 días | 7,3 hrs | 14,4 min | Redundancia parcial |
| 99,5% | 1,8 días | 3,66 hrs | 7,22 min | Redundancia en la capa de aplicación |
| 99,9% | 8,8 hrs | 43,8 min | 1,46 min | Redundancia completa + failover automático |
| 99,95% | 4,4 hrs | 21,9 min | 43,8 s | Multi-zona, monitoreo 24/7 |
| 99,99% | 52,6 min | 4,4 min | 8,6 s | Multi-zona activo-activo, equipo de guardia |
| 99,999% | 5,26 min | 26,3 s | 0,86 s | Multi-región, automatización total |
| 99,9999% | 31,5 s | 2,62 s | 0,08 s | Muy pocas organizaciones lo alcanzan |

> El 99,9% mensual equivale a 43,8 minutos de caída: si su plan de recuperación tarda una hora, ese compromiso ya es incumplible.

### Cómo se calcula la disponibilidad

**Disponibilidad = ( ( A – B ) / A ) × 100 %**

**Donde:**

| Variable | Definición | Ejemplo |
| --- | --- | --- |
| A | Horas comprometidas de disponibilidad | 24 × 365 = 8.760 horas / año |
| B | Número de horas fuera de línea durante el tiempo de disponibilidad comprometido | 15 horas por falla en un disco + 9 horas por mantenimiento preventivo no planeado = 24 horas |
| Resultado | Disponibilidad efectiva del período | ( (8.760 – 24) / 8.760 ) × 100 = 99,73% |

> Note que el mantenimiento no planificado también descuenta. Por eso los contratos definen ventanas de mantenimiento acordadas, que quedan excluidas del cálculo: eso se negocia y se escribe en el SLA.

### Detección de errores y observabilidad

Si un componente de la arquitectura falla, la rápida detección es esencial. Aunque sea posible recuperarse rápidamente de un corte, si toma 90 minutos descubrir el problema, no se puede satisfacer el SLA.

| Métricas | Registros (logs) | Trazas distribuidas |
| --- | --- | --- |
| Números en el tiempo: uso de CPU,<br>latencia, tasa de error, cantidad de<br>peticiones. Responden «¿cómo está el<br>sistema ahora?». | El detalle de lo que ocurrió, con contexto.<br>Responden «¿qué pasó exactamente en ese<br>momento?». | El recorrido completo de una petición a<br>través de varios servicios. Responden<br>«¿dónde se demoró?». |

| Alertas | Tablero operativo | Prueba de recuperación |
| --- | --- | --- |
| Reglas que avisan antes de que el usuario se<br>dé cuenta. Una alerta que nadie atiende no<br>sirve: hay que definir el turno. | Vista única del estado del servicio,<br>disponible para el mandante. Es una entrega<br>concreta que se puede ofrecer. | Restaurar el respaldo en un ambiente de<br>prueba, de forma periódica. Un respaldo<br>que nunca se restauró no es un respaldo. |

### Rendimiento: cómo se mide de verdad

**Latencia**

**Throughput**

**Concurrencia**

**Utilización**

Tiempo que tarda una

Cantidad de operaciones

Cuántos usuarios u

Qué porcentaje de CPU,

operación en responder. Se

atendidas por unidad de

operaciones simultáneas

memoria y disco se ocupa en

compromete por tipo de

tiempo. Es la medida de

soporta antes de degradarse.

régimen y en el máximo.

operación, no en general.

capacidad.

**Por qué el promedio no sirve:**

| Medida | Qué dice | Por qué importa |
| --- | --- | --- |
| Promedio | El tiempo típico de respuesta | Un 5% muy lento no mueve el promedio |
| Percentil 95 (p95) | El 95% de las peticiones responde en este tiempo o menos | Es el compromiso razonable en un SLA: representa la experiencia de casi todos |
| Percentil 99 (p99) | Sólo 1 de cada 100 peticiones es más lenta que esto | Revela problemas intermitentes que el promedio esconde |
| Máximo | La peor respuesta observada | Detecta tiempos de espera agotados y bloqueos |

> Escriba «el p95 de la consulta de saldo es menor a 2 segundos con 500 usuarios concurrentes», no «el sistema será rápido».

### SLA, SLO y SLI · lo que se firma

| SLO · objetivo | SLA · acuerdo |
| --- | --- |
| La métrica que se mide. El valor que se quiere cumplir<br>internamente.<br>Ejemplo: porcentaje de peticiones<br>atendidas correctamente en menos de 2 Ejemplo: 99,9% de las peticiones cumplen<br>segundos. el indicador, medido mensualmente.<br>Lo que un SLA debe declarar para ser defendible:<br>Qué servicio cubre y qué queda excluido. • Las ventanas<br>Cómo y dónde se mide, y quién es el árbitro de la medición. • Los tiempos<br>incidente.<br>El horario de cobertura: 24/7 no cuesta lo mismo que horario<br>hábil. • Las penalidades | El compromiso contractual con el<br>mandante, con consecuencias si no se<br>cumple.<br>Ejemplo: 99,5% mensual, con descuento<br>del 5% de la cuota si no se alcanza.<br>de mantenimiento acordadas, excluidas del cálculo.<br>de respuesta y de solución por severidad del<br>y su tope máximo. |

> Regla de oro: ofrezca el nivel de servicio que su arquitectura efectivamente sostiene. Un SLA que no puede cumplir es una multa diferida, y debe ir en la matriz de riesgos.

### Recomendaciones para profundizar

*Sección 5 · Atributos de calidad*

1. **Cálculo de disponibilidad** — Calcule la disponibilidad compuesta de su arquitectura: componentes en serie multiplican sus disponibilidades y bajan el resultado.
2. **Pruebas de carga** — Investigue una herramienta de pruebas de carga y diseñe el escenario que validaría el p95 que va a comprometer.
3. **SLA reales** — Descargue los acuerdos de nivel de servicio publicados por dos proveedores y compare exclusiones, medición y compensaciones.
4. **Observabilidad** — Revise el estándar OpenTelemetry y defina las cinco métricas y las tres alertas mínimas de su solución.
5. **Ingeniería de confiabilidad** — Lea sobre SRE: presupuesto de error, indicadores y objetivos de servicio. Es el marco detrás de todo lo visto en esta sección.

---

## Sección 6 · Continuidad

- Activo-Pasivo y Activo-Activo: qué significa cada uno y qué cuesta
- RTO y RPO: los dos números que definen toda la estrategia
- Sincronizar datos entre sitios: replicación, topologías y conflictos
- Escenarios híbridos: nube + on-premise y nube + nube
- Respaldos: tipos, política, inmutabilidad y la prueba de restauración

### Activo – Pasivo · qué significa

Hay dos nodos — o dos sitios — capaces de dar el servicio, pero sólo uno atiende tráfico. El otro espera, listo para tomar el relevo.

**NODO ACTIVO**

| Usuarios | Balanceador o DNS | atiende el 100% NODO ACTIVO |
| --- | --- | --- |
| La conmutación | (failover) puede ser automática o manual. Ese | NODO PASIVO<br>en espera<br>Ese detalle es el que define el RTO real. |

| A favor | En contra |
| --- | --- |
| · Simple de diseñar y de operar.<br>· No exige que la aplicación tolere ejecución simultánea.<br>· Sin conflictos de datos: sólo un nodo escribe. | · Se paga capacidad que no produce.<br>· El nodo pasivo suele descubrirse roto justo cuando se necesita.<br>· El RTO nunca es cero: siempre hay un tiempo de conmutación. |

### Activo – Activo · qué significa

Los dos nodos — o los dos sitios — atienden tráfico al mismo tiempo. Si uno cae, el otro absorbe su carga.

**NODO A atiende ~50%**

| Balanceador global | atiende ~50% NODO A |
| --- | --- |
|   | NODO B<br>atiende ~50% |

| A favor | En contra |
| --- | --- |
| · Toda la capacidad comprada está produciendo.<br>· La conmutación es casi instantánea: el otro nodo ya está<br>atendiendo.<br>· Permite mantenimiento sin ventana: se saca un nodo de rotación. | · Exige aplicación sin estado y sesión compartida.<br>· Los datos deben sincronizarse en ambos sentidos: aparecen los<br>conflictos.<br>· Hay que dimensionar cada nodo para absorber la carga del otro<br>(regla del 50%). |

### Pasivo frío, tibio y caliente

El nodo en espera puede estar apagado, encendido pero sin datos al día, o listo para recibir tráfico en segundos. Cada nivel tiene su precio.

| Modalidad | En qué estado está el sitio alternativo | RTO típico | RPO típico | Costo relativo |
| --- | --- | --- | --- | --- |
| Frío | Hardware o suscripción disponible, pero sin sistema instalado. Hay que aprovisionar y restaurar desde respaldo. | Horas a días | Hasta el último respaldo | Bajo |
| Tibio | Sistema instalado y actualizado, con datos replicados periódicamente. No atiende tráfico. | Minutos a horas | Minutos a horas | Medio |
| Caliente | Réplica completa y sincronizada, lista para tomar tráfico con sólo cambiar el enrutamiento. | Segundos a minutos | Segundos o cero | Alto |
| Activo-Activo | Ya está atendiendo tráfico. No hay «conmutación»: hay redistribución de carga. | Casi cero | Cero o casi cero | Muy alto |

> El mandante no elige una modalidad: elige un RTO y un RPO. La modalidad es la consecuencia técnica de esa elección, y el costo es la consecuencia económica.

### RTO y RPO · los dos números

Puede haber muchas opciones para recuperarse de un fallo. Lo primero es determinar qué fallos pueden ocurrir y de qué forma recuperarse en el tiempo que satisface las necesidades del negocio.

| RTO · Recovery Time Objective | RPO · Recovery Point Objective |
| --- | --- |
| ¿Cuánto tiempo puede estar caído el sistema?<br>Se mide desde la falla hasta el servicio restablecido.<br>RTO de 4 horas: basta restaurar desde respaldo.<br>RTO de 15 minutos: exige un sitio alternativo tibio o<br>caliente.<br>RTO cercano a cero: exige activo-activo en dos ubicaciones. | ¿Cuántos datos puede perder el negocio?<br>Se mide en tiempo: cuánto trabajo se pierde.<br>RPO de 24 horas: respaldo diario es suficiente.<br>RPO de 1 hora: respaldo incremental frecuente o<br>replicación asincrónica.<br>RPO cero: replicación sincrónica, y se paga en latencia. |

> Cómo se determinan: no los define el equipo técnico, los define el impacto en el negocio del mandante. Pregunta guía: «si el sistema se cae un martes a las 11 de la mañana, ¿qué deja de poder hacer la organización y cuánto cuesta cada hora?».

### Activo-Activo vs. Activo-Pasivo · decidir

| Criterio | Activo – Pasivo | Activo – Activo |
| --- | --- | --- |
| Uso de la capacidad instalada | 50%: la mitad espera | 100%: todo produce |
| RTO alcanzable | Segundos a horas, según frío/tibio/caliente | Casi cero |
| Complejidad de la aplicación | Baja: puede guardar estado local | Alta: debe ser sin estado, con sesión compartida |
| Complejidad de los datos | Baja: un solo nodo escribe | Alta: hay que resolver escritura concurrente y conflictos |
| Licenciamiento del motor | A veces se licencia sólo el activo | Se licencian ambos nodos |
| Costo de red entre sitios | Bajo: sólo replicación | Alto: tráfico permanente en ambos sentidos |
| Riesgo de partición (split-brain) | Bajo | Alto: exige árbitro o quórum |
| Mantenimiento sin ventana | Parcial: se conmuta y se mantiene el otro | Sí: se saca un nodo de rotación |
| Cuándo elegirlo | La mayoría de los casos del curso: cumple 99,5% – 99,9% a costo razonable | Servicios críticos con RTO cercano a cero y presupuesto que lo respalde |

### El problema de sincronizar datos

Replicar la aplicación es fácil: se copia y se levanta otra instancia. Replicar los datos es el problema difícil,

**porque los datos cambian.**

**La latencia es física**

**Hay que elegir**

Confirmar una escritura en un sitio remoto toma el tiempo de ida y

Ante una caída del enlace entre sitios sólo se puede sostener dos de

vuelta del enlace. Ese tiempo se suma a cada transacción y no se

tres: consistencia, disponibilidad y tolerancia a la partición. La

puede optimizar por software.

partición ocurre igual, así que la elección real es entre consistencia y disponibilidad.

| Partición de cerebro | No todo dato es igual |
| --- | --- |
| Si el enlace se corta y ambos sitios se creen activos, ambos aceptan<br>escrituras y los datos divergen. Reconciliar después es caro y a veces<br>imposible. | El saldo de una cuenta exige consistencia inmediata. El contador de<br>visitas no. Clasificar los datos por criticidad permite no pagar<br>consistencia estricta en todo. |

> Primera decisión de la sección: qué datos se replican, en qué sentido y con qué garantía. No es una decisión de infraestructura: es una decisión de negocio.

### Replicación sincrónica vs. asincrónica

| SINCRÓNICA | ASINCRÓNICA |
| --- | --- |
| La transacción se confirma sólo cuando ambos sitios<br>escribieron.<br>RPO = 0: no se pierde ningún dato confirmado.<br>Cada escritura paga la latencia del enlace: si son 40 ms<br>de ida y vuelta, cada transacción cuesta 40 ms más.<br>Si el sitio remoto no responde, o se detiene el servicio o<br>se degrada a asincrónica.<br>Viable sólo con enlaces de baja latencia: mismo edificio,<br>misma ciudad o zonas de la misma región. | La transacción se confirma localmente y después se<br>envía al otro sitio.<br>RPO > 0: se pierde lo que estaba en tránsito al momento<br>de la falla.<br>No penaliza el tiempo de respuesta de la aplicación.<br>El sitio remoto puede caerse sin afectar la operación: se<br>acumula el retraso.<br>Es la única opción razonable entre ciudades, entre países<br>o entre proveedores de nube. |

> Regla práctica: sincrónica dentro de la región (entre zonas de disponibilidad), asincrónica entre regiones o hacia on-premise. Declare el retraso esperado de la réplica: ése es su RPO real.

### Topologías de replicación

| Primario – réplica | Multi-primario | Quórum | Envío de registro / CDC |
| --- | --- | --- | --- |
| Un solo nodo acepta<br>escrituras; los demás son<br>copias de sólo lectura.<br>+ Simple, sin conflictos<br>posibles.<br>− La réplica no puede escribir:<br>en un failover hay que<br>promoverla.<br>Uso: el caso más frecuente y<br>el recomendado por defecto. | Varios nodos aceptan<br>escrituras y se replican entre<br>sí.<br>+ Habilita activo-activo real<br>con escritura en ambos sitios.<br>− Aparecen conflictos cuando<br>dos sitios modifican el mismo<br>dato.<br>Uso: sólo si el negocio exige<br>escribir en ambos sitios. | La escritura se confirma<br>cuando la acepta la mayoría<br>de los nodos.<br>+ Tolera la caída de una<br>minoría sin perder<br>consistencia.<br>− Requiere número impar de<br>nodos y un tercer sitio árbitro.<br>Uso: bases distribuidas y<br>clústeres de tres o más nodos. | Se replica el registro de<br>transacciones, o se capturan<br>los cambios y se publican<br>como eventos.<br>+ Sirve para alimentar otros<br>sistemas, reportería o un lago<br>de datos.<br>− Retraso variable; no es un<br>mecanismo de alta<br>disponibilidad.<br>Uso: integración y analítica. |

### Escenario A · nube + on-premise

El mandante conserva su data center y la solución se extiende a la nube. La pregunta es qué dato vive dónde y en qué sentido viaja.

**ON-PREMISE · data center del mandante**

**NUBE · región del proveedor**

**Sistemas heredados / ERP**

**Portal público (autoescalado)**

**Enlace dedicado o VPN**

**Base de datos primaria**

**Réplica de lectura**

**Directorio de identidad**

**Respaldo replicado**

| Qué hay que definir | Decisión típica |
| --- | --- |
| Conectividad | Enlace dedicado si hay replicación continua; VPN sólo para volúmenes bajos. Declare su costo. |
| Sentido del dato | El primario suele quedar donde está el sistema heredado; la nube recibe réplica de lectura. |
| Identidad | Una sola fuente de identidad — el directorio del mandante —, federada a la nube. Nunca dos listas. |
| Latencia | Medir el ida y vuelta real antes de comprometer tiempos: el enlace se suma a cada consulta. |

### Escenario B · nube + nube

Dos proveedores distintos, o dos regiones del mismo proveedor. Reduce el riesgo de proveedor único, pero introduce costos que suelen olvidarse.

| Aspecto | Dos regiones · mismo proveedor | Dos proveedores distintos |
| --- | --- | --- |
| Complejidad | Moderada: mismas herramientas y misma consola | Alta: dos ecosistemas, dos equipos formados |
| Replicación de datos | El proveedor ofrece replicación entre regiones como servicio | Hay que construirla: replicación del motor o flujo de eventos propio |
| Costo de transferencia | Tráfico entre regiones, facturado por GB | Salida a Internet en ambos sentidos: el ítem más caro y el más olvidado |
| Enrutamiento del tráfico | DNS con verificación de estado del proveedor | DNS de un tercero independiente, para no depender de ninguno de los dos |
| Identidad y secretos | Un solo sistema de identidad | Federación entre dos sistemas distintos, o un proveedor de identidad externo |
| Qué protege | Caída de una región completa | Caída total de un proveedor y dependencia comercial |
| Cuándo se justifica | Exigencia de continuidad ante desastre regional | Exigencia contractual explícita del mandante, o riesgo de proveedor evaluado y documentado |

> Advertencia para la oferta: la multinube «por si acaso» es innovación que resta. Si la propone, cuantifique el costo adicional de red, licencias y horas de operación.

### Conflictos: cuando dos sitios escriben lo mismo

En una topología multi-primario, tarde o temprano dos sitios modifican el mismo registro casi al mismo tiempo. Hay que decidir de antemano qué pasa.

| Gana la última escritura | Control de versión | Fusión automática | Evitarlo por diseño |
| --- | --- | --- | --- |
| Se conserva la versión con la<br>marca de tiempo más<br>reciente.<br>Simple, pero pierde datos en<br>silencio y depende de relojes<br>bien sincronizados. | Cada registro lleva una<br>versión; si no coincide, la<br>escritura se rechaza y la<br>aplicación decide.<br>No pierde datos, pero traslada<br>el problema a la aplicación. | Estructuras diseñadas para<br>combinarse sin conflicto<br>(contadores, conjuntos, listas).<br>Elegante, pero sólo sirve para<br>ciertos tipos de dato. | Repartir los datos de modo<br>que cada sitio sea dueño<br>exclusivo de una porción: por<br>sucursal, por región, por rango<br>de clientes.<br>Es la estrategia más robusta:<br>el conflicto simplemente no<br>ocurre. |

> Y para el corte del enlace: defina un árbitro o un tercer sitio de quórum que decida quién sigue siendo el activo. Sin árbitro, ambos sitios se creerán activos y los datos divergirán.

### Failover y failback · el procedimiento

**1**

**Detección**

Monitoreo que confirma la falla y descarta un falso positivo. Umbral y tiempo de confirmación declarados.

**2**

**Decisión**

Automática por regla, o manual con responsable identificado y canal de autorización definido.

**3**

**Promoción**

La réplica pasa a primaria: se habilita la escritura y se verifica la integridad de los datos.

Cambio de enrutamiento. Con DNS, el tiempo de vida del registro define cuánto tardan los usuarios en llegar al

**4**

**Redirección**

nuevo sitio.

**5**

**Verificación**

Pruebas funcionales mínimas antes de declarar el servicio restablecido. Comunicación al mandante.

Vuelta al sitio original: resincronizar los datos generados durante la contingencia, y recién entonces conmutar de

**6**

**Failback**

vuelta.

> Un plan de recuperación que nunca se ensayó no es un plan: comprometa una prueba de conmutación al menos anual y declárela en la oferta.

### Respaldo no es lo mismo que replicación

**Es el malentendido más caro de esta unidad: creer que por tener réplica no se necesita respaldo.**

| REPLICACIÓN | RESPALDO |
| --- | --- |
| Mantiene una copia al día en otro sitio.<br>Protege contra: caída de un servidor, de una zona o de<br>un sitio completo.<br>NO protege contra: borrado accidental, corrupción de<br>datos, error de la aplicación o cifrado por ransomware.<br>Porque el error se replica al otro sitio en segundos.<br>Sirve para la disponibilidad. | Guarda copias de distintos momentos en el tiempo.<br>Protege contra: borrado, corrupción, error humano,<br>ransomware y fallas lógicas.<br>NO reemplaza a la replicación: restaurar toma tiempo, a<br>veces horas.<br>Permite volver a un punto anterior al error.<br>Sirve para la recuperación. |

> Toda arquitectura seria tiene las dos cosas. En el informe deben aparecer como dos secciones distintas, con dos costos distintos.

### Tipos de respaldo

| Tipo | Qué copia | Espacio que ocupa | Tiempo de copia | Tiempo de restauración |
| --- | --- | --- | --- | --- |
| Completo | Todo, cada vez. | Máximo | Largo | Corto: un solo archivo |
| Incremental | Sólo lo cambiado desde la copia anterior, sea cual sea. | Mínimo | Muy corto | Largo: hay que encadenar todas las copias |
| Diferencial | Todo lo cambiado desde el último respaldo completo. | Medio | Medio | Medio: completo + último diferencial |
| Instantánea (snapshot) | Estado del volumen en un instante, a nivel de almacenamiento. | Bajo al inicio, crece con los cambios | Segundos | Muy corto |
| Continuo (PITR) | Registro permanente de transacciones que permite volver a cualquier segundo. | Alto | Continuo | Variable: exige reproducir el registro |

> Advertencia sobre las instantáneas: viven en el mismo almacenamiento que el dato original. Son rapidísimas para deshacer un error, pero no son un respaldo: si se pierde la cabina o la cuenta, se pierden con ella.

### La política de respaldo

| Regla 3-2-1 | Extensión 3-2-1-1-0 | Frecuencia | Retención GFS |
| --- | --- | --- | --- |
| Tres copias de los datos, en<br>dos medios distintos, con una<br>fuera del sitio. Es el estándar<br>citable y el mínimo<br>defendible. | Una de las copias además<br>inmutable o desconectada, y<br>cero errores en la verificación.<br>Es la respuesta al<br>ransomware. | Se deriva del RPO: si el RPO es<br>1 hora, no puede haber<br>respaldo diario. Declare<br>frecuencia por tipo de dato. | Esquema abuelo-padre-hijo:<br>diarias por 30 días, semanales<br>por 3 meses, mensuales por 1<br>año, anuales por 5. Ajústelo a<br>la normativa del caso. |

| Inmutabilidad | Cifrado | Aislamiento de credenciales | Registro y alertas |
| --- | --- | --- | --- |
| Copias que no se pueden<br>borrar ni alterar durante un<br>período, ni siquiera por un<br>administrador. Es la defensa<br>contra el borrado malicioso. | El respaldo contiene los<br>mismos datos personales que<br>la producción: va cifrado, con<br>las llaves gestionadas aparte. | Quien administra la<br>producción no debe poder<br>borrar los respaldos. Cuentas<br>y permisos separados. | Cada ejecución deja registro, y<br>el fallo genera alerta. Un<br>respaldo que falla en silencio<br>durante tres meses es lo<br>habitual. |

### Restaurar · lo único que importa

Nadie necesita respaldos. Lo que se necesita son restauraciones. Y sólo se sabe que un respaldo sirve

**cuando se restaura.**

**Pruebe la restauración**

**Pruebe el escenario completo**

Restaurar en un ambiente aislado, de forma periódica, y medir

No sólo un archivo: la base completa, con la aplicación levantada y

cuánto tardó. Ese número es su RTO real, no el que estimó en la

funcionando. Una restauración parcial no demuestra nada.

propuesta.

| Documente el procedimiento | Considere el escenario peor |
| --- | --- |
| Paso a paso, ejecutable por alguien que no lo escribió, a las 3 de la<br>mañana y sin acceso a quien lo diseñó. | Ransomware: la producción y las réplicas están cifradas. ¿Desde<br>dónde restaura? Ésa es la copia inmutable y desconectada. |

> Compromiso concreto y barato de ofrecer: «Prueba de restauración trimestral en ambiente aislado, con informe de resultados y tiempo medido, entregado al mandante». Diferencia una oferta seria de una que sólo dice que respalda.

### Continuidad en la oferta · qué declarar

| Elemento | Qué declarar | Ejemplo |
| --- | --- | --- |
| Modalidad | Activo-activo, activo-pasivo caliente, tibio o frío, y por qué. | Activo-pasivo caliente entre dos zonas de disponibilidad. |
| RTO comprometido | Tiempo máximo de interrupción y cómo se alcanza. | 2 horas, con promoción automática de la réplica. |
| RPO comprometido | Pérdida máxima de datos y el mecanismo que la sostiene. | 15 minutos, por replicación asincrónica continua. |
| Replicación | Tipo, sentido, latencia esperada y qué datos incluye. | Asincrónica del primario a la réplica; retraso medio menor a 10 s. |
| Respaldo | Frecuencia, tipo, destino, cifrado y retención. | Completo semanal + incremental diario; retención GFS a 5 años. |
| Inmutabilidad | Si existe copia inmutable y por cuánto tiempo. | Copia inmutable de 35 días en almacenamiento de objetos. |
| Pruebas | Frecuencia de la prueba de restauración y de la de conmutación. | Restauración trimestral; conmutación anual, con informe. |
| Costo asociado | Cuánto de la inversión y del gasto anual corresponde a continuidad. | Se identifica como línea separada en el flujo de caja. |

### Recomendaciones para profundizar

*Sección 6 · Continuidad*

1. **Análisis de impacto al negocio** — Investigue cómo se hace un BIA y úselo para justificar el RTO y el RPO de su caso con cifras, no con intuición.
2. **Replicación de bases de datos** — Estudie la replicación del motor que eligió: modos sincrónico y asincrónico, promoción de réplica y tiempo de conmutación.
3. **Teorema CAP y quórum** — Profundice en CAP y en los esquemas de quórum. Entienda por qué no se puede tener consistencia y disponibilidad ante una partición.
4. **Respaldo inmutable** — Revise cómo se configura una copia inmutable y qué protección real ofrece frente a ransomware.
5. **Plan de recuperación** — Busque una plantilla de DRP y escriba el procedimiento de conmutación de su solución, paso a paso y con responsables.

---

## Sección 7 · Seguridad

- Defensa en profundidad, capa por capa del modelo OSI
- La capa de seguridad de una solución expuesta a Internet
- Identidad, acceso y protección de datos
- Caso integrador: red interna, home office, sistemas internos y portales públicos
- Monitoreo, respuesta a incidentes y cumplimiento normativo

### Defensa en profundidad, capa por capa

«La solución será segura» no es una medida. Seguridad es un control concreto en cada capa, y cada control es un componente

**que se cotiza.**

| Capa OSI | Amenaza típica | Control que corresponde |
| --- | --- | --- |
| 7 · Aplicación | Inyección SQL, XSS, abuso de la API, credenciales robadas | WAF con reglas OWASP, validación de entradas, límite de llamadas, autenticación fuerte |
| 6 · Presentación | Tráfico en claro, certificados vencidos, cifrado obsoleto | TLS vigente de extremo a extremo, gestión y renovación automática de certificados |
| 5 · Sesión | Robo o fijación de sesión, sesiones que nunca expiran | Cookies seguras, expiración e inactividad, revocación central de sesiones |
| 4 · Transporte | Puertos abiertos de más, agotamiento de conexiones | Grupos de seguridad con puertos mínimos, límites de conexión, protección contra inundación |
| 3 · Red | Movimiento lateral dentro de la red, acceso desde direcciones no autorizadas | Segmentación en subredes, firewall entre zonas, listas de origen permitido, VPN |
| 2 · Enlace | Equipos no autorizados en la red interna | VLAN por tipo de usuario, control de acceso por puerto |
| 1 · Física | Acceso físico al equipamiento, corte de enlace | Control de acceso a la sala, enlaces redundantes con proveedores distintos |

> En el informe, esta tabla — con la columna de la derecha completada para su caso — responde de una sola vez a la pregunta por la seguridad de la solución.

### La superficie de exposición

Antes de proteger, hay que saber qué está expuesto. Todo lo que se puede alcanzar desde Internet es superficie de ataque, y todo lo que no se publica no hay que defenderlo.

| Portal público | API pública | Endpoints de webhook |
| --- | --- | --- |
| El sitio del cliente final. Expuesto por<br>definición: es el que más protección<br>necesita. | Consumida por aplicaciones móviles o por<br>terceros. Necesita autenticación, versión y<br>límite de uso. | URLs que reciben notificaciones de terceros.<br>Son públicas y hay que validar el origen de<br>cada llamada. |

| Consolas de administración | Bases de datos | Ambientes no productivos |
| --- | --- | --- |
| Nunca deben publicarse a Internet. Se<br>acceden por VPN o por acceso condicional<br>con doble factor. | Jamás expuestas. Si el diagrama muestra la<br>base de datos con dirección pública, la<br>propuesta ya perdió puntaje. | Desarrollo y QA olvidados con datos reales y<br>sin protección son la puerta de entrada más<br>común. |

> Principio de mínima exposición: se publica el puerto 443 del portal y de la API, y nada más. Todo el resto se alcanza desde dentro o por acceso controlado.

### La capa de seguridad de una solución expuesta

**Internet · usuario o atacante**

todo lo que llega es no confiable

**BORDE**

**(fuera de su red)**

**Protección contra denegación de servicio**

absorbe el volumen antes del origen

**CDN · caché en el borde**

reduce el tráfico que llega al sistema

**WAF · filtrado de capa 7 (OWASP Top 10)**

bloquea inyección, XSS, bots

**PERÍMETRO**

**(DMZ)**

**Balanceador · terminación TLS**

cifrado, certificados, salud de nodos

**API Gateway · autenticación y límite de uso**

identifica y acota a quien llama

| RED PRIVADA PERÍMETRO | Aplicación en subred privada Internet · usuario o atacante CDN · caché en el borde |
| --- | --- |
|   | Base de datos en subred de datos · cifrada sólo acepta a la capa de aplicación |

> Cada escalón que se omite hay que justificarlo. Un portal público sin WAF es un hallazgo que el evaluador va a marcar.

### Identidad y acceso

Hoy la mayoría de los incidentes no rompe el muro: entra con una credencial válida. Por eso la identidad es el

**nuevo perímetro.**

| Inicio de sesión único | Doble factor |
| --- | --- |
| Una sola fuente de usuarios para todos los El usuario se autentica una vez y accede<br>sistemas. Cuando alguien deja la los sistemas autorizados. Menos<br>organización, se desactiva en un lugar y contraseñas, menos reutilización, mejor<br>pierde el acceso a todo. trazabilidad. | a Obligatorio para administradores y para<br>todo acceso desde fuera de la red<br>corporativa. Es la medida individual con<br>mejor relación costo-beneficio. |

| Permisos por rol | Cuentas de servicio | Revisión periódica |
| --- | --- | --- |
| Se otorgan a roles, no a personas. Mínimo<br>privilegio: cada rol tiene sólo lo que<br>necesita para su función. | Las que usan los sistemas entre sí:<br>nominadas, con permisos acotados,<br>credenciales rotadas y nunca compartidas<br>con personas. | Recertificación de accesos al menos anual.<br>Los permisos se acumulan: nadie devuelve<br>un acceso que ya no usa. |

> «Confianza cero»: ninguna red es confiable por sí sola, ni siquiera la interna. Cada acceso se autentica y se autoriza según quién es, desde qué dispositivo y a qué recurso, venga de donde venga.

### Protección de los datos

| Cifrado en reposo | Gestión de llaves |
| --- | --- |
| TLS vigente en toda comunicación, incluida Discos, base de datos, respaldos y<br>la interna entre servicios. Sin excepciones almacenamiento de objetos cifrados. En<br>«porque es la red privada». nube suele venir activado; declárelo igual. | Las llaves viven en un servicio de gestión de<br>la llaves o en un almacén de secretos, con<br>rotación y con acceso auditado. |

| Enmascaramiento | Registro de auditoría |
| --- | --- |
| No recolectar ni almacenar lo que no se Los ambientes de desarrollo y QA usan<br>necesita. El dato que no existe no se puede datos anonimizados o sintéticos, nunca la<br>filtrar ni hay que protegerlo. copia de producción tal cual.<br>Seguridad en el ciclo de desarrollo: | Quién accedió a qué dato personal y<br>la cuándo, conservado por el período que<br>exige la normativa e inalterable. |

| Análisis automático | Gestión de parches | Pruebas de intrusión |
| --- | --- | --- |
| Referencia estándar de las Revisión de código y de<br>vulnerabilidades más dependencias en cada<br>frecuentes en aplicaciones cambio, dentro de la<br>web. Citable en la oferta. canalización. | Bibliotecas y sistemas<br>actualizados. La mayoría de<br>los ataques usa fallas ya<br>conocidas. | Antes de salir a producción, y<br>periódicas después. Es un<br>ítem cotizable de la oferta. |

### Caso · empresa con trabajo mixto

Tres orígenes de acceso, tres caminos de control, dos tipos de sistema.

**QUIÉN ACCEDE**

**CÓMO SE CONTROLA**

**A QUÉ ZONA LLEGA**

**QUÉ PUEDE USAR**

**Red corporativa**

| VLAN + control de puerto + antivirus | SISTEMAS INTERNOS QUÉ PUEDE USAR Remuneraciones Expedientes Finanzas |
| --- | --- |
| VPN o acceso Zero Trust | Reportes de gestión |

**Funcionario**

| desde su casa en la oficina Funcionario | + doble factor + verificación del VPN o acceso Zero Trust CÓMO SE CONTROLA |
| --- | --- |
| Cliente final | Internet público DMZ PORTAL PÚBLICO |

| CDN + WAF + límite de uso Internet público Red corporativa | zona pública DMZ | trámites del cliente PORTAL PÚBLICO |
| --- | --- | --- |
| el portal accede | a la API interna por un único puerto |   |

> Regla de oro: el funcionario en su casa NO recibe más permisos por estar en la VPN. Recibe los mismos que en la oficina, y para los trámites entra al portal público como cualquier persona.

### Dos zonas, dos reglas

|   | Sistemas internos · administrativos | Portal público · cliente final |
| --- | --- | --- |
| Quién entra | Sólo funcionarios con cuenta corporativa | Cualquier persona en Internet; con o sin registro previo |
| Desde dónde | Red corporativa, o desde la casa por VPN / acceso Zero Trust | Desde cualquier red y cualquier dispositivo |
| Autenticación | Identidad corporativa con inicio de sesión único y doble factor | Registro propio o identidad digital externa; doble factor para operaciones sensibles |
| Exposición a Internet | Ninguna: no tiene dirección pública | Total: es su razón de ser |
| Dónde se despliega | Subred privada de aplicaciones | DMZ, detrás de CDN y WAF |
| Datos que maneja | Información sensible de la organización y de terceros | Datos del propio usuario, acotados a su trámite |
| Carga esperada | Predecible: cantidad conocida de funcionarios en horario hábil | Variable e impredecible: se dimensiona con autoescalado |
| Disponibilidad | Horario hábil suele bastar; se puede acordar ventana de mantenimiento amplia | 24/7 con ventana mínima: el ciudadano entra a cualquier hora |
| Riesgo principal | Abuso de privilegios y fuga interna de información | Ataques automatizados, denegación de servicio y suplantación |

### Cómo se conecta el funcionario desde la casa

| VPN tradicional | Acceso Zero Trust | Publicación con acceso condicional |
| --- | --- | --- |
| El equipo del funcionario se conecta a la red<br>corporativa y queda «dentro».<br>+ Conocida, soportada por todo, fácil de<br>justificar.<br>− Da acceso a toda la red: si el equipo<br>doméstico está comprometido, el problema<br>entra completo.<br>− Concentra tráfico y puede saturarse. | El funcionario no entra a la red: se le publica<br>cada aplicación de forma individual,<br>verificando identidad, doble factor y estado<br>del equipo en cada acceso.<br>+ Sin acceso lateral a la red; permisos por<br>aplicación.<br>+ Mejor experiencia y mejor trazabilidad.<br>− Requiere un servicio adicional y su costo. | La aplicación interna se publica en Internet<br>detrás de un proxy con doble factor y reglas<br>por país, dispositivo y horario.<br>+ No requiere cliente instalado.<br>− Aumenta la superficie expuesta: exige<br>WAF y monitoreo estricto.<br>− No apto para sistemas muy sensibles. |

> Común a las tres: doble factor obligatorio, equipo con antivirus gestionado y disco cifrado, sesión con expiración, y registro de cada acceso. Sin eso, ninguna de las tres es segura.

### Una identidad, permisos distintos

El mismo funcionario entra desde la oficina y desde la casa, y a veces también usa el portal público como ciudadano. Es una sola identidad con reglas distintas según el contexto.

**PROVEEDOR DE IDENTIDAD ÚNICO**

**(directorio corporativo)**

**Acceso desde la oficina**

**Acceso desde la casa**

**red conocida · riesgo bajo**

**red desconocida · riesgo alto**

**Usuario y contraseña**

**Doble factor + equipo verificado**

**+ sesión de 8 horas**

**+ sesión de 2 horas**

> Eso es acceso condicional: los permisos son los mismos, lo que cambia es la exigencia para obtenerlos. Y hay operaciones — aprobar un pago, exportar una base — que pueden exigir doble factor siempre, esté donde esté el funcionario.

### Monitoreo, incidentes y cumplimiento

**Centralización de**

**Detección y alertas**

**Plan de respuesta**

**Notificación de brechas**

**registros**

Los eventos de seguridad de

Reglas que avisan ante

Quién hace qué, en qué orden

La normativa vigente en Chile

todos los componentes van a

accesos anómalos, intentos

y a quién se avisa. Escrito

exige informar a la Agencia y a

un solo lugar, correlacionados

masivos de autenticación o

antes del incidente, no

los titulares dentro de un

y conservados por el período

exportaciones inusuales de

durante.

plazo acotado: sin detección,

que exige la normativa.

datos.

ese plazo no se cumple.

**Marco normativo aplicable en Chile:**

| Obligación | Qué exige | Consecuencia en la arquitectura |
| --- | --- | --- |
| Registro de tratamiento | Documentar qué datos personales se tratan, para qué y con qué base legal. | Inventario de datos y trazabilidad por sistema. |
| Derechos del titular | Acceso, rectificación, cancelación y oposición. | Funciones de exportación y eliminación, no sólo de captura. |

> Ley N° 21.719, publicada el 13 de diciembre de 2024; entrada en plena vigencia el 1 de diciembre de 2026. Cite la norma en el informe según APA 7.ª ed.

### Monitoreo, incidentes y cumplimiento · continuación 1

| Obligación | Qué exige | Consecuencia en la arquitectura |
| --- | --- | --- |
| Notificación de brechas | Informar a la Agencia y a los titulares en el plazo establecido. | Detección temprana, registro de auditoría y procedimiento definido. |
| Seguridad proporcional al riesgo | Medidas técnicas acordes al tipo de dato tratado. | Cifrado, control de acceso y minimización de datos. |
| Encargados de tratamiento | Acuerdo con los proveedores que traten datos por cuenta del responsable. | El proveedor de nube es un encargado: hay que declararlo y contratarlo. |

### Seguridad en la oferta · qué declarar

| Ámbito | Qué declarar | Ejemplo de redacción |
| --- | --- | --- |
| Exposición | Qué se publica a Internet y qué no. | Sólo el portal y la API pública, por el puerto 443, detrás de CDN y WAF. |
| Perímetro | Componentes y sus reglas. | Protección contra denegación de servicio; WAF con conjunto de reglas OWASP en modo bloqueo. |
| Segmentación | Zonas de red y tráfico permitido entre ellas. | Tres subredes: web, aplicación y datos; el tráfico sólo desciende un nivel. |
| Identidad | Fuente, factores y política de sesión. | Directorio corporativo con SSO; doble factor para acceso remoto y para administradores. |
| Acceso remoto | Mecanismo elegido y sus condiciones. | Acceso Zero Trust por aplicación, con verificación de equipo y sesión de 2 horas. |
| Datos | Cifrado, llaves, retención y datos en ambientes no productivos. | Cifrado en tránsito y reposo; ambientes no productivos con datos anonimizados. |
| Desarrollo | Controles dentro del ciclo de construcción. | Análisis de dependencias y de código en cada cambio; prueba de intrusión previa a producción. |
| Operación | Monitoreo, respuesta y evidencia. | Registros centralizados con retención de 12 meses; plan de respuesta con responsable designado. |

### Recomendaciones para profundizar

*Sección 7 · Seguridad*

1. **OWASP Top 10** — Recorra los diez riesgos y verifique cuáles aplican a su solución. Es la referencia citable por excelencia en seguridad de aplicaciones.
2. **Ley 21.719** — Lea la ley de protección de datos personales y liste las obligaciones que su solución debe cumplir desde el diseño.
3. **Confianza cero** — Investigue el modelo Zero Trust y compárelo con la VPN tradicional para el escenario de teletrabajo de su caso.
4. **Gestión de secretos** — Pruebe un almacén de secretos y elimine toda credencial que hoy esté escrita en un archivo de configuración.
5. **Modelado de amenazas** — Aplique el método STRIDE a un módulo de su solución y documente las tres amenazas más probables con su mitigación.

---

## Sección 8 · Identidad y sesión de usuarios

- Autenticación, autorización y sesión: tres preguntas distintas que se resuelven distinto
- Usuarios propios, directorio corporativo (LDAP / Active Directory) y proveedor de identidad
- Protocolos: SAML 2.0, OAuth 2.0 y OpenID Connect — para qué sirve cada uno
- Keycloak, Entra ID, Cognito, Auth0 y ClaveÚnica: alternativas y cuándo elegirlas
- Sesión en el servidor o token autocontenido (JWT): cookies, expiración y revocación
- HTTPS, doble factor y qué declarar en la oferta

### El inicio de sesión es arquitectura, no una pantalla

«El sistema tendrá login con usuario y contraseña» no es una decisión de arquitectura: es la ausencia de una. Detrás hay al menos seis decisiones con consecuencias técnicas y económicas.

| ¿Dónde viven los usuarios? | ¿Cómo se prueba quién es? | ¿Cómo se recuerda que ya entró? |
| --- | --- | --- |
| ¿En su base de datos, en el directorio del<br>mandante, en un proveedor externo, o en<br>varios a la vez? | Contraseña, doble factor, certificado, clave<br>del Estado. Cada opción tiene un costo y un<br>nivel de garantía. | Sesión en el servidor o token<br>autocontenido. Esta decisión condiciona el<br>balanceo y el escalamiento. |

| ¿Qué puede hacer una vez dentro? | ¿Cómo se cierra el acceso? | ¿Cuánto cuesta? |
| --- | --- | --- |
| Roles, permisos, y dónde se decide: en la<br>puerta de enlace o dentro de cada servicio. | Expiración, cierre de sesión, revocación y<br>desvinculación de la persona. Lo que más se<br>olvida. | Un producto de identidad se licencia por<br>usuario activo al mes, o se opera uno propio<br>con su servidor y su gente. |

> Si no puede responder esas seis preguntas con nombres concretos, su propuesta tiene un vacío justo en el componente que usan el 100% de los usuarios.

### Tres preguntas que no son la misma

| Identificación ¿Quién dice ser? | Autenticación ¿Puede probarlo? | Autorización ¿Qué puede hacer? |
| --- | --- | --- |
| El usuario declara una identidad: un<br>nombre de usuario, un correo, un RUT.<br>No prueba nada todavía.<br>Analogía: decir su nombre en el<br>mostrador. | Presenta algo que sólo él tiene o sabe:<br>contraseña, código temporal, llave física,<br>certificado.<br>El resultado es sí o no.<br>Analogía: mostrar el pasaporte. | Ya autenticado, qué recursos y<br>operaciones tiene permitidos.<br>Depende del rol, del contexto y del dato.<br>Analogía: la tarjeta de embarque dice a<br>qué avión sube y en qué asiento. |

> Y una cuarta, la que más se olvida: la SESIÓN. Autenticarse ocurre una vez; la sesión es lo que hace que el sistema siga sabiendo quién es usted en las siguientes doscientas peticiones, sin volver a pedirle la contraseña. Casi todos los problemas de seguridad de este bloque están en la sesión, no en el login.

### El vocabulario mínimo

| Credencial | Factor | Proveedor de identidad (IdP) | Aplicación cliente |
| --- | --- | --- | --- |
| Lo que se presenta para<br>probar la identidad:<br>contraseña, código,<br>certificado, huella. | Categoría de credencial: algo<br>que se sabe, algo que se tiene,<br>algo que se es. | El sistema que guarda los<br>usuarios y los autentica.<br>Keycloak, Entra ID, ClaveÚnica. | El sistema que confía en el<br>proveedor de identidad para<br>saber quién entró. |

| Directorio | Federación | Inicio de sesión único (SSO) | Token |
| --- | --- | --- | --- |
| Base de datos jerárquica de<br>personas, grupos y equipos de<br>una organización. LDAP y<br>Active Directory. | Acuerdo por el que una<br>aplicación acepta identidades<br>emitidas por otra<br>organización. | El usuario se autentica una vez<br>y entra a varios sistemas sin<br>repetir credenciales. | Credencial temporal emitida<br>tras autenticarse, que<br>acompaña cada petición<br>posterior. |

| Atributo o «claim» | Sesión | Alcance («scope») | Revocación |
| --- | --- | --- | --- |
| Dato que el proveedor afirma<br>sobre el usuario: correo, RUT,<br>rol, unidad. | El período durante el cual el<br>sistema recuerda al usuario<br>sin volver a pedirle<br>credenciales. | Porción de permisos que una<br>aplicación pide para actuar en<br>nombre del usuario. | Invalidar una credencial o una<br>sesión antes de que expire por<br>sí sola. |

### El flujo básico, paso a paso

Todo inicio de sesión tiene la misma forma. Lo que cambia entre alternativas es quién valida la credencial y qué se entrega después.

**1**

**El usuario pide un recurso protegido**

El sistema detecta que no hay sesión válida y lo redirige al inicio de sesión.

**2**

**Entrega sus credenciales por HTTPS**

Nunca por HTTP: sin cifrado, la contraseña viaja legible por la red.

**3**

**Alguien valida la credencial**

Su base de datos, el directorio del mandante o un proveedor de identidad externo.

**4**

**Se emite una sesión o un token**

Una cookie con identificador de sesión, o un token firmado con los datos del usuario.

**5**

**Cada petición siguiente lleva esa prueba**

El sistema la verifica y sabe quién es sin volver a pedir la contraseña.

**6**

**La sesión expira o se revoca**

Por tiempo, por inactividad, por cierre voluntario o porque un administrador la corta.

### Alternativa 1 · usuarios propios en su base de datos

El sistema guarda su propia tabla de usuarios y valida la contraseña contra ella. Es la opción más simple y la que más responsabilidad transfiere a su equipo.

| Cuándo tiene sentido | Lo que asume al elegirla |
| --- | --- |
| Portal público de clientes finales que no pertenecen a<br>ninguna organización.<br>El mandante no tiene directorio corporativo ni proveedor<br>de identidad.<br>Sistema pequeño, autocontenido, con un solo frente de<br>acceso.<br>No hay presupuesto para un producto de identidad y el<br>volumen de usuarios es bajo.<br>Se necesita registro autónomo: el usuario se crea la cuenta<br>solo. | Guardar bien las contraseñas es su responsabilidad, y<br>equivocarse es una brecha notificable.<br>Hay que construir registro, recuperación, bloqueo,<br>expiración y doble factor: no vienen gratis.<br>Sin inicio de sesión único: el usuario tendrá una contraseña<br>más que recordar.<br>Cuando alguien deja la organización, hay que acordarse de<br>desactivarlo en este sistema también.<br>Auditoría y cumplimiento quedan enteramente de su lado. |

> Estimación honesta: construir bien esta alternativa — registro, recuperación, bloqueo, doble factor, auditoría — cuesta varias semanas de desarrollo. Ese esfuerzo va en la carta Gantt y en el presupuesto.

### Cómo se guarda una contraseña

Una contraseña no se guarda: se guarda el resultado de una función que no se puede deshacer, calculada con una sal distinta para cada

**usuario.**

**Contraseña**

**+ sal única**

**Función lenta**

**Huella**

**escrita**

**por usuario**

**Argon2id / bcrypt**

**en la base**

| Regla | Por qué | Qué escribir en la oferta |
| --- | --- | --- |
| Nunca en texto claro ni cifrado reversible | Si el sistema puede recuperar la contraseña, un atacante también | «Las contraseñas se almacenan con Argon2id» |
| Función de derivación lenta y con costo ajustable | Argon2id, scrypt o bcrypt. MD5 y SHA-1 se rompen en segundos | Algoritmo y parámetros de costo declarados |
| Sal única por usuario | Impide resolver todas las contraseñas iguales de una vez | Generada aleatoriamente, guardada junto a la huella |
| Longitud sobre complejidad | Una frase larga es más fuerte y más memorable que «Abc123!» | Mínimo 12 caracteres, sin reglas de composición |
| Sin caducidad periódica obligatoria | Forzar cambios mensuales empeora las contraseñas elegidas | Cambio sólo ante sospecha de compromiso |

> Referencia citable: NIST SP 800-63B, Digital Identity Guidelines. Es la fuente que respalda «longitud sobre complejidad» y «sin caducidad obligatoria».

### Cómo se guarda una contraseña · continuación 1

| Regla | Por qué | Qué escribir en la oferta |
| --- | --- | --- |
| Contrastar con listas de contraseñas filtradas | El ataque más eficaz es probar contraseñas ya conocidas | Verificación contra listas públicas al registrar |
| Límite de intentos y retardo progresivo | Frena la prueba masiva sin bloquear cuentas legítimas para siempre | Política de bloqueo temporal declarada |

### Alternativa 2 · el directorio corporativo (LDAP)

LDAP — Protocolo Ligero de Acceso a Directorios — es la forma estándar de consultar un directorio de personas, grupos y equipos de una organización.

| Qué es un directorio | Cómo se nombra a alguien | Implementaciones |
| --- | --- | --- |
| Una base de datos jerárquica optimizada<br>para leer: personas, grupos, unidades<br>organizacionales y equipos, en forma de<br>árbol. | Con su nombre distinguido, la ruta completa<br>en el árbol:<br>cn=jperez, ou=Finanzas,<br>dc=empresa, dc=cl | Active Directory de Microsoft es la más<br>extendida en empresas y servicios públicos.<br>También OpenLDAP, 389 Directory Server y<br>Samba AD. |

| Puertos y cifrado | Grupos como roles | Lo que NO hace |
| --- | --- | --- |
| 389 sin cifrar y 636 para LDAPS. En una<br>oferta seria sólo se propone LDAPS o<br>StartTLS: nunca 389 en claro. | La pertenencia a grupos del directorio se<br>traduce en roles de la aplicación. Así el<br>mandante administra los accesos donde ya<br>lo hace. | No emite tokens, no da inicio de sesión<br>único entre aplicaciones web y no tiene<br>doble factor propio. Para eso hace falta una<br>capa encima. |

> Ventaja decisiva para la oferta: la aplicación no guarda ni una sola contraseña. Cuando el mandante desvincula a un funcionario, éste pierde el acceso al sistema sin que nadie tenga que hacer nada.

### Cómo autentica la aplicación contra LDAP

El truco es simple: la aplicación intenta conectarse al directorio usando las credenciales que escribió el usuario. Si el directorio la acepta, la contraseña es correcta.

**1**

El usuario escribe su nombre y contraseña en el formulario de la aplicación.

**2**

La aplicación se conecta al directorio con una cuenta de servicio de sólo lectura.

**3**

Busca a la persona por su nombre de usuario o correo y obtiene su nombre distinguido completo.

**4**

Intenta una nueva conexión con ese nombre distinguido y la contraseña escrita por el usuario.

**5**

Si el directorio acepta la conexión, la contraseña era correcta. Si la rechaza, no lo era.

**6**

La aplicación lee los grupos de la persona y los traduce a sus propios roles.

**7**

Recién ahora la aplicación crea su propia sesión local para el usuario.

Todo el diálogo viaja por LDAPS. La cuenta de servicio se guarda en el almacén de secretos, nunca en el código.

### LDAP · lo que hay que acordar con el mandante

| Punto a acordar | Qué preguntar | Riesgo si no se acuerda |
| --- | --- | --- |
| Servidor y disponibilidad | ¿Cuántos controladores de dominio hay y cuáles puede consultar el sistema? | Un solo servidor de directorio es punto único de falla del inicio de sesión |
| Cuenta de servicio | ¿Quién la crea, con qué permisos y cómo se rota la contraseña? | Se termina usando una cuenta de administrador, que es un hallazgo grave |
| Atributo de búsqueda | ¿Se busca por nombre de usuario, correo o RUT? ¿Es único? | Usuarios que no pueden entrar o, peor, que entran como otra persona |
| Grupos y roles | ¿Qué grupos existen y quién los administra? ¿Se crean grupos nuevos para el sistema? | El mandante no puede otorgar accesos sin llamar al proveedor |
| Red y puertos | ¿Hay conectividad desde donde corre el sistema hasta el directorio? ¿Puerto 636 abierto? | Si el sistema está en la nube, hay que resolver un túnel o un enlace privado |
| Certificado de LDAPS | ¿Quién lo emite y cuándo vence? ¿Es de una autoridad interna? | El día que vence el certificado, nadie puede iniciar sesión |
| Usuarios externos | Los clientes finales no están en el directorio: ¿dónde viven? | Hay que sostener dos mecanismos de identidad en paralelo |

> Los dos últimos puntos son los que más proyectos atrasan: el certificado que vence sin aviso y el descubrimiento tardío de que hay usuarios fuera del directorio.

### Alternativa 3 · un proveedor de identidad

La aplicación deja de preguntar contraseñas. Redirige al usuario a un proveedor de identidad, y confía en la

**respuesta firmada que recibe de vuelta.**

**Usuario**

**Su aplicación**

**Proveedor de identidad**

| con su navegador Usuario | (confía, no autentica) Su aplicación |
| --- | --- |
| 1. pide | 2. redirige |

| Lo que gana | Lo que entrega | Lo que cuesta | Lo que exige |
| --- | --- | --- | --- |
| Inicio de sesión único, doble<br>factor, políticas de contraseña,<br>auditoría y recuperación ya<br>construidos y mantenidos por<br>otro. | Una dependencia externa: si<br>el proveedor no está<br>disponible, nadie entra al<br>sistema. Hay que declararlo en<br>el análisis de riesgos. | Por usuario activo al mes en<br>los productos comerciales, o<br>el costo de operar un servidor<br>propio si elige uno libre. | Hablar un protocolo estándar:<br>OpenID Connect para<br>aplicaciones nuevas, SAML 2.0<br>cuando el mandante ya usa<br>ese lenguaje. |

> Este es el modelo detrás de «Iniciar sesión con Google», de ClaveÚnica del Estado de Chile y de cualquier portal corporativo con inicio de sesión único.

### SAML 2.0, OAuth 2.0 y OpenID Connect

Tres estándares que suenan parecido y resuelven cosas distintas. Confundirlos es el error de vocabulario más común en este tema.

|   | SAML 2.0 | OAuth 2.0 | OpenID Connect |
| --- | --- | --- | --- |
| Qué resuelve | Autenticación federada entre organizaciones | Autorización delegada: NO autentica | Autenticación sobre OAuth 2.0 |
| Pregunta que responde | ¿Quién es este usuario, según su organización? | ¿Puede esta aplicación actuar en nombre del usuario? | ¿Quién es este usuario, y con qué datos? |
| Formato | XML, con firma digital | Token opaco o JWT | Token de identidad en formato JWT |
| Año y madurez | 2005, muy maduro y muy extendido en el sector público | 2012, base de todo lo demás | 2014, es el estándar para aplicaciones nuevas |
| Dónde se usa | Portales corporativos, universidades, servicios del Estado | Acceso de aplicaciones a APIs de terceros | Aplicaciones web y móviles modernas, APIs propias |
| Complejidad | Alta: XML, firmas, metadatos | Media | Media, con buenas bibliotecas para todo lenguaje |
| Qué elegir hoy | Sólo si el mandante ya lo exige | Como base, junto con OpenID Connect | Opción por defecto para un sistema nuevo |

> OAuth 2.0 responde «¿qué puede hacer?»; OpenID Connect agrega «¿y quién es?». Usarlo solo para entrar es un error conocido.

### El flujo de OpenID Connect, en concreto

Flujo de código de autorización con PKCE: el recomendado hoy tanto para aplicaciones web como móviles.

**1**

La aplicación redirige el navegador al proveedor, con un código de verificación que sólo ella conoce.

**2**

El proveedor muestra su propia pantalla de inicio de sesión y pide doble factor si corresponde.

**3**

El usuario se autentica. Su contraseña nunca pasa por la aplicación.

**4**

El proveedor devuelve el navegador a la aplicación con un código de un solo uso, de vida muy corta.

**5**

La aplicación canjea ese código por tokens, desde su servidor y probando que es la misma que inició el flujo.

**6**

Recibe un token de identidad (quién es), uno de acceso (qué puede hacer) y uno de refresco (para renovar).

**7**

Verifica la firma del token contra las llaves públicas del proveedor y crea la sesión.

> Flujos que ya no se deben usar: el implícito y el de contraseña directa. Si los ve en un ejemplo de Internet, el ejemplo está desactualizado.

### Keycloak

Proveedor de identidad de código abierto, respaldado por Red Hat. Habla OpenID Connect y SAML 2.0, se instala en un contenedor y no tiene costo de licencia.

**Reinos («realms»)**

**Federación de usuarios**

**Intermediación de identidad**

Espacios de usuarios completamente

Se conecta al Active Directory o al LDAP del

Permite además entrar con Google,

separados. Uno para funcionarios y otro

mandante y usa esos usuarios sin copiarlos.

Microsoft o ClaveÚnica, y unifica todo en

para clientes externos, en el mismo

una sola identidad para la aplicación.

servidor.

**Doble factor incluido**

**Roles, grupos y políticas**

**Personalización visual**

Códigos temporales, correo, y llaves de

Administración de permisos desde una

Las pantallas de inicio de sesión se ajustan a

seguridad o passkeys mediante WebAuthn.

consola web, sin tocar la aplicación ni

la imagen del mandante mediante plantillas.

Configurable por rol.

desplegar de nuevo.

| Lo que hay que cotizar igual | Detalle |
| --- | --- |
| Infraestructura | Al menos dos instancias tras un balanceador, más una base de datos PostgreSQL propia |
| Operación | Actualizaciones, respaldo del reino, monitoreo y certificados: es un sistema crítico más que operar |
| Puesta en marcha | Configuración de reinos, clientes, roles, federación y plantillas: semanas de trabajo, no horas |

**Soporte**

Opcional, con Red Hat build of Keycloak, si el mandante exige respaldo formal de un fabricante

### Alternativas de producto, comparadas

| Producto | Tipo | Modelo de costo | Fortaleza | Cuándo elegirlo |
| --- | --- | --- | --- | --- |
| Keycloak | Libre | Sin licencia; costo de operar | Completo, sin ataduras, se instala donde sea | On-premise o nube, sin presupuesto de licencias |
| Microsoft Entra ID | Servicio | Por usuario al mes, por niveles | Integración total con Microsoft 365 y Windows | El mandante ya vive en el ecosistema Microsoft |
| Auth0 / Okta | Servicio | Por usuario activo al mes | Muy rápido de implementar, excelente documentación | Startups y proyectos con plazo corto |
| Amazon Cognito | Servicio | Por usuario activo al mes, con capa gratuita | Integrado con el resto de AWS | La solución ya corre en AWS |
| Azure AD B2C / Entra External ID | Servicio | Por autenticación mensual | Pensado para clientes finales, no funcionarios | Portal público sobre Azure |
| Zitadel / Authentik / FusionAuth | Libre o mixto | Sin licencia o por volumen | Más livianos que Keycloak, despliegue simple | Equipos pequeños que quieren autoalojar |
| ClaveÚnica (Chile) | Estatal | Sin costo para el organismo | Identidad del Estado, ya la tiene el ciudadano | Trámites y servicios públicos a personas naturales |

> ClaveÚnica se integra mediante OpenID Connect y requiere solicitar la incorporación del servicio ante la División de Gobierno Digital: es un trámite con plazo, y ese plazo va en la carta Gantt.

### Cómo conviven varias fuentes de identidad

Casi ningún caso tiene una sola fuente de usuarios. El patrón correcto es un intermediario: la aplicación habla con uno solo, y ése habla con todos.

**SU APLICACIÓN**

**habla un solo protocolo: OpenID Connect**

**PROVEEDOR DE IDENTIDAD / INTERMEDIARIO**

**Keycloak, Entra ID o equivalente**

**Directorio corporativo**

**ClaveÚnica**

**Usuarios propios**

**Google / Microsoft**

| LDAP / Active Directory Directorio corporativo | OpenID Connect Keycloak, Entra ID o equivalente ClaveÚnica | base de datos del sistema Usuarios propios | identidad social o corporativa Google / Microsoft |
| --- | --- | --- | --- |
| Funcionarios del mandante | Ciudadanos y clientes finales | Proveedores y externos sin directorio | Colaboradores ocasionales |

> Beneficio de diseño: si mañana el mandante cambia de directorio o incorpora una fuente nueva, se ajusta el intermediario y la aplicación no se toca. Sin este patrón, cada fuente nueva es un desarrollo.

### La sesión: las dos familias

Autenticarse ocurre una vez. La sesión es lo que sostiene las siguientes doscientas peticiones. Hay dos maneras de hacerlo, y eligen cosas distintas.

| Sesión en el servidor (cookie con identificador) | Token autocontenido (JWT firmado) |
| --- | --- |
| El servidor guarda el estado de la sesión y le entrega al navegador<br>una cookie con un identificador opaco, sin significado.<br>En cada petición busca ese identificador en su almacén y recupera<br>quién es el usuario.<br>El almacén suele ser Redis o la base de datos. | El servidor entrega un token que lleva dentro los datos del usuario,<br>firmado digitalmente.<br>En cada petición verifica la firma: no necesita consultar nada ni<br>recordar nada.<br>Es el modelo natural de las APIs y los microservicios. |

> Consecuencia física directa: con sesión en el servidor y varios nodos, o fija al usuario a un nodo — y pierde balanceo — o monta un almacén compartido, que es un componente más que cotizar y del que hay que asegurar la disponibilidad.

### Sesión en servidor o token: cuál elegir

| Criterio | Sesión en el servidor | Token autocontenido (JWT) |
| --- | --- | --- |
| Dónde vive el estado | En el servidor o en un almacén compartido | En el propio token, en el cliente |
| Revocación inmediata | Trivial: se borra del almacén | Difícil: el token vale hasta que expira |
| Escalado horizontal | Requiere almacén compartido o sesión fija | Natural: cualquier nodo lo valida solo |
| Tamaño en cada petición | Pequeño: sólo un identificador | Mayor: viaja el contenido completo en cada llamada |
| Entre dominios y móviles | Incómodo: depende de cookies y dominios | Natural: es sólo una cabecera |
| Microservicios | Cada servicio debe consultar el almacén | Cada servicio verifica la firma sin consultar a nadie |
| Riesgo principal | Que el almacén de sesiones se caiga o se sature | Que un token robado sirva hasta que expire |
| Cuándo conviene | Portal web clásico, un solo frente, necesidad de corte inmediato | APIs, aplicaciones móviles, microservicios, varios frentes |

> La solución habitual es mixta: token de acceso de vida muy corta — cinco a quince minutos — más un token de refresco revocable. Se obtiene el escalado del token y el control de la sesión en servidor.

### Anatomía de un token JWT

Un JWT son tres partes separadas por puntos, codificadas en base64. Codificado no es cifrado: cualquiera puede leer su contenido.

**ENCABEZADO**

Algoritmo de firma y qué llave se usó

{ "alg": "RS256", "kid": "a3f..." }

{ "sub": "12345",

**CONTENIDO**

Los datos que el proveedor afirma del usuario "roles": ["auditor"],

"exp": 1735689600 }

**FIRMA**

Prueba criptográfica de que nadie lo modificó Calculada por el proveedor con su llave privada

| Regla de uso | Por qué |
| --- | --- |
| Nunca poner datos sensibles dentro | El contenido es legible por cualquiera que tenga el token |
| Expiración corta en el token de acceso | Es la única defensa real si el token es robado: entre 5 y 15 minutos |
| Firma asimétrica en sistemas distribuidos | Los servicios validan con la llave pública y no emiten tokens falsos |
| Verificar emisor, destinatario y expiración | Una firma válida no basta: hay que comprobar que el token era para usted |
| Rotación de llaves publicada | El proveedor publica sus llaves públicas y las rota sin romper a nadie |

### Token de acceso y token de refresco

Dos tokens con vidas distintas: uno corto para trabajar y uno largo y revocable para renovarlo sin molestar al usuario.

| Token de acceso | Token de refresco |
| --- | --- |
| Vida muy corta: de 5 a 15 minutos.<br>Acompaña cada petición a la API, en la cabecera de<br>autorización.<br>No se puede revocar: por eso dura poco.<br>Contiene los permisos: el servicio lo verifica sin consultar<br>a nadie.<br>Si se filtra, el daño está acotado a esa ventana de<br>minutos. | Vida larga: horas o días, según la política de sesión.<br>Sólo se usa contra el proveedor de identidad, nunca<br>contra la API.<br>Se guarda en el servidor o en una cookie HttpOnly,<br>nunca en el almacenamiento del navegador.<br>Es revocable: cerrar sesión o desvincular a alguien lo<br>invalida de inmediato.<br>Rotación: cada uso emite uno nuevo y anula el anterior.<br>Detección de reutilización: si se usa uno ya canjeado, se<br>anula toda la cadena de sesión. |

> En su oferta escriba los dos números: duración del token de acceso y duración de la sesión. Son dos parámetros que el mandante puede exigir y que se revisan en una auditoría.

### La cookie de sesión y sus marcas

La cookie que transporta la sesión debe llevar marcas explícitas. Cada una desactiva un ataque conocido.

| Marca | Qué hace | Ataque que evita |
| --- | --- | --- |
| Secure | La cookie sólo viaja por HTTPS | Robo de la sesión leyendo tráfico sin cifrar en una red pública |
| HttpOnly | El código JavaScript de la página no puede leerla | Robo del token mediante inyección de scripts en la página |
| SameSite=Lax o Strict | No se envía cuando la petición viene desde otro sitio | Peticiones falsificadas desde un sitio malicioso |
| Domain y Path acotados | Limita a qué servidores y rutas se envía | Exposición innecesaria de la sesión a subdominios de terceros |
| Max-Age o Expires | Fija cuándo caduca sola | Sesiones eternas en equipos compartidos |
| Prefijo __Host- | Obliga a Secure, sin Domain y con Path raíz | Que un subdominio comprometido escriba cookies para el dominio principal |
| Renovar el identificador al iniciar sesión | Se descarta el identificador previo y se emite uno nuevo | Fijación de sesión: que el atacante imponga un identificador conocido |

> Patrón recomendado hoy para aplicaciones de página única: el token nunca llega al navegador. Un intermediario propio — el patrón «servidor para el frontend» — lo guarda del lado del servidor y entrega sólo una cookie HttpOnly.

### Cerrar sesión de verdad

Cerrar sesión no es borrar la cookie del navegador. Hay tres cierres distintos, y una arquitectura seria los distingue.

**Cierre local**

**Cierre en el proveedor**

**Cierre único global**

Se borra la cookie o el token del dispositivo.

Se avisa al proveedor de identidad, que

El proveedor avisa a todas las aplicaciones

termina la sesión central.

donde el usuario tenía sesión abierta, para

El usuario deja de estar autenticado en esa

que la cierren también.

aplicación y en ese equipo.

Sin esto, volver a entrar es instantáneo: el proveedor lo reconoce y no vuelve a pedir

Es lo que exige un entorno con inicio de

Es lo mínimo, y es lo único que hacen

nada.

sesión único real.

muchos sistemas.

| Situación | Qué debe pasar |
| --- | --- |
| El usuario cierra sesión | Se anula el token de refresco y la sesión del proveedor; el de acceso caduca solo en minutos |
| Un administrador desvincula a una persona | Se anulan todas sus sesiones activas en todos los dispositivos, de inmediato |
| Se detecta un robo de credenciales | Anulación masiva de sesiones y cambio forzado de contraseña |
| El usuario cambia su contraseña | Todas las sesiones anteriores se invalidan, salvo la actual |

### HTTPS: el requisito previo de todo lo anterior

Todo lo anterior asume que el canal está cifrado. Sin HTTPS, la contraseña, la cookie y el token viajan legibles por la red.

**Qué es**

**El certificado**

**Dónde termina el cifrado**

HTTP dentro de un canal cifrado con TLS.

Prueba que el servidor es quien dice ser. Lo

Normalmente en el balanceador o en el

Hoy corresponde usar TLS 1.2 como mínimo

emite una autoridad certificadora, tiene

WAF. Desde ahí hacia adentro conviene

y preferir TLS 1.3.

fecha de vencimiento y hay que renovarlo.

volver a cifrar: es la práctica de confianza cero.

**HSTS**

**Redirección obligatoria**

**Entre servicios**

Cabecera que le dice al navegador que

Todo lo que llegue por el puerto 80 se

TLS mutuo: además del servidor, el cliente

jamás use HTTP con ese dominio. Evita el

redirige a 443. No debe existir ninguna ruta

presenta certificado. Es la forma de que un

primer salto sin cifrar.

accesible sin cifrar.

servicio pruebe su identidad a otro.

| Decisión de la oferta | Alternativas | Costo típico |
| --- | --- | --- |
| Emisor del certificado | Let's Encrypt automatizado · autoridad comercial · autoridad interna del mandante | Desde sin costo hasta cientos de dólares al año |
| Alcance | Un dominio · comodín para todos los subdominios · varios dominios | Aumenta con el alcance |
| Renovación | Automática mediante ACME, o manual con recordatorio en calendario | El certificado vencido es una de las caídas más frecuentes y más evitables |

### Doble factor: no todos valen lo mismo

Un segundo factor multiplica la seguridad del inicio de sesión. Pero hay una diferencia enorme entre unos y otros.

| Factor | Cómo funciona | Fortaleza | Debilidad | Costo |
| --- | --- | --- | --- | --- |
| Código por SMS | Se envía un número de seis dígitos al teléfono | Baja | Suplantación de la línea telefónica y reenvío por engaño | Por mensaje enviado: puede ser significativo |
| Código por correo | El mismo mecanismo, pero al correo del usuario | Baja | Si el correo está comprometido, el factor no aporta nada | Casi nulo |
| Aplicación de códigos temporales | Una aplicación genera un código que cambia cada 30 segundos | Media-alta | Todavía se puede pedir por engaño en un sitio falso | Sin costo |
| Notificación con número | Llega un aviso al teléfono y hay que confirmar un número mostrado en pantalla | Alta | Requiere una aplicación instalada y gestionada | Incluido en los productos de identidad |
| Llave de seguridad o passkey | Criptografía ligada al dominio del sitio: huella, rostro o llave física | Muy alta | Recuperación si el usuario pierde el dispositivo | Sin costo con passkeys; la llave física cuesta |

> Las llaves de seguridad y las passkeys son las únicas resistentes al engaño: están ligadas al dominio real y no funcionan en un sitio falso, aunque el usuario caiga.

### Autorización: dónde se decide qué puede hacer

**Por rol (RBAC)**

**Por atributos (ABAC)**

**Por relación**

**Alcances de la API**

Los permisos se asignan a

La decisión considera

«Puede ver este expediente

Cuando una aplicación actúa

roles y los roles a personas.

atributos: unidad del

porque es el abogado

en nombre del usuario, el

Simple, entendible y suficiente

funcionario, monto de la

asignado». Se decide sobre el

token limita qué porción de la

para la mayoría de los casos

operación, horario, canal de

dato concreto, no sobre el

API puede tocar.

del curso.

acceso.

tipo de dato.

**Dónde se aplica cada control:**

| Punto de control | Qué decide ahí | Qué NO debe decidir ahí |
| --- | --- | --- |
| Interfaz de usuario | Qué menús y botones se muestran | Nada de seguridad: es sólo comodidad, el cliente se puede manipular |
| Puerta de enlace de API | Que el token sea válido, no haya expirado y el rol tenga acceso al recurso | Reglas que dependen del dato concreto que se está pidiendo |
| Servicio de negocio | Si este usuario puede hacer esta operación sobre este registro en particular | Nada: aquí es donde la decisión es definitiva |
| Base de datos | Aislamiento entre inquilinos y cifrado de columnas sensibles | Lógica de permisos de negocio, que quedaría invisible y duplicada |

> Control de acceso roto es la vulnerabilidad número uno del OWASP Top 10. Casi siempre por confiar en una validación que sólo estaba en el navegador.

### Identidad de los sistemas, no sólo de las personas

Cuando el sistema de facturación llama a la API de pagos no hay ninguna persona escribiendo una contraseña. Esa llamada también necesita identidad.

| Mecanismo | Cómo funciona | Nivel | Cuándo usarlo |
| --- | --- | --- | --- |
| Llave de API | Una cadena secreta fija que acompaña cada llamada | Bajo | Integraciones simples de bajo riesgo; nunca para datos sensibles |
| Credenciales de cliente (OAuth 2.0) | El sistema pide un token al proveedor con su identificador y su secreto | Bueno | Estándar para llamadas entre sistemas propios y con terceros |
| TLS mutuo | Cada extremo presenta su certificado y ambos se verifican | Muy alto | Integraciones bancarias, salud, tráfico interno entre servicios |
| Identidad de carga de trabajo | La plataforma emite la identidad al contenedor; no hay secreto que guardar | Muy alto | Servicios en la nube o en Kubernetes que llaman a otros servicios |
| Usuario y contraseña compartidos | Una cuenta genérica usada por varios sistemas y personas | Inaceptable | Nunca: rompe la trazabilidad y nadie se atreve a rotarla |

> Regla transversal: ningún secreto vive en el código ni en el repositorio. Van a un almacén de secretos — Vault, Key Vault, Secrets Manager — con rotación programada y acceso auditado. Es un componente del diagrama y una línea del presupuesto.

### Los errores que el evaluador busca

**1**

**2**

| Contraseñas mal guardadas 1 | Sin HTTPS en alguna ruta 2 |
| --- | --- |
| Texto claro, cifrado reversible o funciones rápidas como MD5. Es la falla<br>más grave y la más fácil de detectar.<br>3 | Basta una página de inicio de sesión accesible por HTTP para que todo<br>el esquema pierda sentido.<br>4 |

| Token en el almacenamiento del navegador 3 | Sesiones sin expiración 4 |
| --- | --- |
| Cualquier script inyectado en la página puede leerlo. Va en cookie con<br>marca HttpOnly.<br>5 | Un usuario que nunca cierra sesión y un equipo compartido son una<br>combinación previsible.<br>6 |

| Permisos sólo en el frontend 5 | Identificadores predecibles 6 |
| --- | --- |
| El botón oculto no protege nada. La API tiene que negar la operación<br>por sí sola. | Cambiar el número en la dirección y ver el registro de otra persona. Es<br>el hallazgo clásico. |

### Los errores que el evaluador busca · continuación 1

**7**

**8**

| Un solo rol «administrador» 7 | Sin registro de accesos 8 |
| --- | --- |
| Sin granularidad no hay mínimo privilegio, y toda la operación termina<br>usando la cuenta más poderosa.<br>9 | Si nadie puede reconstruir quién entró y qué hizo, no hay auditoría<br>posible ni respuesta a incidentes.<br>10 |

| Doble factor sólo opcional 9 | Sin proceso de desvinculación 10 |
| --- | --- |
| Debe ser obligatorio para administradores y para todo acceso desde<br>fuera de la red del mandante. | Cuentas activas de personas que ya no trabajan ahí. Se detecta en la<br>primera auditoría. |

### Cómo elegir para su caso

| Si su caso es… | Fuente de identidad | Sesión | Doble factor |
| --- | --- | --- | --- |
| Sistema interno para funcionarios de una organización con directorio | LDAP / Active Directory, mediante un proveedor de identidad | Sesión en el servidor o token corto | Obligatorio fuera de la red interna |
| Portal público para ciudadanos, sector público chileno | ClaveÚnica mediante OpenID Connect | Token corto con refresco | Lo aporta ClaveÚnica |
| Portal de clientes de una empresa privada | Usuarios propios o servicio de identidad para clientes | Token corto con refresco | Opcional, obligatorio para operaciones sensibles |
| Solución mixta: funcionarios y clientes externos | Proveedor de identidad con dos reinos separados | Token, con políticas distintas por reino | Obligatorio para funcionarios |
| API para integrarse con sistemas de terceros | Credenciales de cliente OAuth 2.0 o TLS mutuo | Token de acceso, sin sesión | No aplica: es identidad de máquina |
| Aplicación móvil | OpenID Connect con código de autorización y PKCE | Token corto con refresco rotatorio | Biometría del dispositivo como segundo factor |

> Ninguna fila es obligatoria: es un punto de partida. Lo que el evaluador exige es que la elección esté justificada con el tipo de usuario y el nivel de riesgo del caso.

### Qué declarar en la oferta

**Elemento**

**Qué escribir**

**Dónde impacta**

| Fuente de identidad | Nombre del producto o servicio, y de dónde salen los usuarios | Diagrama lógico y físico; licencias |
| --- | --- | --- |
|   |   |   |
| Protocolo | OpenID Connect, SAML 2.0 o autenticación directa contra LDAP | Esfuerzo de desarrollo e integración |
| Almacenamiento de contraseñas | Si aplica: algoritmo y parámetros; o bien «el sistema no almacena contraseñas» | Cumplimiento y seguridad |
| Mecanismo de sesión | Sesión en el servidor o token, con la duración de cada uno en minutos | Arquitectura física: almacén compartido o balanceo libre |
| Segundo factor | Qué factor, para qué perfiles y en qué circunstancias es obligatorio | Costo por mensaje o por licencia; experiencia de usuario |
| Modelo de roles | Lista de roles previstos y quién los administra después de la puesta en marcha | Alcance funcional y capacitación |
| Certificados | Emisor, alcance, mecanismo de renovación y responsable | Operación y riesgo de indisponibilidad |
| Ciclo de vida de cuentas | Alta, modificación, desvinculación y recertificación periódica | Procedimientos de operación |
| Registro de auditoría | Qué eventos se registran, dónde se guardan y por cuánto tiempo | Almacenamiento y cumplimiento normativo |
| Costo del componente | Licencias por usuario, infraestructura del proveedor y esfuerzo de integración | Directamente al flujo de caja |

> Estas diez filas son media página del informe y suelen valer más que tres páginas describiendo pantallas.

### Recomendaciones para profundizar

*Sección 8 · Identidad y sesión de usuarios*

1. **OpenID Connect en la práctica** — Levante Keycloak en un contenedor, cree un reino y conecte una aplicación de ejemplo. Observe los tokens que emite.
2. **Anatomía de un token** — Tome un JWT real de una sesión suya y decodifíquelo. Identifique emisor, destinatario, expiración y roles.
3. **Directorios LDAP** — Revise la estructura de un árbol LDAP y la diferencia entre buscar y «atarse». Pruebe con un servidor de ejemplo. Lea la documentación de integración de la División de Gobierno Digital y estime el plazo del trámite de incorporación. Lea el capítulo de contraseñas: es la fuente que respalda «longitud sobre complejidad» y la ausencia de caducidad obligatoria. Revise las categorías de control de acceso roto y de fallas de identificación y autenticación, con sus ejemplos.

---

## Sección 9 · Entrega

- Por qué se necesitan varios ambientes y qué hace cada uno
- Desarrollo, QA, preproducción y producción: propósito, datos y dimensionamiento
- Qué es CI/CD y cómo se ve una canalización completa
- Cómo montar el ambiente de integración y entrega continua, paso a paso
- Estrategias de despliegue y qué comprometer en la oferta

### Por qué varios ambientes

Un ambiente es una instalación completa de la solución — aplicación, base de datos y configuración — destinada a un propósito específico. Separarlos no es un lujo: es la única forma de cambiar sin romper.

| Aislar el riesgo | Probar de verdad | Validar con el mandante |
| --- | --- | --- |
| Un error en desarrollo no puede afectar al<br>usuario final. Sin separación, cada prueba<br>es un riesgo para la operación. | Las pruebas necesitan un lugar donde se<br>pueda romper todo, borrar datos y volver<br>a empezar. | La contraparte necesita ver y aprobar la<br>funcionalidad antes de que llegue a<br>producción. |

| Verificar el despliegue | Separar responsabilidades | Cumplir la normativa |
| --- | --- | --- |
| El procedimiento de instalación se ensaya<br>varias veces antes de ejecutarlo en<br>producción. | Quien desarrolla no debería poder<br>modificar producción por su cuenta. Es un<br>control de auditoría. | Los datos personales de producción no<br>pueden circular libremente por los<br>ambientes de prueba. |

### Los cuatro ambientes

|   | DESARROLLO | QA / PRUEBAS | PREPRODUCCIÓN | PRODUCCIÓN |
| --- | --- | --- | --- | --- |
| Para qué existe | Construir y probar mientras se programa | Verificar que lo construido cumple los requisitos | Ensayar el despliegue y validar con el mandante | Dar el servicio real |
| Quién lo usa | Equipo de desarrollo | Equipo de pruebas y de calidad | Mandante y equipo de operaciones | Usuarios finales |
| Datos | Sintéticos o mínimos | Sintéticos, con casos de prueba diseñados | Copia anonimizada de producción | Reales |
| Tamaño respecto de producción | 10% a 20% | 20% a 30% | Idéntico en configuración, menor en cantidad | 100% |
| Disponibilidad | Horario hábil; se puede apagar de noche | Horario hábil | Cuando se necesita, más las ventanas de ensayo | La comprometida en el SLA |
| Quién despliega | Automático en cada cambio | Automático al aprobar | Automático con aprobación | Automático con aprobación formal |
| Frecuencia de despliegue | Varias veces al día | Diaria | Semanal o por hito | Según el plan de liberación |
| Monitoreo | Básico | Básico | Igual que producción, para validar el comportamiento | Completo, con alertas y turno |

### Cuánto cuestan los ambientes

Los ambientes no productivos suelen sumar entre un 30% y un 50% del gasto de infraestructura. Si no están en

**el presupuesto, aparecen igual — como sobrecosto.**

| Ambiente | Proporción del gasto de producción | Cómo se reduce |
| --- | --- | --- |
| Desarrollo | 10% – 20% | Instancias pequeñas; apagado automático fuera de horario hábil (ahorra hasta 65%) |
| QA / Pruebas | 20% – 30% | Se levanta bajo demanda para la campaña de pruebas y se destruye al terminar |
| Preproducción | 30% – 50% | Misma configuración que producción pero con menos nodos; se enciende para el ensayo del despliegue |
| Producción | 100% (referencia) | Autoescalado y capacidad reservada para la carga base |

**Ambientes efímeros**

**Apagado programado**

**Etiquetado por ambiente**

Levantar el ambiente completo con

Desarrollo y QA apagados de 20:00 a 8:00 y

Cada recurso etiquetado con su ambiente

infraestructura como código para una

los fines de semana: son unas 128 horas de

permite saber cuánto cuesta cada uno y

prueba y destruirlo después. Se paga sólo lo

las 168 de la semana.

decidir dónde recortar.

usado.

### Datos en ambientes no productivos

Copiar la base de producción a QA «para probar con datos reales» es la práctica más extendida y una de las más

**riesgosas.**

| Por qué es un problema | Qué hacer en cambio |
| --- | --- |
| Multiplica los lugares donde viven los datos personales.<br>Los ambientes no productivos tienen menos controles,<br>menos monitoreo y más gente con acceso.<br>Es un tratamiento de datos sin la base legal que lo<br>justifique.<br>Ante una fuga, el incidente y la notificación son igual de<br>obligatorios. | Datos sintéticos generados a partir del modelo, para<br>desarrollo y QA.<br>Copia anonimizada o seudonimizada para<br>preproducción, cuando se necesita volumen realista.<br>Subconjuntos: un 5% de los registros suele bastar para<br>probar.<br>Si se debe usar una copia, cifrada, con acceso restringido<br>y con fecha de eliminación. |

> Compromiso concreto para la oferta: «los ambientes no productivos operan con datos anonimizados; ningún dato personal identificable sale de producción». Es barato, es verificable y responde directamente al criterio de restricciones legales.

### La promoción entre ambientes

Principio fundamental: se construye una sola vez y ese mismo artefacto se promueve. Lo que cambia entre

**ambientes es la configuración, nunca el código.**

| DESARROLLO | QA | PREPRODUCCIÓN | PRODUCCIÓN |
| --- | --- | --- | --- |
| Compila, pasan las pruebas unitarias Pasan las<br>y el análisis de código integración<br>criterio | pruebas funcionales, de<br>y de regresión<br>de salida de cada ambiente: si | El mandante valida, se ensaya el<br>despliegue y se prueba el<br>acordada<br>rendimiento<br>no se cumple, no se promueve | Aprobación formal, ventana<br>y plan de reversión listo |

| Un solo artefacto | Configuración externa | Reversión preparada |
| --- | --- | --- |
| La misma imagen o paquete que pasó QA es<br>la que llega a producción. Recompilar para<br>producción invalida todas las pruebas. | Direcciones, credenciales y parámetros<br>vienen del ambiente, no del paquete. Un<br>mismo artefacto, cuatro configuraciones. | Antes de desplegar hay que saber cómo<br>volver atrás: versión anterior disponible y<br>procedimiento probado. |

### Qué es CI/CD

Es la automatización del camino que va desde que alguien escribe una línea de código hasta que esa línea está funcionando para el usuario.

| CI · Integración continua | CD · Entrega continua | CD · Despliegue continuo |
| --- | --- | --- |
| Cada cambio se integra al código común y<br>se verifica automáticamente: compila,<br>pasan las pruebas, se analiza la calidad y la<br>seguridad.<br>Objetivo: que un error se detecte en<br>minutos y no en la etapa de pruebas.<br>Es el piso mínimo. Todo proyecto debería<br>tenerlo. | Todo cambio que pasó las verificaciones<br>queda listo para desplegarse, con un<br>artefacto versionado y un procedimiento<br>automatizado.<br>El paso a producción existe, pero lo autoriza<br>una persona.<br>Objetivo: que publicar deje de ser un evento<br>riesgoso. | Todo cambio que pasa las verificaciones<br>llega a producción de forma automática, sin<br>intervención humana.<br>Exige una batería de pruebas muy sólida y<br>despliegue progresivo con reversión<br>automática.<br>Raramente apropiado en un proyecto con<br>contrato y ventanas de cambio. |

> Para su oferta, lo razonable es comprometer integración continua y entrega continua hasta preproducción, con aprobación formal para el paso a producción.

### Anatomía de una canalización

**INTEGRACIÓN CONTINUA · ocurre con cada cambio, en minutos**

| Compilación | Análisis de código y dependencias |
| --- | --- |
| ENTREGA CONTINUA · el mismo artefacto recorre los ambientes |   |

| Despliegue en QA | Aprobación formal | Despliegue en PRODUCCIÓN versionado Artefacto |
| --- | --- | --- |
| en cualquier etapa que falle, la canalización se detiene y avisa: nada avanza a medias |   |   |

| Todo queda registrado en DESARROLLO Cambio en el repositorio Despliegue | Reversión en un paso | El despliegue deja de dar miedo |
| --- | --- | --- |
| Quién hizo el cambio, qué pruebas pasó,<br>quién aprobó y a qué hora se desplegó. Es<br>trazabilidad de auditoría, gratis. | Si el despliegue sale mal, se vuelve a la<br>versión anterior con el mismo mecanismo,<br>en minutos. | Cuando publicar es un procedimiento<br>automático y ensayado, se publica seguido y<br>en cambios pequeños: menos riesgo por<br>vez. |

### Cómo montar el ambiente de CI/CD

Ocho pasos, en orden. Los cuatro primeros se hacen en días y ya entregan la mayor parte del beneficio.

**1**

**2**

**3**

**4**

| Repositorio y estrategia de ramas 1 | Servidor de canalización 2 | Construcción automatizada 3 | Pruebas en la canalización 4 |
| --- | --- | --- | --- |
| Un repositorio por<br>componente, con una rama<br>principal siempre desplegable<br>y ramas cortas por cambio.<br>Nadie escribe directo en la<br>principal.<br>5 | El servicio que ejecuta la<br>automatización, integrado al<br>repositorio. Puede ser el del<br>propio proveedor del<br>repositorio.<br>6 | Un comando único que<br>compila y produce el artefacto<br>imagen de contenedor o<br>paquete — de forma<br>reproducible.<br>7 | Unitarias siempre; de<br>integración sobre servicios<br>simulados; un umbral mínimo<br>de cobertura acordado con el<br>equipo.<br>8 |

| Análisis de calidad y seguridad 5 | Almacén de artefactos 6 | Infraestructura como código 7 | Despliegue automatizado con aprobación 8 |
| --- | --- | --- | --- |
| Revisión estática del código,<br>análisis de dependencias con<br>vulnerabilidades conocidas y<br>escaneo de la imagen. | Registro privado donde se<br>publica cada artefacto con su<br>versión inmutable. Es la<br>fuente de lo que se despliega. | Los ambientes se describen en<br>archivos versionados, de<br>modo que DEV, QA, PREPROD<br>y PROD sean iguales salvo en<br>tamaño. | Un mismo procedimiento para<br>los cuatro ambientes, con<br>compuerta de aprobación<br>antes de producción y<br>reversión preparada. |

### Estrategias de despliegue

| Estrategia | Cómo funciona | Interrupción | Costo | Cuándo usarla |
| --- | --- | --- | --- | --- |
| Recrear | Se detiene la versión antigua y se levanta la nueva. | Sí, hay corte | Mínimo | Sistemas internos con ventana acordada |
| Progresivo (rolling) | Se reemplazan las instancias de a poco, unas pocas por vez. | No | Bajo | El caso general; por defecto en el orquestador |
| Azul – verde | Se levanta el entorno nuevo completo en paralelo y se conmuta el tráfico. | No | Alto: doble infraestructura | Cambios grandes con reversión en segundos |
| Canario | Recibe una fracción del tráfico y se amplía si las métricas se mantienen. | No | Medio | Servicios de alto volumen y cambios de riesgo |
| Interruptores de función | El código nuevo se despliega apagado y se enciende por configuración. | No | Bajo | Para separar despliegue y puesta en marcha |

> En la oferta, declarar la estrategia elegida y el tiempo de reversión es lo que convierte «desplegaremos sin interrupción» en un compromiso verificable.

### Configuración y secretos por ambiente

El mismo artefacto en cuatro ambientes significa que todo lo que cambia entre ellos vive fuera del artefacto.

| Configuración por ambiente | Secretos aparte | Credenciales distintas |
| --- | --- | --- |
| Direcciones, tamaños, umbrales y<br>parámetros de negocio, versionados en el<br>repositorio de configuración — nunca dentro<br>del código. | Contraseñas, llaves y certificados en un<br>almacén de secretos, inyectados en el<br>arranque, con acceso auditado y rotación<br>definida. | Cada ambiente tiene sus propias<br>credenciales. Si QA usa las de producción,<br>un error en QA es un error en producción. |

| Separación de red | Nada de secretos en el repositorio | Terceros en modo prueba |
| --- | --- | --- |
| El ambiente de QA no debe poder alcanzar<br>la base de datos de producción. Es una regla<br>de firewall, no una promesa. | Análisis automático que rechaza el cambio<br>si detecta una credencial. Una llave<br>publicada por error se considera<br>comprometida. | Los ambientes no productivos apuntan a los<br>sandbox de los proveedores externos, jamás<br>a sus interfaces productivas. |

> Incidente clásico: el ambiente de pruebas apuntando a la base de datos de producción. Ocurre por configuración compartida y termina con datos reales modificados por una prueba automatizada.

### Qué comprometer en la oferta

| Compromiso | Redacción tipo | Qué demuestra |
| --- | --- | --- |
| Ambientes | Cuatro ambientes: desarrollo, QA, preproducción y producción, aprovisionados como código. | Que el proyecto tiene disciplina de entrega y que los ambientes están costeados. |
| Datos no productivos | Los ambientes no productivos operan con datos anonimizados o sintéticos. | Cumplimiento normativo y control del riesgo de fuga. |
| Integración continua | Cada cambio se compila, se prueba y se analiza automáticamente antes de integrarse. | Calidad verificable y detección temprana de defectos. |
| Cobertura de pruebas | Umbral mínimo de cobertura acordado, verificado en la canalización. | Un compromiso de calidad medible, no una declaración de intenciones. |
| Despliegue | Procedimiento automatizado e idéntico para los cuatro ambientes, con aprobación formal para producción. | Que el paso a producción es repetible y auditable. |
| Reversión | Estrategia progresiva con reversión a la versión anterior en menos de N minutos. | Que un despliegue fallido no se transforma en una caída prolongada. |
| Trazabilidad | Registro de qué se desplegó, quién lo aprobó y cuándo, conservado durante todo el contrato. | Evidencia de auditoría y control de cambios. |
| Métricas de entrega | Informe periódico de frecuencia de despliegue, tiempo de entrega, tasa de fallo y tiempo de recuperación. | Gestión basada en datos y transparencia con el mandante. |

### Recomendaciones para profundizar

*Sección 9 · Entrega*

1. **Monte una canalización** — Cree un repositorio y configure integración continua: compilar, probar y publicar un artefacto en cada cambio. Se hace en una tarde.
2. **Infraestructura como código** — Pruebe una herramienta de aprovisionamiento declarativo y levante y destruya un ambiente completo con un comando.
3. **Datos de prueba** — Investigue técnicas de anonimización y generación de datos sintéticos para no copiar producción a los ambientes de prueba.
4. **Estrategias de despliegue** — Profundice en azul-verde, canario e interruptores de función. Elija una y defina su tiempo de reversión.
5. **Métricas DORA** — Estudie las cuatro métricas de entrega — frecuencia, tiempo de entrega, tasa de fallo y tiempo de recuperación — y decida cuáles comprometer.

---

## Sección 10 · Tendencias

- Contenedores, orquestación e ingeniería de plataforma
- Infraestructura como código, GitOps y entrega continua
- Observabilidad, malla de servicios y computación en el borde
- Arquitecturas de datos e inteligencia artificial en la solución
- FinOps, sostenibilidad y cómo tratar la innovación sin caer en la moda

### Mapa de tendencias

No hay que usarlas todas. Hay que conocerlas para poder elegir con criterio — y para poder responder si el evaluador pregunta.

| Contenedores y orquestación | Ingeniería de plataforma | Infraestructura como código | Observabilidad |
| --- | --- | --- | --- |
| Empaquetado portátil y<br>coordinación automática de<br>decenas de servicios. | Una plataforma interna que<br>estandariza cómo se despliega<br>y se opera. | La infraestructura se define en<br>archivos versionados, no a<br>mano. | Métricas, registros y trazas<br>unificados para entender<br>sistemas distribuidos. |

| Computación en el borde | Datos en tiempo real | Inteligencia artificial | FinOps y sostenibilidad |
| --- | --- | --- | --- |
| Procesar cerca de donde se<br>generan los datos, no en un<br>solo centro. | Flujos continuos de eventos<br>en vez de procesos por lotes<br>nocturnos. | Modelos de lenguaje,<br>recuperación aumentada y<br>agentes dentro del producto. | Gobernar el costo y el<br>consumo energético como<br>atributos de diseño. |

### Contenedores y orquestación

Los contenedores dejaron de ser una novedad: son la unidad de despliegue estándar. La discusión actual ya no es si usarlos, sino cuánta complejidad de orquestación se justifica.

| Lo que se consolidó | La discusión abierta |
| --- | --- |
| La imagen del contenedor como artefacto único que<br>viaja entre ambientes.<br>Los servicios gestionados de orquestación, que evitan<br>administrar el clúster.<br>El despliegue progresivo con reversión automática como<br>práctica normal.<br>El registro de imágenes con análisis de vulnerabilidades<br>integrado. | Para muchas soluciones, un orquestador completo es<br>excesivo: bastan contenedores gestionados.<br>La complejidad operativa se subestima de forma<br>sistemática.<br>Alternativas más simples ganaron terreno para cargas<br>pequeñas y medianas.<br>La pregunta correcta: ¿cuántos servicios y cuántos<br>despliegues por semana tendré realmente? |

> Para su oferta: si propone orquestación, declare si el clúster es gestionado por el proveedor o por su equipo. Cambia el presupuesto de horas.

### Ingeniería de plataforma

En vez de que cada equipo resuelva por su cuenta el despliegue, el monitoreo y la seguridad, una plataforma interna ofrece un camino estándar, documentado y automatizado.

| Camino pavimentado | Autoservicio | Plantillas | Gobierno incorporado |
| --- | --- | --- | --- |
| Una forma recomendada y<br>automatizada de construir y<br>desplegar, que resuelve por<br>defecto seguridad, registro y<br>monitoreo. | El equipo de desarrollo crea<br>sus ambientes sin abrir un<br>ticket ni esperar a<br>operaciones. | Servicios nuevos que nacen ya<br>con pruebas, canalización de<br>despliegue y observabilidad<br>configuradas. | Las políticas de seguridad y de<br>costo se aplican en la<br>plataforma, no en la buena<br>voluntad de cada equipo. |

> Traducción para su propuesta: aunque no construyan una plataforma, sí pueden comprometer un procedimiento único y automatizado de despliegue. Eso reduce riesgo y es un diferenciador creíble frente a competidores que despliegan a mano.

### Infraestructura como código y GitOps

| Infraestructura como código | GitOps |
| --- | --- |
| Servidores, redes y reglas de seguridad se describen<br>en archivos de texto versionados.<br>El ambiente se crea y se destruye con un comando,<br>siempre igual.<br>Desaparece la diferencia entre desarrollo, pruebas y<br>producción.<br>El cambio de infraestructura pasa por revisión, igual<br>que el código.<br>La documentación deja de desactualizarse: el código<br>es la documentación. | El repositorio es la única fuente de verdad del estado<br>deseado.<br>Un agente compara continuamente lo desplegado con<br>lo declarado y corrige la diferencia.<br>Cada cambio queda registrado, con autor y motivo:<br>auditoría automática.<br>Volver atrás es revertir un cambio en el repositorio.<br>Nadie modifica producción a mano. |

> Argumento para la oferta: «El ambiente completo está descrito como código; ante un desastre se reconstruye en menos de X horas y ese procedimiento se prueba trimestralmente». Es un compromiso de continuidad verificable, no una promesa.

### DevOps, DevSecOps y entrega continua

**Una arquitectura moderna sin automatización de despliegue no es moderna: es frágil.**

| Integración continua | Entrega continua | Seguridad en la canalización |
| --- | --- | --- |
| Cada cambio se integra y se prueba<br>automáticamente. Los errores aparecen en<br>minutos, no en la etapa de pruebas. | Cada versión aprobada puede desplegarse<br>con un botón. Publicar deja de ser un<br>evento riesgoso. | Análisis de dependencias, revisión de código<br>y escaneo de imágenes automatizados en<br>cada cambio. |

| Pruebas automatizadas | Despliegue progresivo | Cultura de postmortem |
| --- | --- | --- |
| Unitarias, de integración y de carga,<br>ejecutadas sin intervención antes de cada<br>publicación. | La versión nueva se libera a un porcentaje<br>del tráfico y se revierte automáticamente si<br>empeoran las métricas. | Los incidentes se analizan sin buscar<br>culpables y producen mejoras concretas en<br>el sistema. |

> En el presupuesto de la oferta esto aparece como horas de ingeniería y herramientas. Omitirlo no lo hace gratis: lo transforma en sobrecosto durante la operación.

### Observabilidad, malla de servicios y eBPF

| Observabilidad unificada | Malla de servicios | eBPF |
| --- | --- | --- |
| Métricas, registros y trazas<br>correlacionados bajo un estándar abierto<br>de instrumentación, de modo que la<br>aplicación no quede amarrada a una<br>herramienta.<br>Permite responder preguntas que no se<br>anticiparon al construir el sistema. | Una capa de red que resuelve fuera del<br>código el cifrado entre servicios, los<br>reintentos, los tiempos límite, el<br>enrutamiento y la telemetría.<br>Muy potente y muy pesada: se justifica<br>cuando hay muchos servicios, no cuando<br>hay cinco. | Tecnología que permite observar y<br>controlar el tráfico y el comportamiento<br>del sistema desde el núcleo del sistema<br>operativo, sin modificar la aplicación.<br>Está detrás de las herramientas de red,<br>seguridad y observabilidad más recientes. |

> Criterio de proporción: la observabilidad siempre se justifica — sin ella no hay SLA. La malla de servicios y eBPF, en cambio, sólo aparecen en soluciones con muchos servicios y equipos dedicados a operarlas.

### Computación en el borde

En vez de enviar todos los datos a un centro de procesamiento, parte del cómputo ocurre cerca de donde se generan.

| Ancho de banda | Continuidad | Privacidad |
| --- | --- | --- |
| Procesar localmente evita el Se envía sólo el resultado y<br>viaje de ida y vuelta. Crítico no el flujo completo de<br>cuando la respuesta debe ser datos. Baja el costo de<br>inmediata. transmisión.<br>Casos donde aparece con naturalidad:<br>Sucursales, faenas mineras o instalaciones con conectividad<br>intermitente.<br>Sensores industriales y control de procesos que no toleran<br>latencia. | La operación sigue<br>funcionando aunque se caiga<br>el enlace con el centro de<br>datos.<br>Video y visión por computador,<br>inviable.<br>Puntos de venta y logística en | El dato sensible puede<br>procesarse en el sitio y salir<br>sólo agregado o<br>anonimizado.<br>donde transmitir todo el flujo es<br>terreno. |

### Datos en tiempo real

| El modelo tradicional · por lotes | El modelo de flujo · streaming |
| --- | --- |
| Los datos se acumulan y se procesan de noche.<br>El reporte de hoy refleja lo que pasó ayer.<br>Simple de construir y de operar.<br>Suficiente para contabilidad, cierres y reportes<br>periódicos. | Cada hecho de negocio se publica como evento en el<br>momento en que ocurre.<br>Los tableros y las alertas reflejan el estado actual.<br>Habilita detección de fraude, alertas operativas y<br>personalización inmediata.<br>Más complejo: exige orden, reintentos y manejo de<br>eventos duplicados. |

> Innovación acotada y defendible: no convierta todo el sistema a tiempo real. Elija un caso de uso donde la inmediatez genere valor medible para el mandante — una alerta operativa, un tablero de gestión — y proponga sólo eso. Es más creíble y mucho más barato.

### Arquitecturas de datos

| Almacén de datos | Lago de datos | Lakehouse | Malla de datos |
| --- | --- | --- | --- |
| Datos estructurados, limpios y<br>modelados para reportes y<br>análisis de negocio.<br>Fortaleza: consultas rápidas y<br>consistentes.<br>Límite: rígido y costoso de<br>cambiar. | Repositorio que guarda datos<br>en bruto, de cualquier<br>formato, a bajo costo.<br>Fortaleza: flexibilidad y<br>volumen.<br>Límite: sin gobierno se<br>convierte en un pantano de<br>datos. | Combina el almacenamiento<br>barato del lago con las<br>garantías de consistencia del<br>almacén.<br>Fortaleza: una sola plataforma<br>para reportes y analítica<br>avanzada. | Enfoque organizacional: cada<br>dominio de negocio publica<br>sus datos como un producto,<br>con dueño y calidad<br>comprometida.<br>Más un modelo de gobierno<br>que una tecnología. |

> Para la mayoría de los casos del curso, una base de datos transaccional bien modelada más una vista de lectura para reportes es la respuesta correcta y honesta.

### Inteligencia artificial en la arquitectura

**Incorporar IA cambia la arquitectura: aparecen componentes, costos y riesgos que antes no existían.**

| Recuperación aumentada (RAG) | Base de datos vectorial |
| --- | --- |
| Se consume un modelo de lenguaje por API. El modelo responde apoyándose en los<br>No hay que entrenar nada, pero se paga por documentos de la organización: se buscan<br>uso y los datos salen de la organización. los fragmentos relevantes y se le entregan<br>como contexto. | Almacén especializado que permite buscar<br>por significado y no por palabra exacta. Es el<br>componente nuevo en el diagrama. |

| Agentes | Modelos propios | IA en el desarrollo |
| --- | --- | --- |
| Modelos que encadenan pasos y ejecutan<br>acciones sobre otros sistemas. Requieren<br>límites, permisos y registro de todo lo que<br>hacen. | Entrenar o ajustar un modelo con datos de<br>la organización. Alto costo, exige datos de<br>calidad y perfiles especializados. | Asistentes que generan código y pruebas.<br>Cambia la productividad estimada del<br>equipo, pero exige revisión humana. |

> Si su propuesta incluye IA, el diagrama debe mostrarla: dónde está el modelo, de dónde salen los datos que lo alimentan y qué pasa cuando el modelo no está disponible.

### IA · lo que cambia en costos, riesgos y ética

| Costos nuevos | Riesgos y responsabilidades |
| --- | --- |
| Cobro por volumen procesado: el costo crece con el uso,<br>no con el número de servidores.<br>Latencia mayor que una consulta tradicional: hay que<br>diseñar la experiencia con eso en mente.<br>Cómputo especializado si se ejecuta el modelo<br>internamente: es caro y escaso.<br>Curaduría y actualización permanente de la base de<br>conocimiento. | Respuestas incorrectas presentadas con seguridad: exige<br>verificación y trazabilidad.<br>Datos personales o confidenciales enviados a un tercero:<br>hay que declararlo y contratarlo.<br>Sesgos en las respuestas y decisiones que afectan a<br>personas.<br>Dependencia de un proveedor y de un modelo que<br>puede cambiar sin aviso.<br>Quién responde ante un error del sistema: es una<br>pregunta contractual, no técnica. |

> Si incorpora IA, declare en la oferta qué decisiones toma el modelo, cuáles quedan siempre en manos de una persona y cómo se audita lo que el sistema respondió.

### MLOps y el ciclo de vida de los modelos

Un modelo no es un entregable que se instala una vez: se degrada con el tiempo porque la realidad cambia. Operarlo es parte de la arquitectura.

**1**

**2**

**3**

**4**

**5**

**6**

| Datos 1 | Entrenamiento 2 | Validación 3 | Despliegue 4 | Monitoreo 5 | Reentrenamiento 6 |
| --- | --- | --- | --- | --- | --- |
| Recolección,<br>etiquetado,<br>versionado y<br>control de calidad<br>del conjunto de<br>entrenamiento. | Experimentos<br>reproducibles, con<br>registro de<br>parámetros y<br>resultados. | Métricas de<br>desempeño y<br>revisión de sesgos<br>antes de liberar. | El modelo se<br>publica como<br>servicio,<br>versionado y con<br>posibilidad de<br>reversión. | Vigilancia de la<br>deriva: cuando los<br>datos reales se<br>alejan de los de<br>entrenamiento, el<br>modelo pierde<br>precisión. | Ciclo periódico y<br>automatizado. Es<br>un costo<br>recurrente que<br>debe estar en el<br>flujo de caja. |

> Si su propuesta incluye un modelo propio, el reentrenamiento y el monitoreo son ítems de operación anual, no una tarea del proyecto inicial.

### FinOps · el costo como atributo de diseño

En la nube, cada decisión de arquitectura tiene un precio por hora. FinOps es la práctica de gobernar ese gasto con la misma disciplina con que se gobierna el rendimiento.

| Visibilidad | Asignación | Optimización | Previsión |
| --- | --- | --- | --- |
| Etiquetar cada recurso por<br>proyecto, ambiente y<br>responsable. Sin etiquetas<br>no hay control posible. | Saber cuánto cuesta cada<br>módulo o cada cliente.<br>Permite decidir qué se<br>optimiza primero. | Ajustar el tamaño de las<br>instancias, apagar ambientes<br>fuera de horario, usar<br>capacidad reservada donde<br>la carga es estable. | Estimar el gasto del próximo<br>período y alertar antes de<br>superarlo, no después de la<br>factura. |

> Diferenciador concreto para la oferta: comprometer un informe mensual de consumo y un tope de gasto acordado con el mandante. Cuesta poco ofrecerlo y demuestra que entienden que la nube es un costo operacional que hay que administrar.

### Sostenibilidad y eficiencia energética

El impacto ambiental de una solución informática es una restricción del contexto que el diseño puede reducir. Y en varias bases de licitación ya es un criterio evaluado.

| Eficiencia del cómputo | Elección de región | Ciclo de vida del hardware |
| --- | --- | --- |
| Menos recursos ociosos, autoescalado y<br>apagado de ambientes fuera de horario<br>reducen consumo y costo al mismo tiempo. | Los centros de datos difieren en su matriz<br>energética y en su eficiencia. Es un criterio<br>declarable en la decisión. | En on-premise: vida útil, reciclaje y<br>disposición final del equipamiento<br>reemplazado. |

| Datos que se guardan | Eficiencia del software | Cómo se declara |
| --- | --- | --- |
| Retener todo para siempre consume<br>energía y dinero. Una política de retención<br>es también una medida ambiental. | Código y consultas eficientes reducen el<br>hardware necesario. Optimizar es la medida<br>más barata. | Estime el consumo asociado a la solución y<br>señale las medidas adoptadas. No hace falta<br>ser exacto: hace falta ser explícito. |

### Otras corrientes que conviene conocer

| Bajo código / sin código | API como producto | Arquitectura componible |
| --- | --- | --- |
| Construir aplicaciones con configuración<br>visual en vez de programación. Rápido para<br>procesos internos; limitado y con<br>dependencia fuerte del proveedor. | Las interfaces se diseñan, documentan,<br>versionan y se les mide adopción como si<br>fueran un producto con clientes. | Armar la solución integrando servicios<br>especializados de terceros — pagos,<br>identidad, notificaciones — en vez de<br>construir todo. |

| WebAssembly | Arquitectura sin base de datos propia | Ingeniería del caos |
| --- | --- | --- |
| Formato que permite ejecutar código de<br>forma segura y muy liviana, tanto en el<br>navegador como en el servidor y en el<br>borde. | Servicios gestionados que eliminan la<br>administración del motor: menos<br>operación, más costo variable y más<br>dependencia. | Provocar fallas controladas en producción<br>para verificar que los mecanismos de<br>resiliencia realmente funcionan. |

### Cómo tratar la innovación en su propuesta

La innovación es un ítem evaluado de su propuesta. Pero una tecnología sin justificación resta puntaje en vez

**de sumarlo.**

| Innovación que suma | Innovación que resta |
| --- | --- |
| Resuelve un problema declarado en las bases.<br>Está acotada: se aplica a un módulo, no a todo el<br>sistema.<br>Tiene costo estimado en el flujo de caja.<br>Tiene un plan alternativo si no funciona.<br>Está respaldada por una referencia verificable, citada en<br>norma APA. | Aparece porque «está de moda» o porque suena bien en<br>la presentación.<br>Abarca todo el sistema y multiplica el riesgo del<br>proyecto.<br>No tiene costo asociado en la oferta económica.<br>Nadie del equipo puede explicar cómo se opera.<br>No resiste la primera pregunta del evaluador. |

> Prueba de fuego: si le preguntan «¿qué pasa si sacamos esta tecnología de su propuesta?» y la respuesta es «nada importante», entonces no es innovación: es adorno.

### Recomendaciones para profundizar

*Sección 10 · Tendencias*

1. **Elija sólo una** — Tome una tendencia de esta sección, investíguela a fondo y prepare una defensa de dos minutos sobre por qué su caso la necesita.
2. **Ecosistema nativo de nube** — Recorra el mapa de proyectos de la Cloud Native Computing Foundation e identifique los que resolverían un problema real de su caso.
3. **IA en el producto** — Estudie el patrón de recuperación aumentada (RAG) y estime su costo por consulta antes de proponerlo en la oferta.
4. **FinOps** — Investigue las prácticas de etiquetado y control de gasto en la nube, y proponga un tope mensual acordado con el mandante.
5. **Sostenibilidad** — Busque cómo se estima la huella de una solución informática y qué medidas concretas la reducen. Es un diferenciador poco usado.

---

## Sección 11 · De la teoría a su propuesta

- Qué se evalúa exactamente en la arquitectura de su oferta
- Una ruta de siete pasos, del requisito al diagrama y del diagrama al costo
- Matriz de trazabilidad y ficha de parámetros a declarar
- Comparación de alternativas con criterios explícitos y ponderados
- Errores frecuentes y cómo presentar la arquitectura ante cada audiencia

### Qué se evalúa exactamente

Resultado de Aprendizaje 1: construye la arquitectura lógica y física de la solución informática requerida en el caso asignado, considerando estándares tecnológicos vigentes y las restricciones organizacionales, económicas y ambientales del contexto.

| CE 1.1 · Trazabilidad | CE 1.2 · Dimensionamiento | CE 1.3 · Estándares | CE 1.4 · Restricciones |
| --- | --- | --- | --- |
| Especifica los módulos,<br>interfaces e integraciones de<br>la arquitectura lógica,<br>estableciendo la trazabilidad<br>de cada componente con los<br>requisitos declarados en las<br>bases técnicas. | Dimensiona los componentes<br>de la arquitectura física y de la<br>base de datos — servidores,<br>redes, equipos de seguridad,<br>tamaño, uptime y tiempos de<br>respuesta — con parámetros<br>verificables y consistentes con<br>el volumen de operación<br>previsto. | Aplica estándares y buenas<br>prácticas vigentes de la<br>industria en las decisiones de<br>arquitectura, señalando la<br>referencia que respalda cada<br>opción adoptada. | Identifica las restricciones<br>organizacionales, económicas<br>y ambientales que<br>condicionan la solución, e<br>indica de qué modo son<br>incorporadas en el diseño. |

### La ruta, en siete pasos

**1**

**Leer las bases**

Extraer todos los requisitos, explícitos e implícitos.

**2**

**Definir el alcance**

Qué entra, qué no entra, qué supuestos se declaran.

**3**

**Arquitectura lógica**

Módulos, interfaces e integraciones, trazables a los requisitos.

**4**

**Arquitectura física**

Nodos, redes, seguridad y dimensionamiento con parámetros.

**5**

**Comparar alternativas**

Criterios explícitos, ponderados y aplicados de forma uniforme.

**6**

**Justificar**

Estándares, buenas prácticas y referencias en norma APA.

**7**

**Costear**

Traducir cada componente en inversión y costo de operación.

### Pasos 1 y 2 · de las bases al alcance

| Paso 1 · Leer las bases técnicas | Paso 2 · Definir el alcance |
| --- | --- |
| Numere cada requisito: RQ-01, RQ-02… Ese número es la<br>clave de toda la trazabilidad posterior.<br>Separe requisitos funcionales de atributos de calidad.<br>Anote los volúmenes: usuarios, transacciones,<br>documentos, sucursales, horarios de operación.<br>Identifique los sistemas del mandante con los que hay<br>que integrarse.<br>Marque lo que no está dicho: si no se declara, hay que<br>preguntarlo o declararlo como supuesto. | Escriba explícitamente qué queda dentro del contrato.<br>Escriba explícitamente qué queda fuera: es la protección<br>del proyecto y de su margen.<br>Declare los supuestos con su fundamento: «se asume<br>10% de concurrencia en hora punta».<br>Declare las dependencias del mandante: accesos,<br>ambientes, datos, contrapartes.<br>Todo lo que quede ambiguo aquí se transformará en<br>conflicto durante la ejecución. |

> Un alcance bien delimitado es una decisión de arquitectura: define las fronteras del sistema, y por lo tanto qué se construye, qué se integra y qué se deja afuera.

### Paso 3 · La arquitectura lógica

Objetivo: que cualquier persona entienda de qué partes se compone la solución y cómo se relacionan, sin necesidad de conocer la tecnología.

| Diagrama de contexto | Diagrama de módulos | Interfaces |
| --- | --- | --- |
| El sistema como una caja, rodeado de sus<br>usuarios y de los sistemas externos con los<br>que conversa. Una sola lámina, entendible<br>por cualquiera. | El interior del sistema: los grandes bloques<br>funcionales, con sus responsabilidades<br>declaradas en una frase cada uno. | Qué expone cada módulo y qué consume.<br>Con qué protocolo y con qué frecuencia.<br>Aquí aparecen las APIs. |

| Integraciones | Modelo de datos conceptual | Decisiones |
| --- | --- | --- |
| Cada sistema externo: qué dato se<br>intercambia, en qué sentido, con qué<br>periodicidad y qué pasa si no responde. | Las entidades principales y sus relaciones.<br>No el modelo físico completo: las entidades<br>del negocio. | El estilo elegido — monolito modular, capas,<br>servicios — con las razones y las alternativas<br>descartadas. |

> Prueba de calidad: si el diagrama menciona marcas de productos, todavía es arquitectura física disfrazada. La lógica se describe con funciones, no con proveedores.

### La matriz de trazabilidad

Cada componente de su arquitectura debe poder responder: ¿qué requisito de las bases justifica que existas?

| Requisito (bases técnicas) | Componente lógico | Nodo físico | Atributo de calidad comprometido |
| --- | --- | --- | --- |
| RQ-01 · Registro de solicitudes en línea | Módulo de Solicitudes + Portal Web | Servidores web y de aplicación | p95 < 2 s con 500 concurrentes |
| RQ-02 · Integración con el ERP del mandante | Servicio de Integración ERP | Servidor de integración | Reintento automático; cola de respaldo |
| RQ-03 · Firma electrónica de documentos | Módulo de Firma + proveedor externo | Servicio externo (SaaS) | Disponibilidad dependiente de tercero: declarada |
| RQ-04 · Reportería de gestión mensual | Módulo de Reportes + vista de lectura | Réplica de sólo lectura | No impacta la operación transaccional |
| RQ-05 · Trazabilidad y auditoría por 5 años | Servicio de Auditoría | Almacenamiento de objetos | Retención 60 meses; escritura inmutable |
| RQ-06 · Operación 24/7 con 99,5% mensual | Transversal | Dos zonas de disponibilidad | 99,5% mensual; RTO 2 h; RPO 15 min |

> Doble lectura: hacia abajo verifica que no falte ningún requisito; hacia arriba verifica que no haya componentes que nadie pidió (y que nadie va a pagar).

### Paso 4 · La ficha de parámetros

Estos son los parámetros verificables que exige el criterio de evaluación. Complételos todos, con su supuesto de origen.

| Parámetro | Unidad | De dónde sale | Ejemplo |
| --- | --- | --- | --- |
| Usuarios totales | N.º | Bases técnicas del caso | 12.000 |
| Usuarios concurrentes en hora punta | N.º | Supuesto declarado sobre el total | 1.200 (10%) |
| Transacciones por segundo | TPS | Concurrentes × operaciones por minuto ÷ 60 | 80 |
| Tiempo de respuesta comprometido | s (p95) | Requisito de las bases o compromiso propio | < 2 s |
| Disponibilidad comprometida | % | Requisito de las bases; define la redundancia | 99,5% mensual |
| RTO / RPO | h / min | Impacto de la interrupción para el negocio | 2 h / 15 min |
| Volumen inicial de datos | GB | Registros × tamaño de fila + índices | 180 GB |
| Crecimiento de datos | GB / mes | Transacciones mensuales × tamaño medio | 12 GB/mes |
| Retención de información | meses | Normativa aplicable y política del mandante | 60 meses |

### Paso 4 · La ficha de parámetros · continuación 1

| Parámetro | Unidad | De dónde sale | Ejemplo |
| --- | --- | --- | --- |
| Ancho de banda requerido | Mbps | Tamaño medio de respuesta × TPS | 45 Mbps |
| Ventana de mantenimiento | h / mes | Acuerdo con el mandante; se excluye del SLA | 4 h mensuales, domingo de madrugada |
| Horizonte de evaluación | años | Definido para la evaluación económica | 5 años |

### Paso 5 · Comparar alternativas

Construya un cuadro comparativo con criterios explícitos, pondérelos según lo que el caso hace importante y aplíquelos de manera uniforme a todas las alternativas.

| Criterio | Peso | A · On-premise | B · Nube pública | C · Híbrido |
| --- | --- | --- | --- | --- |
| Inversión inicial | 25% | 2 | 5 | 3 |
| Costo total a 5 años | 20% | 3 | 4 | 4 |
| Cumplimiento de residencia de datos | 20% | 5 | 3 | 5 |
| Elasticidad ante estacionalidad | 15% | 1 | 5 | 4 |
| Tiempo de puesta en marcha | 10% | 2 | 5 | 3 |
| Capacidad de operación del mandante | 10% | 3 | 4 | 3 |
| TOTAL PONDERADO | 100% | 2,75 | 4,25 | 3,85 |

> Escala declarada: 1 = muy desfavorable, 5 = muy favorable. Los pesos se justifican con el caso, no con la preferencia del equipo. Y la decisión final puede no ser el puntaje más alto: si eligen otra, expliquen por qué — eso también se evalúa.

### Paso 6 · Justificar con estándares y referencias

«Lo elegimos porque nos pareció mejor» no es un fundamento. «Lo elegimos siguiendo X, que establece Y» sí lo es.

| Tipo de fuente | Para qué sirve | Ejemplos de uso en la oferta |
| --- | --- | --- |
| Normas y estándares | Respaldar decisiones de calidad, seguridad y gestión. | Modelo de calidad de producto de software; normas de seguridad de la información; marcos de gestión de servicios de TI. |
| Normativa aplicable | Fundar restricciones del contexto y obligaciones del diseño. | Ley de protección de datos personales; normativa sectorial del mandante; bases de licitación. |
| Documentación de proveedores | Sustentar dimensionamiento, precios y niveles de servicio. | Calculadoras de costo, acuerdos de nivel de servicio publicados, guías de arquitectura de referencia. |
| Marcos de buenas prácticas | Ordenar decisiones de arquitectura y de operación. | Marcos de arquitectura bien diseñada, guías de arquitectura nativa de nube, patrones de integración. |
| Literatura técnica | Fundamentar patrones y sus consecuencias. | Libros y artículos sobre patrones de arquitectura, sistemas distribuidos y microservicios. |

> Toda referencia debe ser verificable y estar citada en norma APA 7.ª ed., tanto en el texto como en el listado final.

### Paso 7 · Las restricciones del contexto

**No basta con identificarlas: hay que indicar de qué modo son incorporadas en el diseño.**

| Tipo de restricción | Ejemplos en un caso TIC | Cómo se incorpora en el diseño |
| --- | --- | --- |
| Organizacional | Capacidades del área de TI del mandante; políticas internas; sistemas heredados; disponibilidad de contrapartes. | Se elige un servicio gestionado para no exigir perfiles que el mandante no tiene. |
| Económica | Presupuesto de inversión; presupuesto anual de operación; forma de pago; horizonte de evaluación. | Se prefiere un perfil de gasto operacional para evitar el desembolso inicial. |
| Legal y normativa | Protección de datos personales; residencia de los datos; requisitos de auditoría y retención. | La región de despliegue y la política de retención se definen por la normativa. |
| Ambiental | Consumo energético; ciclo de vida del hardware; disposición del equipamiento reemplazado. | Autoescalado y apagado de ambientes no productivos; retención acotada de datos. |
| Técnica | Estándares del mandante; protocolos de integración obligatorios; conectividad disponible. | Las interfaces se diseñan según el estándar exigido, no según la preferencia del equipo. |
| Temporal | Plazo de implementación; hitos contractuales; ventanas de cambio del mandante. | Se prefiere una arquitectura simple y una entrega por fases antes que una solución elegante e imposible de terminar. |

### De la arquitectura al flujo de caja

Regla de consistencia: todo componente del diagrama tiene una línea en el presupuesto, y toda línea del

**presupuesto tiene un componente en el diagrama.**

| Componente de la arquitectura | Inversión (año 0) | Costo de operación (anual) |
| --- | --- | --- |
| Servidores / instancias de cómputo | Compra de hardware o nada, si es nube | Arriendo mensual o energía, soporte y renovación |
| Motor de base de datos | Licencia inicial | Mantención de licencia o servicio gestionado |
| Almacenamiento y respaldo | Cabina o volumen inicial | Crecimiento mensual + retención + pruebas de restauración |
| Red y seguridad perimetral | Firewall, WAF, certificados | Renovaciones, enlaces, actualizaciones de reglas |
| Observabilidad | Configuración inicial | Volumen de registros y métricas ingeridas |
| Ambientes no productivos | Habilitación | Consumo de desarrollo, pruebas y capacitación |
| Operación y soporte | Traspaso y documentación | Horas de operación, turnos y plan de soporte |
| Licencias de software base | Sistemas operativos, herramientas | Suscripciones y actualizaciones |

> Este cuadro es el insumo directo de la estructura de costos y del flujo de caja que construirán en la unidad de evaluación económica.

### Errores frecuentes que hunden una propuesta

| Un solo diagrama para todo | Cifras sin origen | Tecnología por moda | SLA imposible |
| --- | --- | --- | --- |
| Se entrega una lámina que<br>mezcla módulos con<br>servidores. No es ni<br>arquitectura lógica ni física. | «Se requieren 4 servidores»<br>sin explicar de dónde salió el<br>4. El evaluador no puede<br>verificarlo. | Microservicios, contenedores<br>e IA en un proyecto de cuatro<br>meses con cinco personas. | Se compromete 99,99% con<br>un servidor y respaldo diario.<br>Es una multa diferida. |

| Sin alternativas comparadas | Componentes que nadie pidió | Integraciones sin detalle | Arquitectura sin costo |
| --- | --- | --- | --- |
| Se presenta una solución sin<br>mostrar qué se evaluó ni por<br>qué se descartó lo demás. | Módulos que no responden a<br>ningún requisito: aumentan el<br>costo y bajan la<br>competitividad. | Una flecha que dice «se<br>integra con el ERP» sin<br>protocolo, frecuencia ni plan<br>ante falla. | El capítulo técnico y el<br>económico no se<br>corresponden. Es la<br>inconsistencia que más se<br>castiga. |

### Cómo presentar la arquitectura

| Audiencia técnica | Audiencia comercial y directiva |
| --- | --- |
| Muestre el diagrama de despliegue y las cifras de<br>dimensionamiento.<br>Explique el punto único de falla que eliminó y el que<br>decidió aceptar.<br>Use los términos correctos: p95, RTO, RPO, zona de<br>disponibilidad.<br>Tenga a mano el detalle de las integraciones y los<br>protocolos.<br>Prepare la respuesta a «¿y si se cae X?» para cada<br>componente. | Muestre el diagrama de contexto, no el de despliegue.<br>Traduzca a consecuencias: «el servicio sigue operando<br>aunque falle un centro de datos».<br>Hable de costo total, de riesgo y de plazo, no de<br>tecnología.<br>Una sola cifra memorable por atributo: disponibilidad,<br>tiempo de respuesta, costo mensual.<br>Cierre con qué recibe el mandante y qué se compromete<br>por contrato. |

> Tiene 15 minutos para toda la propuesta. La arquitectura no debería tomar más de 4 o 5: dos diagramas, tres cifras y una decisión bien justificada valen más que diez láminas.

### Qué hacer esta semana

Cinco productos concretos para llegar con la arquitectura resuelta a la próxima instancia de validación.

**1**

**2**

**3**

**4**

**5**

| Requisitos numerados 1 | Dos diagramas 2 | Ficha de parámetros 3 | Matriz de decisión 4 | Tres ADR 5 |
| --- | --- | --- | --- | --- |
| Listado RQ-01, RQ-02…<br>extraído de las bases<br>técnicas de su caso,<br>separando funcionales<br>de atributos de calidad. | Uno de contexto y uno<br>de módulos para la<br>arquitectura lógica; uno<br>de despliegue para la<br>física. Distintos y<br>consistentes entre sí. | La tabla completa, con<br>cada cifra y su supuesto<br>de origen declarado. | Al menos una<br>comparación<br>ponderada: on-premise<br>vs nube, o el estilo<br>arquitectónico elegido. | Las tres decisiones más<br>importantes, con<br>contexto, alternativas,<br>fundamento,<br>consecuencias y su<br>referencia. |

> Traiga estos cinco productos a la próxima sesión. Sobre ellos vamos a trabajar la estimación, la planificación y la estructura de costos: sin arquitectura definida, no hay nada que estimar.

### Estimar el costo de la solución · el método

La estimación no se adivina: se construye a partir del diagrama físico, componente por componente, con una

**unidad de medida declarada para cada uno.**

**1**

**2**

**3**

| 1 · Listar los componentes 1 | 2 · Definir la unidad 2 | 3 · Cuantificar 3 |
| --- | --- | --- |
| Tome el diagrama físico y escriba cada<br>elemento en una fila: cómputo, base de<br>datos, red, almacenamiento, seguridad,<br>monitoreo, respaldo.<br>4 | Para cada componente, en qué se mide:<br>horas de instancia, vCPU-hora, GB al mes,<br>millón de solicitudes, GB transferidos.<br>5 | Cuántas unidades al mes, derivadas del<br>volumen de operación del caso y de los<br>supuestos declarados.<br>6 |

| 4 · Multiplicar por ambientes 4 | 5 · Agregar lo transversal 5 | 6 · Proyectar 6 |
| --- | --- | --- |
| Producción, certificación, testing y<br>desarrollo. Cada uno consume, y todos<br>van en el presupuesto. | Plan de soporte del proveedor,<br>transferencia de datos, monitoreo y<br>respaldo. Es lo que siempre se olvida. | Del costo mensual al horizonte de<br>evaluación: doce meses, cinco años,<br>crecimiento de la demanda y<br>contingencia. |

### Las unidades de medida

Estas son las unidades en que los proveedores cobran. Cada línea de su presupuesto tiene que estar expresada en una de ellas.

| Unidad | Qué mide | Dónde aparece |
| --- | --- | --- |
| GB · TB | Gigabyte y Terabyte: volumen de datos almacenados o transferidos. | Almacenamiento, respaldo, transferencia |
| IDT · Inbound Data Transfer | Datos que entran a la nube. Habitualmente no se cobra. | Red virtual, almacenamiento |
| IRDT · Intra Region Data Transfer | Tráfico entre recursos dentro de la misma región, por ejemplo entre dos zonas de disponibilidad. | Red virtual; es el costo oculto de la alta disponibilidad |
| ODT · Outbound Data Transfer | Datos que salen hacia Internet. Es la transferencia que sí se cobra, y suele sorprender. | Red virtual, contenido descargado por usuarios |
| vCPU-hora | Un procesador virtual durante una hora. Unidad de cobro de los contenedores sin servidor. | Fargate, Container Apps |
| GB-hora | Un gigabyte de memoria durante una hora. Acompaña siempre a la vCPU-hora. | Fargate, Container Apps |
| Hora de instancia | Una máquina virtual encendida durante una hora, del tamaño contratado. | EC2, Azure VM, base de datos gestionada |

### Las unidades de medida · continuación 1

| Unidad | Qué mide | Dónde aparece |
| --- | --- | --- |
| Millón de solicitudes | Unidad de cobro de las pasarelas de API y de las funciones. | API Gateway, Lambda |
| ACL · Access Control List | Lista de control de acceso: conjunto de reglas del firewall de aplicación. Se cobra por lista y por regla. | WAF |
| Métrica · panel · alarma | Unidades de cobro del servicio de monitoreo: cada métrica personalizada, cada tablero y cada alarma suman. | CloudWatch, Azure Monitor |
| Evento registrado | Cada acción sobre la plataforma que queda auditada. Se cobra por millón de eventos. | CloudTrail |
| Pod o tarea | Una unidad de ejecución de contenedor, con su CPU y memoria asignadas. | Fargate, Kubernetes |

### El caso de ejemplo

Una solución en contenedores con cuatro ambientes, base de datos gestionada, pasarela de API y los servicios transversales de seguridad y monitoreo.

| Componente de la solución | Dimensionamiento declarado |
| --- | --- |
| Base de datos productiva | PostgreSQL gestionado, 4 vCPU / 16 GB RAM, 30 GB de almacenamiento, multizona, 100% del mes encendida |
| Base de datos de certificación y testing | PostgreSQL gestionado, 2 vCPU / 8 GB RAM, 30 GB, dos nodos, una sola zona |
| Ambiente productivo | 7 tareas de 0,25 vCPU / 0,5 GB y 5 tareas de 0,5 vCPU / 1 GB, 20 GB cada una, 30 días al mes |
| Ambiente de testing | 6 tareas de 0,25 vCPU / 0,5 GB y 5 tareas de 0,5 vCPU / 1 GB |
| Ambiente de certificación | 6 tareas de 0,25 vCPU / 0,5 GB y 5 tareas de 0,5 vCPU / 1 GB |
| Gestor de ambientes | 2 tareas de 0,5 vCPU / 1 GB |
| Servicios de comunicaciones | 2 tareas de 1 vCPU / 2 GB y 1 tarea de 4 vCPU / 8 GB |
| Pasarela de API | 1 millón de solicitudes REST al mes, más canales de tiempo real |
| Firewall de aplicación | 2 listas de control de acceso, con sus reglas y grupos de reglas |
| Registro de imágenes | 50 GB de almacenamiento mensual y 1 GB de descarga |
| Monitoreo y auditoría | 50 métricas, 1 tablero, 1 alarma; 3 millones de eventos de escritura y de lectura |
| Almacenamiento de objetos | Tres depósitos: 50 GB, 100 GB y 30 GB mensuales, con su transferencia asociada |

### Escenario 1 · contenedores sin servidor, una zona

Solución sobre contenedores sin servidor, desplegada en una sola región y una sola zona de disponibilidad.

| Servicio | Qué incluye | USD / mes |
| --- | --- | --- |
| Plan de soporte del proveedor | Soporte con tiempos de respuesta comprometidos; se cobra como porcentaje del gasto | 171,47 |
| Base de datos productiva | PostgreSQL gestionado 4 vCPU / 16 GB, multizona, bajo demanda | 583,60 |
| Bases de certificación y testing | PostgreSQL gestionado 2 vCPU / 8 GB, dos nodos, zona única | 316,42 |
| Contenedores · ambiente productivo | 7 tareas pequeñas + 5 tareas medianas | 151,08 |
| Contenedores · testing | 6 tareas pequeñas + 5 tareas medianas | 142,19 |
| Contenedores · certificación | 6 tareas pequeñas + 5 tareas medianas | 142,19 |
| Contenedores · gestor de ambientes | 2 tareas medianas | 17,78 |
| Contenedores · comunicaciones | 2 tareas de 1 vCPU + 1 tarea de 4 vCPU | 213,28 |
| Transferencia de datos de la red virtual | Cuatro tramos de red, con su tráfico de entrada, interno y de salida | 64,35 |
| Pasarela de API | 1 millón de solicitudes REST y canales de tiempo real | 46,02 |

### Escenario 1 · contenedores sin servidor, una zona · continuación 1

| Servicio | Qué incluye | USD / mes |
| --- | --- | --- |
| Firewall de aplicación | 2 listas de control con sus reglas | 16,80 |
| Registro de imágenes | 50 GB almacenados, 1 GB descargado | 5,02 |
| Monitoreo | 50 métricas, 1 tablero, 1 alarma | 16,00 |
| Auditoría de la plataforma | 3 millones de eventos de escritura y de lectura | 21,50 |
| Almacenamiento de objetos | Tres depósitos de 50, 100 y 30 GB con su transferencia | 20,69 |
| TOTAL MENSUAL | Todos los ambientes incluidos | 1.928,39 |

### Cómo se calcula una línea · las tareas de contenedor

Toda línea del presupuesto es una multiplicación. Ésta es la de las tareas de contenedor, que es la más representativa.

| Paso | Dato | Resultado |
| --- | --- | --- |
| Tamaño de la tarea | 0,25 vCPU y 0,5 GB de memoria | Es la unidad más pequeña que se puede contratar |
| Tiempo encendida | 1 tarea durante 30 días, las 24 horas | 720 horas al mes |
| Costo unitario mensual | vCPU-hora × 720 + GB-hora × 720 | ≈ 8,89 USD por tarea al mes |
| Cantidad de tareas | 7 tareas de este tamaño en el ambiente productivo | 8,89 × 7 = 62,23 USD |
| Tarea mediana | 0,5 vCPU y 1 GB, es decir el doble de recursos | ≈ 17,77 USD por tarea al mes |
| Cantidad de tareas medianas | 5 tareas en el ambiente productivo | 17,77 × 5 = 88,85 USD |
| Total del ambiente productivo | 62,23 + 88,85 | 151,08 USD al mes |

> Observe la proporción: doble de CPU y memoria, doble de precio. Esa linealidad es lo que permite estimar sin tener la solución construida — y lo que permite al evaluador verificar su cifra.

> Los valores unitarios cambian con el tiempo y con la región: lo que no cambia es el procedimiento.

### Escenario 2 · máquinas virtuales, una zona

La misma solución, pero ejecutada sobre nodos propios que hay que dimensionar, administrar y parchar.

| Servicio | Qué incluye | USD / mes |
| --- | --- | --- |
| Plan de soporte del proveedor | Sube respecto del escenario anterior porque el gasto total es mayor | 361,64 |
| Base de datos productiva | PostgreSQL gestionado 4 vCPU / 16 GB, multizona | 583,60 |
| Bases de certificación y testing | PostgreSQL gestionado 2 vCPU / 8 GB, dos nodos | 316,42 |
| Nodo productivo 1 | 8 vCPU / 32 GB / 300 GB de disco | 279,81 |
| Nodo productivo 2 | Mismo equipo, pero contratado en otra región | 1.623,81 |
| Nodo de testing y certificación | 8 vCPU / 32 GB / 300 GB | 279,81 |
| Coordinadores del clúster | Tres nodos de 4 vCPU / 8 GB / 100 GB | 446,76 |
| Transferencia de datos de la red virtual | Comunicaciones, portales y gestión de ambientes | 64,35 |
| Firewall de aplicación y registro de imágenes | Mismas reglas y mismo registro que el escenario anterior | 21,82 |
| TOTAL MENSUAL | Todos los ambientes incluidos | 3.978,02 |

> Lección de la quinta línea: el mismo nodo, con la misma especificación, cuesta casi seis veces más por estar en otra región. Revise siempre la columna de región antes de firmar una estimación.

### Los cuatro escenarios, comparados

La misma solución, estimada de cuatro formas. Ésta es la tabla que va en la comparación de alternativas del informe.

| Escenario | Cómputo | Zonas | USD / mes | USD / año | Diferencia |
| --- | --- | --- | --- | --- | --- |
| 1 | Contenedores sin servidor | Una zona | 1.928 | 23.141 | Referencia |
| 2 | Contenedores sin servidor | Dos zonas | 2.590 | 31.085 | +34% |
| 3 | Nodos propios (máquinas virtuales) | Una zona | 3.978 | 47.736 | +106% |
| 4 | Nodos propios (máquinas virtuales) | Dos zonas | 5.062 | 60.745 | +163% |

**Los contenedores sin servidor**

**La segunda zona cuesta un tercio**

**El soporte crece con el gasto**

**salieron a la mitad**

**más**

En este caso, no administrar nodos cuesta la

Ése es el precio concreto de subir de una

El plan de soporte pasó de 171 a 460

mitad que administrarlos — y además

zona a dos. Es exactamente la cifra que hay

dólares entre el escenario más barato y el

elimina las horas de operación del sistema

que poner al lado del compromiso de

más caro: se cobra como porcentaje del

operativo, que no están en esta tabla.

disponibilidad.

consumo.

### El escenario de peor caso

Una estimación seria no entrega un solo número: entrega el caso base y el techo. Así se modela el techo.

| Columna de la planilla | Qué representa | Ejemplo |
| --- | --- | --- |
| Costo mensual | El gasto del escenario base que entrega la calculadora. | 62,23 USD por 7 tareas |
| Cantidad | Cuántas unidades componen la línea: tareas, nodos, instancias. | 7 tareas |
| Costo mensual unitario | El costo dividido por la cantidad. Es lo que cuesta agregar una unidad más. | 62,23 ÷ 7 = 8,89 USD |
| Valor de levantamiento | Lo que cuesta poner en marcha una unidad adicional cuando sube la demanda. | 0,29 USD por tarea |
| Factor | Cuántas veces podría multiplicarse esa cantidad en el peor escenario previsto. | 50 veces |
| Peor caso | Cantidad × costo unitario + valor de levantamiento × factor × cantidad. | El techo del gasto de esa línea |

> Por qué importa en una licitación: si el contrato es a precio fijo, el peor caso es su riesgo. Si es a precio variable, es el riesgo del mandante y él querrá un tope. En ambos casos hay que tener la cifra calculada antes de firmar.

### De dólares al mes al flujo de caja

**La calculadora del proveedor entrega dólares al mes. El flujo de caja necesita seis cosas más.**

| Horizonte de evaluación | Crecimiento de la demanda |
| --- | --- |
| Declare la moneda del contrato y el tipo Proyecte los mismos meses que el resto<br>de cambio o la unidad de reajuste que de la evaluación. Doce meses no bastan si<br>usará. Si cobra en pesos y paga en dólares, el horizonte son cinco años.<br>el riesgo cambiario es suyo. | El gasto en la nube crece con el uso.<br>Modele el crecimiento anual de usuarios y<br>de datos: el almacenamiento nunca baja. |

| Puesta en marcha | Operación humana | Contingencia |
| --- | --- | --- |
| Migración de datos, configuración inicial,<br>certificaciones y horas de ingeniería. Es<br>inversión del año cero, no gasto mensual. | Las horas de quien administra la<br>plataforma no están en la calculadora. En<br>el escenario de nodos propios son<br>bastantes más. | Un porcentaje declarado sobre el total,<br>justificado por la incertidumbre de la<br>estimación. Entre 10% y 20% es<br>defendible. |

> Consistencia: el total mensual de esta planilla debe ser exactamente la línea «servicios de nube» de su flujo de caja. Si los números no coinciden, el evaluador lo va a notar.

### Errores frecuentes al estimar

| Cotizar sólo producción | Olvidar la transferencia de salida | Ignorar el plan de soporte | No revisar la región |
| --- | --- | --- | --- |
| Los ambientes de desarrollo,<br>testing y certificación suman<br>entre un tercio y la mitad del<br>gasto. En este ejemplo, más<br>de la mitad de las tareas son<br>de ambientes no productivos. | Los datos que salen hacia<br>Internet se cobran. En<br>soluciones con documentos o<br>video, esta línea puede ser la<br>más grande. | Es un porcentaje del gasto<br>total. Aparece en la factura<br>desde el primer mes y nadie lo<br>presupuesta. | El mismo equipo puede costar<br>varias veces más según dónde<br>se contrate. Verifique la<br>columna de región en cada<br>línea. |

| Dejar fuera el monitoreo | Estimar un solo escenario | Confundir mensual con anual | No guardar la evidencia |
| --- | --- | --- | --- |
| Métricas, tableros, alarmas,<br>registros y auditoría se cobran<br>por volumen. Sin ellos no hay<br>SLA, así que no son<br>opcionales. | Presente al menos dos<br>alternativas de cómputo y el<br>peor caso. Es lo que pide el<br>criterio de comparación de<br>alternativas. | Multiplicar por doce parece<br>obvio, pero es el error<br>aritmético más común en los<br>informes. | Las calculadoras generan un<br>enlace permanente a la<br>estimación. Guárdelo y cítelo:<br>es evidencia verificable. |

### Qué debe entregar en el informe

Cinco entregables que cierran el capítulo de costos de infraestructura de la oferta.

| Planilla de estimación | Al menos dos escenarios | Escenario de peor caso | Proyección al horizonte | Enlace a la estimación |
| --- | --- | --- | --- | --- |
| Una fila por<br>componente, con la<br>unidad de medida, la<br>cantidad, el supuesto<br>que la origina y el costo<br>mensual. | Dos alternativas de<br>cómputo comparadas<br>sobre la misma solución<br>y el mismo volumen,<br>con la diferencia<br>porcentual. | El techo de gasto con el<br>factor de crecimiento<br>declarado, y qué pasa<br>con el contrato si se<br>alcanza. | El costo mensual<br>convertido a la moneda<br>y al horizonte de la<br>evaluación, con<br>crecimiento y<br>contingencia. | La referencia verificable<br>de la calculadora del<br>proveedor, citada en el<br>informe según norma<br>APA. |

> Regla de cierre: cada caja de su diagrama físico debe tener una fila en la planilla, y cada fila de la planilla debe tener una caja en el diagrama. Si algo aparece en uno y no en el otro, hay un error en alguno de los dos.

### Glosario 1 / 8

| Término | Definición |
| --- | --- |
| Activo – Activo | Modalidad en que dos nodos o sitios atienden tráfico simultáneamente; si uno cae, el otro absorbe su carga. |
| Activo – Pasivo | Modalidad en que sólo un nodo atiende tráfico y el otro espera en reserva para tomar el relevo. |
| Alta disponibilidad | Capacidad del sistema de seguir prestando servicio aunque falle uno de sus componentes, sin interrupción ni intervención manual. |
| Ambiente | Instalación completa de la solución destinada a un propósito: desarrollo, QA, preproducción o producción. |
| Anonimización | Transformación de datos personales para que dejen de identificar a una persona. Obligatoria en ambientes no productivos. |
| API | Interfaz de programación de aplicaciones. Definiciones y protocolos que permiten a dos componentes de software comunicarse. |
| API Gateway | Punto único de entrada que recibe las llamadas a las APIs, las autentica, las enruta y agrega los resultados. |
| Arquitectura física | Vista que muestra la ubicación del software en el hardware: nodos, redes, capacidad y ubicación geográfica. |

### Glosario 2 / 8

| Término | Definición |
| --- | --- |
| Arquitectura lógica | Vista que muestra módulos, interfaces e integraciones del software, con independencia de la tecnología que los ejecuta. |
| Artefacto | Paquete versionado producido por la construcción — imagen de contenedor o binario — que se promueve entre ambientes. |
| Autoescalado | Ajuste automático de la cantidad de instancias según una métrica de carga o un horario. |
| Azul – verde | Estrategia de despliegue que levanta el entorno nuevo completo en paralelo y conmuta el tráfico de una sola vez. |
| Balanceador de carga | Componente que reparte peticiones entre varios nodos y retira de rotación al que no responde. |
| Base de datos | El conjunto de datos y su estructura — tablas, índices, relaciones — que el motor administra. |
| Canario | Estrategia de despliegue que envía un pequeño porcentaje del tráfico a la versión nueva y la amplía si las métricas se mantienen. |
| CAPEX | Gasto de capital: inversión inicial en activos como hardware y licencias perpetuas. Se deprecia. |

### Glosario 3 / 8

| Término | Definición |
| --- | --- |
| CDN | Red de distribución de contenido. Nodos distribuidos que entregan contenido estático desde el punto más cercano al usuario. |
| CI / CD | Integración continua y entrega o despliegue continuo: automatización del camino desde el cambio de código hasta producción. |
| Consistencia eventual | Propiedad por la cual los datos replicados quedan consistentes después de un tiempo, no de inmediato. |
| Contenedor | Paquete estándar que agrupa una aplicación con sus bibliotecas y dependencias, para ejecutarse igual en cualquier entorno. |
| DMZ | Zona desmilitarizada: segmento de red intermedio entre Internet y la red interna donde se publican los servicios expuestos. |
| Doble factor (MFA) | Autenticación que exige un segundo elemento además de la contraseña. Obligatoria para acceso remoto y administradores. |
| Elasticidad | Capacidad de asignar y retirar recursos de forma automática, respondiendo de forma flexible a la demanda. |
| Endpoint | URL específica donde una API recibe solicitudes. |

### Glosario 4 / 8

| Término | Definición |
| --- | --- |
| Escalamiento horizontal | Agregar más nodos a la solución para repartir la carga entre ellos. |
| Escalamiento vertical | Agregar más recursos — procesador, memoria — al mismo equipo. |
| Evento | Registro de un hecho de negocio que ocurrió. Se publica para que otros componentes reaccionen a él. |
| Failover / Failback | Conmutación del servicio al sitio alternativo ante una falla, y posterior regreso al sitio original. |
| FinOps | Práctica de gobernar el gasto en la nube: visibilidad, asignación por responsable, optimización y previsión. |
| GFS | Esquema de retención de respaldos abuelo-padre-hijo: diarias, semanales, mensuales y anuales con distinta permanencia. |
| IaaS | Infraestructura como servicio: cómputo, almacenamiento y red entregados como servicio, con pago por uso. |
| IaC | Infraestructura como código: definir la infraestructura en archivos versionados en vez de configurarla manualmente. |

### Glosario 5 / 8

| Término | Definición |
| --- | --- |
| Idempotencia | Propiedad por la cual repetir una operación produce el mismo resultado que ejecutarla una sola vez. |
| Inmutabilidad (respaldo) | Copia que no puede borrarse ni alterarse durante un período definido, ni siquiera por un administrador. |
| Latencia | Tiempo que tarda una operación en responder. |
| Microservicio | Servicio pequeño y autónomo que implementa una capacidad de negocio y se despliega de forma independiente. |
| Modelo OSI | Modelo de referencia que describe la comunicación en red en siete capas, de la física a la de aplicación. |
| Monolito | Aplicación cuyo código y funcionalidades están acoplados en un único paquete desplegable. |
| Motor de base de datos | El software que administra los datos: recibe consultas, controla concurrencia y garantiza integridad. Tiene licencia. |
| Multi-primario | Topología de replicación en que varios nodos aceptan escrituras. Habilita activo-activo, pero introduce conflictos. |

### Glosario 6 / 8

| Término | Definición |
| --- | --- |
| Observabilidad | Capacidad de entender el estado interno del sistema desde fuera, combinando métricas, registros y trazas. |
| OPEX | Gasto operacional: costo recurrente de operar la solución. No se deprecia; se imputa al ejercicio. |
| PaaS | Plataforma como servicio: entorno gestionado donde se despliegan aplicaciones sin administrar el servidor. |
| Percentil 95 (p95) | Valor bajo el cual responde el 95% de las peticiones. Medida realista del tiempo de respuesta comprometido. |
| Punto único de falla | Componente cuya caída deja fuera de servicio a todo el sistema. |
| Quórum | Esquema en que una escritura se confirma cuando la acepta la mayoría de los nodos. Evita la partición de cerebro. |
| Región / Zona de disponibilidad | Región: ubicación geográfica de centros de datos. Zona: centro de datos aislado dentro de una región. |
| Regla 3-2-1 | Política de respaldo: tres copias de los datos, en dos medios distintos, con una fuera del sitio. |

### Glosario 7 / 8

| Término | Definición |
| --- | --- |
| Replicación asincrónica | La transacción se confirma localmente y se envía después al otro sitio. No penaliza la latencia; el RPO es mayor que cero. |
| Replicación sincrónica | La transacción se confirma sólo cuando ambos sitios escribieron. RPO cero, a costa de la latencia del enlace. |
| REST | Estilo de API sobre HTTP que usa métodos estándar — GET, POST, PUT, DELETE — para operar sobre recursos. |
| RTO / RPO | Tiempo máximo aceptable de interrupción / cantidad máxima aceptable de datos perdidos, medida en tiempo. |
| SaaS | Software como servicio: aplicación entregada como servicio bajo demanda, normalmente vía navegador. |
| Serverless | Modelo en que se ejecutan funciones sin administrar servidores y se paga sólo por el tiempo de ejecución. |
| SLA / SLO / SLI | Acuerdo contractual de nivel de servicio / objetivo interno / indicador que se mide. |
| Split-brain | Situación en que se corta el enlace entre sitios y ambos se creen activos, aceptando escrituras y divergiendo. |

### Glosario 8 / 8

| Término | Definición |
| --- | --- |
| Storage de bloque | Disco crudo que el sistema operativo formatea y monta. Es el almacenamiento propio de las bases de datos. |
| Storage de objetos | Almacenamiento accesible por API HTTP, con capacidad casi ilimitada y bajo costo. Para documentos, imágenes y respaldos. |
| Throughput | Cantidad de operaciones que el sistema atiende por unidad de tiempo. |
| Uptime / Downtime | Tiempo en que el sistema opera sin interrupciones / tiempo en que no está operativo o es inaccesible. |
| VPC | Red virtual privada: red aislada dentro de la nube donde se despliegan los recursos, con control de subredes y rutas. |
| VPN | Túnel cifrado que conecta un equipo remoto a la red corporativa. Da acceso a la red completa: por eso se prefiere Zero Trust. |
| WAF | Firewall de aplicación web: filtra tráfico malicioso de capa 7 antes de que llegue a los servidores. |
| Zero Trust | Enfoque en que ninguna red es confiable por sí sola: cada acceso se autentica y autoriza según identidad, dispositivo y recurso. |

---

## Referencias

Fuentes de apoyo de esta unidad. En el informe, cite en norma APA 7.ª edición.

- **ISO/IEC 25010:2023.** *Systems and software engineering — SQuaRE — Product quality model*. Organización Internacional de Normalización. <https://iso25000.com/index.php/normas-iso-25000/iso-25010>
- **Ley N° 21.719**, que regula la protección y el tratamiento de los datos personales y crea la Agencia de Protección de Datos Personales. *Diario Oficial de la República de Chile*, 13 de diciembre de 2024. Entrada en plena vigencia: 1 de diciembre de 2026.
- **ISO/IEC 7498-1.** *Information technology — Open Systems Interconnection — Basic Reference Model: The Basic Model* (modelo OSI de siete capas).
- **OWASP Top 10.** Riesgos de seguridad más críticos en aplicaciones web. <https://owasp.org/Top10>
- **Kruchten, P.** *Architectural Blueprints — The 4+1 View Model of Software Architecture*.
- **Modelo C4** para la documentación de arquitecturas de software. <https://c4model.com>
- **Estilos arquitectónicos: microservicios.** <https://reactiveprogramming.io/blog/es/estilos-arquitectonicos/microservicios>
- **Diagramas de arquitectura de microservicios.** <https://www.edrawsoft.com/es/article/microservices-architecture-diagram.html>
- **Guías de arquitectura de referencia y marcos de buenas prácticas** publicados por los proveedores de nube (arquitecturas bien diseñadas, patrones de aplicaciones distribuidas).
- **Cloud Native Computing Foundation.** Ecosistema de herramientas y mejores prácticas para arquitecturas nativas de la nube. <https://www.cncf.io>

---

## Cierre

**Dibuje la suya. Póngale números. Después defiéndala.**

Antonio Moya Villegas · antonio.moya@pucv.cl · ICI-5444 · 2026
