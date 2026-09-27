# FORMULACIÓN DE PROYECTOS

## BASES TÉCNICAS
### PARA LA PREPARACIÓN DE LA PROPUESTA

**Versión 1.0**
**Fecha Documento:** 18-08-2026

---

# Bases Técnicas - Servicio de Puerto Deportivo

*Marina y Club Náutico Bahía Panitao S.A. — custodia, seguridad de las personas y evidencia ambiental*

| Asignatura | Taller de Formulación de Proyectos Informáticos — ICI-5444 |
|---|---|
| Unidad académica | Escuela de Informática, Pontificia Universidad Católica de Valparaíso |
| Profesor | Antonio Moya Villegas — antonio.moya@pucv.cl |
| Industria | Náutica deportiva y recreativa — puerto deportivo con varadero, surtidor, escuela de vela y club |
| Mandante | Marina y Club Náutico Bahía Panitao S.A. (empresa ficticia) |
| Operación | 320 amarras, 180 puestos de invernada y 40 boyas a 6 millas, en el Seno de Reloncaví. 4.800 zarpes, 1.150 movimientos de travelift y 470 menores navegando al año |
| Condición especial | Empresa de $ 4.200 millones de ingresos, sin ninguna persona de tecnologías de información, que custodia bienes ajenos de alto valor y opera bajo aviso de marejadas |
| Documentos que rigen | Bases Administrativas FEP01.26 y Bases Técnicas Transversales FEP02.26 |
| Duración del contrato | 56 meses: implementación en dos etapas y 36 meses de operación |
| Versión | 1.0 — agosto de 2026 |

> Este documento no es una especificación de requerimientos. Es la descripción de una operación real, con sus datos, sus dolores, sus contradicciones internas y sus vacíos.
>
> Identificar qué es funcional y qué no lo es, completar lo que falta con supuestos declarados y con reglas de negocio propias de la industria, investigar aquello que el documento no explica, y traducir todo ello en un alcance, una arquitectura, un plan y una estrategia de puesta en producción, es exactamente el trabajo que se está licitando y lo que será evaluado.

---

## CONTENIDO

| Título | Contenido | Capítulos |
|---|---|---|
| I · El mandante y el encargo | Cómo llegamos a esta licitación, la compañía, sus cifras, sus instalaciones, sus personas y las zonas del recinto. | 1 – 3 |
| II · La operación tal como es hoy | El ciclo de la embarcación y el del socio, los sistemas existentes, la conectividad y las condiciones del sitio, y los indicadores del problema. | 4 – 7 |
| III · Lo que dicen quienes operan | Diez entrevistas de levantamiento, incluidas las de un armador, una operadora de charter y una apoderada, con sus contradicciones intactas. | 8 |
| IV · Lo que el mandante espera | Expectativas de negocio, restricciones no negociables, marco normativo y prioridades. | 9 – 13 |
| V · Antecedentes para el dimensionamiento | Volumetría entregada y volumetría a estimar, parámetros del caso y decisiones deliberadamente no resueltas. | 14 – 16 |
| VI · Lo que debe producir el proponente | El trabajo de traducción exigido, los criterios de aceptación y cómo se evaluará este caso. | 17 – 19 |
| VII · Anexos del caso | Mapa de sistemas y flujos actuales, perfil y calendario operacional, y glosario de la industria. | A – C |

### Cómo leer este documento

Los Títulos I y II describen la operación. Se entregan con detalle porque de ellos dependen todas las decisiones de diseño: no hay atajo que permita saltarlos.

El Título III recoge las voces de quienes operan y también las de las tres personas que no trabajan en la marina: un armador, la operadora internacional de charter y la presidenta del centro de padres de la escuela de vela. No están de acuerdo entre sí, y esa discrepancia es información, no ruido: revela dónde el proyecto va a encontrar resistencia y qué tensiones habrá que arbitrar.

El Título IV expresa lo que el mandante espera, deliberadamente en lenguaje de negocio y no de requerimientos. El Título V entrega los datos duros que la compañía conoce, señala cuáles debe estimar el proponente, fija los parámetros de los requisitos que las Bases Técnicas Transversales dejaron abiertos al caso, y enumera veintidós decisiones que el cliente no ha tomado.

El Título VI describe el trabajo exigido y los criterios con que se juzgará. Conviene leerlo primero y volver a él al final.

> **Tres particularidades de este caso.**
>
> La primera es que el mandante no tiene ninguna persona de tecnologías de información. No es una dotación reducida: es cero. Toda decisión de arquitectura, de operación y de costo debe hacerse cargo de que al terminar el proyecto no hay a quién dejarle la solución, y el directorio aprobó licitar con un voto de minoría que exige demostrar que la empresa puede pagarla y operarla, no sólo comprarla.
>
> La segunda es que aquí se administra una custodia y no un servicio: embarcaciones ajenas de alto valor, cuatrocientos setenta menores de edad que navegan cada año, combustible y residuos peligrosos. Los dos episodios que originaron la licitación no fueron pérdidas económicas, sino la incapacidad de demostrar un aviso y la incapacidad de responder, durante cuarenta minutos, si un niño estaba en el agua.
>
> La tercera es que este es el único caso de la serie donde una ventana de trabajo puede cancelarse por decisión de la naturaleza. Un aviso de marejadas de la autoridad marítima, emitido con veinticuatro a cuarenta y ocho horas de anticipación y varias veces al año, suspende toda faena programada. El plan del proyecto debe absorber esas cancelaciones sin desplazar hitos contractuales, y debe declarar cuánta holgura reserva para ello y sobre qué base la calculó.

---

# TÍTULO I
## EL MANDANTE Y EL ENCARGO

## CAPÍTULO 1 · CÓMO LLEGAMOS A ESTA LICITACIÓN

El aviso de marejadas anormales llegó el 6 de julio de 2026 a las once de la mañana, con treinta y seis horas de anticipación. La marina activó su protocolo: doblar amarras, retirar del agua las embarcaciones más expuestas, avisar a los armadores.

Avisar a los armadores es una frase corta. En la práctica significa que tres personas de administración se sentaron con una planilla de doscientos noventa y seis contratos y empezaron a llamar por teléfono.

Alcanzaron a contactar efectivamente a ciento noventa. Del resto, unos tenían el número que dejaron el 2019, otros habían cambiado de correo, y de catorce embarcaciones sencillamente no hay una persona identificable a quien llamar: son las que llevan meses sin pagar y cuyos dueños dejaron de contestar hace tiempo.

La marejada entró la noche del 8 de julio. Tres embarcaciones sufrieron daños y una velero de once metros se hundió en su amarra, con el derrame menor de combustible que eso implica. No hubo personas a bordo y nadie resultó herido.

Lo que vino después fue peor que la noche. La compañía de seguros pidió el registro de a quién se avisó, cuándo y por qué medio. La autoridad marítima pidió lo mismo. Un armador presentó un reclamo formal sosteniendo que nunca fue notificado.

«Nosotros sí avisamos», dijo Ximena Bassa Undurraga, gerente general, en el directorio del 23 de julio. «El problema es que no lo puedo probar. Tengo tres personas que se acuerdan de haber llamado y una planilla con marcas hechas a lápiz. Eso no es evidencia en ninguna parte.»

Seis meses antes había pasado algo distinto, que no salió en ninguna parte y que en el club todavía se comenta.

El 12 de enero, un lunes de viento, la escuela de vela salió con dieciocho embarcaciones menores y tres monitores. Cuando volvieron al pantalán, el recuento no cuadraba: faltaba un alumno de trece años.

Durante cuarenta minutos nadie pudo establecer con certeza si el niño estaba en el agua o no. Estaba en su casa: su madre lo había retirado antes del inicio de la clase y lo había avisado en la portería, donde quedó anotado en un cuaderno que la escuela no revisa.

Nadie estuvo en peligro en ningún momento. Pero durante cuarenta minutos la marina no fue capaz de responder una pregunta que debería contestarse en diez segundos: quién salió al agua, en qué embarcación, con qué monitor y quién autorizó esa salida.

«Yo tengo cuatrocientos setenta menores de edad al año en el agua», dijo Marisol Ovando Kuschel, jefa de la escuela de vela, en la reunión con el centro de padres. «Y mi registro es una hoja que se firma en la mañana y que a las once ya no representa la realidad. Ese día tuvimos suerte. La suerte no es un procedimiento.»

Y en julio llegó la tercera noticia, esta vez por escrito, con tres hallazgos y con fecha de vencimiento.

La auditoría de renovación del esquema internacional de certificación ambiental de marinas levantó tres no conformidades: que la marina no puede demostrar qué residuos peligrosos generó cada embarcación ni dónde terminaron; que no mide consumo de agua ni de energía por amarra y por lo tanto sus indicadores ambientales son una estimación sobre un solo medidor; y que no tiene evidencia de la capacitación ambiental de las ciento cuarenta personas de empresas contratistas que trabajan en el varadero. Plazo para cerrarlas: la temporada 2029.

La misma semana, la operadora internacional de charter que mantiene catorce embarcaciones en la marina —el veintidós por ciento de los ingresos por amarra— envió su carta anual de renovación con tres condiciones nuevas: reserva y contratación de servicios en línea, interfaz en inglés y facturación con el consumo real de cada embarcación. Y una cuarta, escrita en una sola línea: mantener vigente la certificación ambiental.

El directorio aprobó licitar el proyecto por cinco votos contra dos. En el acta quedó consignado el voto de minoría, que la gerente general pidió expresamente que se transcribiera: «esta empresa factura cuatro mil doscientos millones de pesos al año y no tiene una sola persona dedicada a informática. Antes de aprobar un proyecto de esta envergadura quiero ver una evaluación económica que demuestre que podemos pagarlo y operarlo, y no solo comprarlo».

> Este documento es el resultado de seis meses de levantamiento en los pantalanes, en el varadero, en la torre de control, en la escuela de vela y en las oficinas, en temporada alta y en invierno, y de treinta y una entrevistas.
>
> No es una especificación. Es la descripción, lo más honesta que el CLIENTE ha sido capaz de hacer, de una operación real con sus datos, sus dolores, sus contradicciones internas y sus vacíos. Traducir esto en requerimientos es el trabajo del PROPONENTE, y es precisamente lo que se evalúa.

## CAPÍTULO 2 · LA COMPAÑÍA

### 2.1 Identificación

| Antecedente | Detalle |
|---|---|
| Razón social | Marina y Club Náutico Bahía Panitao S.A. |
| Giro | Explotación de un puerto deportivo: arriendo de amarras, invernada en seco, varadero y servicios técnicos, expendio de combustible, escuela de vela y servicios de club. |
| Condición | Sociedad anónima cerrada titular de una concesión marítima sobre el sector de playa y fondo de mar que ocupa, vigente hasta 2044, con obligaciones de conservación y de uso. |
| Ubicación | Seno de Reloncaví, comuna de Puerto Montt, Región de Los Lagos. |
| Inicio de operaciones | 1998. Ampliación de pantalanes en 2009 y del varadero en 2016. |
| Calificación | Recinto portuario deportivo sujeto a la fiscalización de la autoridad marítima. No es instalación portuaria comercial. |
| Ingresos anuales | $ 4.200 millones. |
| Propiedad | 62 % de una sociedad de inversiones familiar; 38 % distribuido entre 96 socios accionistas, la mayoría de ellos también armadores con amarra en la marina. |

> La doble condición de la propiedad no es un dato menor. Treinta y ocho por ciento de los accionistas son a la vez clientes con contrato de amarra, y varios de ellos son socios del club con derecho a voz en la asamblea. Toda decisión que afecte tarifas, cobranza, acceso o control tiene, en esta empresa, una lectura societaria además de una comercial.

### 2.2 Cifras de la operación

| Indicador | Valor |
|---|---|
| Amarras en el agua | 320, distribuidas en 5 pantalanes y un muelle de espera y visitas |
| Esloras que admite | Desde 7 hasta 28 metros |
| Embarcaciones con contrato permanente de amarra | 296 |
| Puestos de invernada en seco | 180, con 152 ocupados en el invierno 2026 |
| Boyas de fondeo en Bahía Ilque | 40, a 6 millas náuticas por mar y 22 km por camino de ripio |
| Recaladas de embarcaciones visitantes al año | ≈ 1.900 |
| Zarpes tramitados al año | ≈ 4.800; hasta 90 en un fin de semana largo de enero |
| Movimientos de travelift al año | 1.150, con el 62 % concentrado en dos campañas de seis semanas |
| Combustible expendido al año | 1.900.000 litros, entre petróleo y gasolina |
| Socios del club | 1.240 personas |
| Alumnos de la escuela de vela al año | 640, de los cuales 470 son menores de 18 años |
| Regatas y eventos náuticos al año | 14; el mayor reúne 120 embarcaciones y hasta 800 personas en el recinto |
| Empresas contratistas registradas para trabajar en el varadero | 62, con ≈ 140 personas |
| Temporada alta | 15 de noviembre al 31 de marzo. Concentra el 68 % de la actividad del año |

### 2.3 Instalaciones y equipamiento

| Elemento | Cantidad | Observación |
|---|---|---|
| Pantalanes flotantes | 5 | Estructuras flotantes que suben y bajan con la marea, con torretas de agua y electricidad. El cableado trabaja a la flexión permanente, en ambiente salino. |
| Amarras por tramo de eslora | 68 / 74 / 62 / 48 / 40 | De 8 a 10 m, de 10 a 12 m, de 12 a 15 m, de 15 a 18 m y de 18 a 22 m, respectivamente. |
| Muelle de espera y visitas | 28 puestos | Hasta 28 m de eslora. Es donde atraca una embarcación que llega sin reserva. |
| Torretas de servicio en pantalán | 168 | Cada torreta sirve a dos amarras. Sin medición individual de agua ni de energía. |
| Travelift | 1, de 75 toneladas | Único equipo de izaje mayor. Si se detiene, se detiene toda la campaña de varada. |
| Grúa de pluma | 1, de 12 toneladas | Para embarcaciones menores y desarbolado de mástiles. |
| Puestos de trabajo en el varadero | 14 | Donde trabajan las empresas contratistas. Pintura, fibra, motores, velas y electrónica. |
| Surtidor de combustible | 2 mangueras | Estanques de 30.000 litros de petróleo y 12.000 de gasolina. Recinto sujeto a normativa de almacenamiento de combustibles. |
| Embarcaciones de la escuela de vela | 24 menores y 2 semirrígidos de apoyo | Las menores no llevan radio ni energía a bordo. |
| Embarcación de servicio de la marina | 1 | Con la que se inspeccionan las boyas de Bahía Ilque dos veces por semana. |
| Cámaras de videovigilancia | 38 | En accesos, varadero, surtidor y cabezas de pantalán. No cubren la extensión de los pantalanes. |
| Estación meteorológica propia | 1 | Instalada en 2011. Registra viento y presión; el dato no se almacena ni se publica. |

### 2.4 Las personas

| Categoría | Dotación | Régimen |
|---|---|---|
| Personal propio en temporada baja | 39 | Jornada ordinaria, con turnos en torre de control y control de acceso. |
| Personal propio en peak de temporada alta | hasta 78 | La diferencia son trabajadores de temporada contratados de noviembre a marzo. |
| Marineros de pantalán | 9, hasta 19 en temporada | Reciben embarcaciones, dan y toman amarras, asisten maniobras. Más de la mitad del refuerzo de temporada es personal nuevo cada año. |
| Torre de control y radio | 4, hasta 6 en temporada | Turnos. Escucha permanente de radio y tramitación de zarpes. |
| Varadero y travelift | 6, hasta 9 en temporada | Dos operadores habilitados de travelift, uno de ellos con ocho meses de antigüedad. |
| Surtidor de combustible | 2, hasta 4 en temporada | Personal con habilitación específica para manipulación de combustibles. |
| Escuela de vela | 2 permanentes, hasta 9 en temporada | Monitores contratados por temporada, con certificación deportiva vigente exigible. |
| Administración, socios, contratos y cobranza | 5, hasta 7 en temporada | Jornada ordinaria. |
| Mantenimiento de instalaciones | 4, hasta 5 en temporada | Pantalanes, torretas, redes de agua y energía, y obras menores. |
| Control de acceso y seguridad | 5, hasta 7 en temporada | 24×7, parcialmente subcontratado. |
| Gerencia y comercial | 2 | Jornada ordinaria. |
| Área de tecnologías de información | ninguna | No existe. Un proveedor externo atiende a solicitud, con dos visitas mensuales de cuatro horas. |

> **La compañía no tiene personal de tecnologías de información. No es una dotación reducida: es cero.** Toda función que hoy suponga la existencia de un administrador de sistemas, de un responsable de respaldos, de un encargado de accesos o de un enlace técnico con proveedores no tiene hoy a quién asignarse. El PROPONENTE debe hacerse cargo de esta condición en la arquitectura, en el modelo de operación y, sobre todo, en el costo del período de 36 meses.

## CAPÍTULO 3 · EL RECINTO Y SUS ZONAS

La marina ocupa unas nueve hectáreas de borde costero más el espejo de agua concesionado. Aquí conviven en el mismo lugar una operación marítima, un taller pesado, un expendio de combustibles, una escuela con niños y un club social. Cada zona tiene reglas y usuarios distintos, y varias de ellas flotan.

| Zona | Qué ocurre allí | Condiciones relevantes |
|---|---|---|
| Pantalanes A a E | Amarre permanente, conexión a agua y energía, embarque y desembarque de tripulaciones. | Estructuras flotantes que suben y bajan con la marea. Superficie mojada y resbaladiza. Cableado a la flexión permanente y a la salinidad. |
| Muelle de espera y visitas | Recepción de embarcaciones visitantes, espera de maniobra, atraque de paso. | Es el primer punto de contacto de quien llega. En temporada se ocupa por completo un viernes por la tarde. |
| Torre de control | Escucha de radio, coordinación de maniobras, tramitación de zarpes y recepción de avisos. | Opera con radio marítima como medio principal. Es el único punto desde el que se ve la entrada del canal. |
| Explanada de invernada en seco | Almacenamiento de embarcaciones fuera del agua durante el invierno. | 180 puestos sobre calzos. La posición condiciona el orden en que pueden botarse. |
| Varadero y foso del travelift | Varada y botadura de embarcaciones, y trabajos técnicos. | Cargas de hasta 75 t suspendidas, con personas alrededor. Los puntos de izaje son propios de cada casco. |
| Puestos de trabajo de contratistas | Trabajos de casco, pintura, motores, velas y electrónica ejecutados por empresas externas. | 62 empresas y ≈ 140 personas externas. Generan residuos peligrosos: pinturas, aceites y baterías. |
| Surtidor de combustible | Expendio de petróleo y gasolina a embarcaciones. | Recinto sujeto a normativa de combustibles, con restricciones de operación y de registro. |
| Bodega de residuos peligrosos | Acopio de aceites usados, aguas de sentina, envases y baterías antes de su retiro. | Su trazabilidad es una de las tres no conformidades de la auditoría ambiental. |
| Escuela de vela y rampa | Clases de vela y remo, con embarcaciones menores. | 470 menores de edad al año en el agua. Las embarcaciones menores no llevan radio ni energía. |
| Casa club y restaurante | Servicios a socios; restaurante operado por un concesionario. | El concesionario emite sus propios documentos y consume energía y agua de la marina. |
| Portería y estacionamiento | Control de acceso de personas y vehículos. 260 plazas. | Un mismo día ingresan socios, tripulantes, apoderados, contratistas, proveedores y visitas. |
| Campo de boyas de Bahía Ilque | 40 boyas de fondeo para desahogo de temporada y para embarcaciones en tránsito. | A 6 millas náuticas, sin energía, datos ni personal. Se inspecciona dos veces por semana desde el mar. |

---

# TÍTULO II
## LA OPERACIÓN TAL COMO ES HOY

## CAPÍTULO 4 · EL CICLO DE LA EMBARCACIÓN Y EL CICLO DEL SOCIO

Lo que sigue es la descripción del proceso tal como ocurre, no como debería ocurrir. Se entrega con este nivel de detalle porque de él dependen las decisiones de alcance, de arquitectura y de trazabilidad que el PROPONENTE deberá tomar.

Una marina parece un negocio simple: se arrienda un lugar en el agua. En realidad son cinco negocios distintos que comparten el mismo recinto, las mismas personas y el mismo mostrador: el arriendo de amarras, la invernada y el varadero, el expendio de combustible, la escuela de vela y el club. Cada uno tiene su propio ciclo y su propia regulación, y ninguno se entiende sin los demás.

### 4.1 El contrato de amarra y la asignación del puesto

Un armador contrata una amarra por un año, con tarifa mensual según el tramo de eslora. La contratación se hace en la oficina, con un contrato en papel que se firma en dos copias, y con la documentación de la embarcación: matrícula, seguro vigente y datos del armador.

Asignar la amarra no es trivial. Una embarcación de doce metros y cuatro de manga no cabe en cualquier puesto del tramo de doce a quince: depende de la manga del puesto, del calado disponible con marea baja, de la orientación al viento dominante y de si la embarcación es de vela o de motor. Esa asignación la hace hoy el jefe de operaciones marítimas mirando un plano plastificado que tiene sobre el escritorio, con las embarcaciones anotadas con lápiz graso.

El resultado es que el veintidós por ciento de las amarras contratadas está ocupado por una embarcación cuya eslora no corresponde al tramo que paga. Unas pagan de más y no lo saben; otras pagan de menos y ocupan un puesto que la marina podría estar vendiendo cuatro veces más caro. Hay noventa embarcaciones en lista de espera para esloras sobre quince metros.

Cuando una embarcación se va, el puesto queda libre y alguien de la lista de espera debería ocuparlo. Que eso ocurra depende de que la persona del plano plastificado se acuerde.

### 4.2 La llegada de una embarcación visitante

Una embarcación que no tiene contrato llega y llama por radio marítima cuando está a un par de millas de la entrada. Pide amarra.

En la torre contestan, preguntan eslora, manga y calado, y luego alguien tiene que averiguar si hay un puesto disponible que sirva. Eso significa mirar el plano, llamar por radio a los marineros de pantalán para que confirmen que la amarra que se creía libre efectivamente lo está, y volver a la radio.

El proceso toma once minutos en promedio. Once minutos en los que una embarcación de quince metros está dando vueltas frente a la entrada, muchas veces con viento, a veces con una tripulación que lleva doce horas navegando y a veces de noche.

Las reservas anticipadas llegan por correo electrónico, por teléfono, por radio y por mensaje directo en redes sociales. No hay un registro común: cada canal termina en un cuaderno, en una bandeja de entrada o en la memoria de quien atendió.

El nueve por ciento de las recaladas de visitantes no queda registrado como servicio facturable. Nadie sabe si es porque el marinero no alcanzó a informarlo, porque la embarcación se fue antes de pasar por la oficina, o porque alguien decidió no cobrarle a un conocido.

### 4.3 La salida a navegar y el zarpe

Una embarcación deportiva no sale a navegar sin autorización de la autoridad marítima. El zarpe exige acreditar la matrícula vigente de la embarcación, el título del patrón, la nómina de las personas a bordo, el destino y la duración estimada del viaje, y el equipo de seguridad reglamentario.

La marina no otorga el zarpe —eso es facultad de la autoridad—, pero es donde el trámite ocurre. El armador llega al mostrador de la torre de control, entrega o dicta sus datos, y alguien completa el formulario. Cuatro mil ochocientas veces al año.

Cada trámite toma dieciocho minutos. El treinta y cuatro por ciento requiere corregir a mano al menos un dato: un certificado que venció, una nómina que cambió porque a última hora se bajó un tripulante, un título que el patrón no trae encima.

El fin de semana largo de enero se tramitan hasta noventa zarpes, casi todos entre las siete y las once de la mañana del viernes y del sábado. La fila llega a la puerta y sale al pantalán.

Toda la información que se entrega en ese trámite —quién es el armador, qué embarcación es, qué certificados tiene, quién es el patrón— ya está, en su mayor parte, en el contrato de amarra firmado hace años. Nadie la reutiliza porque nadie vive en una carpeta de papel.

### 4.4 El regreso, y la ausencia de regreso

Aquí está el vacío más incómodo de toda la operación: la marina no registra el regreso de las embarcaciones.

Cuando una embarcación vuelve y se amarra, vuelve. Si el marinero de turno está cerca, la ve. Si no, no. No hay registro, no hay hora, no hay nada.

Eso significa que si una embarcación zarpó el viernes con destino a los fiordos y volvió el domingo, la marina no lo sabe con certeza. Y si no volvió, tampoco.

El jefe de operaciones marítimas lo describió sin adornos: «si mañana un familiar me llama y me pregunta si el velero de su padre está en su amarra, yo tengo que mandar a alguien a caminar el pantalán a mirar. Eso es lo que tengo hoy».

Buena parte de las embarcaciones que zarpan de esta marina en verano se van a navegar el Seno de Reloncaví y los canales del sur. En esa zona no hay cobertura de telefonía móvil durante días. Las tripulaciones que quieren dejar constancia de su plan de navegación lo hacen dejando un papel escrito en la torre, y algunos avisan por radio cuando pasan cerca de un punto con cobertura. Ese papel se guarda en una carpeta y no se revisa.

### 4.5 El aviso de marejada

La autoridad marítima emite avisos de marejadas con anticipación variable, típicamente entre veinticuatro y cuarenta y ocho horas. El aviso llega por los canales oficiales a la torre de control.

A partir de ahí, el protocolo de la marina exige tres cosas: reforzar amarras en los puestos más expuestos, evaluar el retiro del agua de embarcaciones en riesgo, y avisar a los armadores para que vengan o autoricen que se intervenga su embarcación.

Las dos primeras las hace el personal. La tercera se hace llamando por teléfono, uno por uno, desde una planilla.

En el episodio del 8 de julio de 2026 se contactó efectivamente a ciento noventa de doscientos noventa y seis armadores. El cuarenta y siete por ciento de los contratos vigentes tiene al menos un dato de contacto obsoleto. Y no existe registro de a quién se llamó, a qué hora, con qué resultado y qué instrucción dejó.

Un aviso de marejada también cancela faenas: se suspende el travelift, se suspende el expendio de combustible y se suspenden las clases de la escuela. Eso significa que cualquier actividad programada en la marina puede caerse con treinta y seis horas de aviso, varias veces al año, sin que nadie pueda hacer nada al respecto.

### 4.6 La campaña de varada y la invernada

Entre abril y mayo, la mayoría de las embarcaciones sale del agua para pasar el invierno en la explanada. Entre septiembre y noviembre vuelven a entrar. El sesenta y dos por ciento de los mil ciento cincuenta movimientos anuales del travelift ocurre en esas dos campañas de seis semanas.

Cada movimiento se agenda por teléfono. La agenda es un cuaderno de doble página con las horas de la semana. Cuando una varada se atrasa —y se atrasa, porque una embarcación llegó tarde, porque el viento no permitió la maniobra o porque hubo que esperar la marea— se corre a lápiz todo lo que viene detrás y se llama a los afectados.

La maniobra en sí toma setenta y cuatro minutos en promedio y ocupa a tres personas. Lo delicado no es el tiempo: es dónde se ponen las eslingas. Cada embarcación tiene puntos de izaje específicos, y ponerlas mal significa aplastar una hélice de eje saliente, un transductor o una quilla de bulbo.

Esa información no está escrita en ninguna parte. Está en la memoria de dos personas, y una de ellas lleva veintidós años en la marina.

En cinco años ha habido cuatro siniestros con daño a embarcaciones durante maniobra, por noventa y seis millones de pesos cubiertos por el seguro. La prima subió en la última renovación y la aseguradora pidió, sin exigirlo todavía, un plan de izaje documentado por embarcación.

Una vez en tierra, la embarcación se ubica en un puesto de la explanada. Dónde se pone determina en qué orden podrá salir: una embarcación al fondo no puede botarse antes que las tres que tiene delante. Esa decisión también la toma una persona mirando la explanada.

### 4.7 El varadero y las empresas contratistas

Mientras la embarcación está en tierra, su propietario contrata trabajos: pintura de casco, mantención de motor, reparación de velas, electrónica. Esos trabajos los ejecutan empresas externas, no la marina. Hay sesenta y dos empresas registradas y alrededor de ciento cuarenta personas que entran a trabajar al recinto.

La marina les cobra un derecho de trabajo en el varadero y les exige acreditación: iniciación de actividades, seguro de accidentes, elementos de protección personal y, para ciertos trabajos, autorizaciones específicas. La verificación se hace mirando carpetas en la portería. Al día de la última revisión interna, sólo el cuarenta y uno por ciento de las empresas tenía su documentación completa y vigente.

Estos trabajos generan residuos peligrosos: restos de pintura antiincrustante que se lija del casco, aceites usados, solventes, envases contaminados y baterías. La marina los recibe en su bodega y los entrega a un gestor autorizado.

Lo que la marina no puede hacer es decir qué embarcación generó qué. El residuo llega a la bodega en tambores comunes. Cuando el auditor ambiental preguntó cuántos kilos de residuo de pintura generó cada embarcación varada esa temporada y a qué destino final fueron, la respuesta fue que no se sabe.

Esa es la primera de las tres no conformidades.

### 4.8 El surtidor de combustible

El surtidor expende un millón novecientos mil litros al año. La embarcación se acerca, un operador habilitado carga, anota el volumen en una boleta y el cargo se lleva al mostrador o se cobra en el momento.

El control de existencias se hace por varillaje del estanque, una vez al día. La diferencia entre lo que dice el varillaje y lo que dice la suma de las boletas se atribuye a la temperatura, a la evaporación y al error de medición, y no se investiga.

El expendio se suspende con viento sobre cierto umbral y con aviso de marejada. Esa suspensión no queda registrada, de modo que tampoco se sabe cuántas horas al año el surtidor estuvo cerrado ni cuánta venta se dejó de hacer.

### 4.9 La escuela de vela

Seiscientos cuarenta alumnos al año, de los cuales cuatrocientos setenta son menores de dieciocho años. Los cursos duran ocho semanas y se concentran en verano. Los monitores son personal de temporada con certificación deportiva vigente exigible.

La matrícula se hace en la oficina, con una ficha de papel donde el apoderado firma la autorización, declara condiciones de salud relevantes y deja un teléfono de emergencia. Esa ficha se archiva.

Cada clase empieza con una hoja de asistencia que se firma en la mañana. Después la hoja se queda en la caseta de la escuela y la clase sale al agua. Si un alumno se retira antes, o si un apoderado lo retira, eso se anota en la portería, en un cuaderno distinto que la escuela no revisa.

No hay registro de qué alumno salió en qué embarcación, con qué monitor, a qué hora ni con qué condiciones de viento. Cuando la clase vuelve, se cuentan las embarcaciones.

El 12 de enero de 2026 el recuento no cuadró y tomó cuarenta minutos establecer que el alumno faltante nunca había salido al agua. Nadie estuvo en peligro. El centro de padres envió una carta y la aseguradora de la escuela pidió los registros de asistencia y de autorización; encontró una hoja firmada en la mañana.

### 4.10 Las boyas de Bahía Ilque

A seis millas náuticas hay un campo de cuarenta boyas de fondeo que la marina mantiene para desahogar la temporada y para embarcaciones en tránsito. No tiene energía, no tiene datos y no tiene personal.

Saber qué boya está ocupada y por quién depende de que alguien lo vea. Una embarcación de servicio recorre el campo dos veces por semana, anota lo que ve en una libreta y lo informa al volver.

Las boyas y su tren de fondeo —cadena, grillete, muerto— tienen una vida útil y un programa de inspección que se lleva en una planilla. Dos boyas se han soltado en los últimos cuatro años. En ninguno de los dos casos había registro de la última inspección de ese tren específico.

### 4.11 La facturación, la cobranza y las embarcaciones abandonadas

Cada mes hay que emitir la facturación de doscientas noventa y seis amarras, ciento cincuenta y dos invernadas, los movimientos de travelift del período, los derechos de varadero de las contratistas, las recaladas de visitantes, las cuotas de los socios y los cursos de la escuela.

Dos personas dedican cinco días al mes a armar esa facturación, reuniendo cuadernos, boletas del surtidor, hojas de varadero y anotaciones de pantalán. El seis por ciento de los documentos emitidos termina en nota de crédito por error.

El once por ciento de los contratos está en mora. La deuda acumulada asciende a doscientos catorce millones de pesos.

El caso extremo son catorce embarcaciones abandonadas: sus propietarios dejaron de pagar y dejaron de responder, con veintiséis meses de deuda promedio. Ocupan amarras que la marina no puede arrendar, no puede mover sin autorización y no puede rematar sin un procedimiento legal que nadie ha iniciado. Cuatro de ellas están en tramos de eslora con lista de espera.

### 4.12 El agua y la energía de los pantalanes

Cada torreta de pantalán entrega agua y electricidad a dos amarras. Las torretas no tienen medición individual. La marina paga la cuenta total al distribuidor y la recupera de los armadores mediante un cargo fijo mensual según el tramo de eslora.

El resultado es que el treinta y ocho por ciento de lo que la marina paga no lo recupera. La diferencia la asume la marina y crece cada invierno, porque una embarcación habitada o con calefacción consume mucho más que una que está cerrada, y las dos pagan lo mismo.

Para efectos ambientales el problema es otro: como no hay medición por amarra, el indicador de consumo por embarcación que exige el esquema de certificación se calcula prorrateando un solo medidor por eslora. El auditor lo objetó. Esa es la segunda no conformidad.

## CAPÍTULO 5 · LOS SISTEMAS QUE EXISTEN HOY

El PROPONENTE deberá integrarse a este panorama. La columna de destino indica la decisión ya tomada por el CLIENTE; donde dice «decisión del proponente», la decisión no está tomada y debe fundamentarse en la propuesta.

| Sistema | Función | Destino |
|---|---|---|
| Sistema de administración de socios y cobranza, adquirido en 2014 | Padrón de socios, contratos de amarra, emisión de cobros y estado de cuenta. Instalado en un computador de la oficina de administración. | Se reemplaza. El proveedor que lo vendió dejó de operar en 2021: no hay soporte, no hay actualizaciones y no hay documentación. Una sola persona sabe ejecutar el cierre mensual. |
| Sistema contable y de facturación electrónica | Contabilidad y emisión de documentos tributarios electrónicos. | Se mantiene. Es el único emisor de documentos tributarios. La solución le entrega los hechos facturables. |
| Planilla del plano de amarras | No existe como sistema. La asignación de puestos vive en un plano plastificado anotado con lápiz graso. | Desaparece. Es el punto de partida del 22 % de amarras mal asignadas. |
| Cuaderno de agenda del travelift | Programación de varadas y botaduras. | Desaparece. |
| Carpetas de contratos y de matrículas | Contratos de amarra en papel, con la documentación de la embarcación y del armador. | Se digitalizan. Son la fuente que hoy no se reutiliza en la tramitación del zarpe. |
| Registro de zarpes | Formularios de la autoridad marítima completados en el mostrador. | El trámite y su formato son de la autoridad y no se alteran. Lo que se pide es que la marina deje de digitar desde cero lo que ya tiene. |
| Sistema de control de acceso y videovigilancia | 38 cámaras y control de barrera en portería, con credenciales de socios y de contratistas. | Se mantiene el equipamiento. Su integración con la habilitación de contratistas y con el registro de personas en el recinto es parte del alcance. |
| Sistema del surtidor | Bomba con totalizador mecánico y boletas manuales. | Decisión del PROPONENTE: puede automatizarse la captura del despacho o mantenerse el registro manual con controles compensatorios, con justificación técnica y económica. |
| Sitio web y redes sociales | Información institucional. Las consultas y reservas llegan por mensaje directo. | Se reemplaza el sitio y se incorpora el portal exigido en el Capítulo 15. |
| Correo electrónico, cuadernos y planillas | Reservas de visitantes, avisos de marejada, asistencia de la escuela de vela, inspección de boyas, control de residuos, acreditación de contratistas y cierre de caja. | Deben desaparecer como sistema de registro. Ese es, en buena medida, el objeto de esta licitación. |

> El sistema de 2014 no tiene proveedor desde 2021, corre sobre un sistema operativo fuera de soporte y no tiene documentación de su modelo de datos. Contiene doce años de contratos, de historia de pagos y del registro de embarcaciones, incluida la información de las catorce embarcaciones abandonadas que la marina necesitará para cualquier acción de cobranza. Extraer esa información es una tarea de migración cuya complejidad el PROPONENTE debe dimensionar, sin poder consultar a nadie que conozca el sistema por dentro.

## CAPÍTULO 6 · CONECTIVIDAD, SEGURIDAD Y CONDICIONES DEL SITIO

| Elemento | Situación actual |
|---|---|
| Enlace de datos del recinto | Fibra óptica de un proveedor hasta el edificio de administración, sin respaldo contratado. Un corte deja al recinto completo sin datos y sin telefonía fija. |
| Sala de equipos | Un armario de 12 U en la oficina de administración, con un conmutador, el servidor del sistema de 2014 y el grabador de las cámaras. Sin climatización dedicada, sin respaldo de energía más allá de una unidad de 15 minutos y con acceso por la misma puerta que usa el personal. |
| Respaldos | Un disco externo que una persona conecta los viernes, cuando se acuerda. La última verificación de que un respaldo se puede restaurar no está registrada. |
| Red inalámbrica | Un punto de acceso en la casa club y otro en administración. Los pantalanes no tienen cobertura de datos. La red es única: socios, administración, cámaras y el sistema de 2014 comparten el mismo segmento. |
| Cobertura de telefonía móvil | Buena en tierra. Irregular en los pantalanes exteriores y en el campo de boyas de Bahía Ilque. |
| Radio marítima | Es el medio de comunicación real de la operación. Torre, marineros de pantalán, embarcación de servicio y las embarcaciones se coordinan por radio, con escucha permanente en la torre. |
| Ambiente salino y estructuras móviles | Los pantalanes suben y bajan varios metros con la marea y se mueven con el oleaje. Todo cableado que llegue a ellos trabaja a la flexión de forma permanente y en atmósfera marina. Es la causa habitual de falla de las instalaciones de pantalán. |
| Energía | Alimentación desde la red pública. Sin generación de respaldo. Un corte de energía deja sin agua a los pantalanes, porque el suministro depende de una bomba. |
| Zona de combustibles | Recinto clasificado con restricciones para la instalación de equipamiento eléctrico y electrónico. Cualquier dispositivo a instalar allí debe acreditar su idoneidad para esa clasificación. |
| Condiciones del trabajo en pantalán | Superficie flotante, mojada y resbaladiza, con lluvia buena parte del año, manos mojadas y frecuentemente con guantes. El marinero trabaja con una mano en un cabo y la radio en la otra. |
| Condiciones del trabajo en el travelift | Maniobra de una carga de hasta 75 toneladas suspendida en eslingas, con personas guiando a ambos lados. El operador no puede apartar la vista de la carga. |
| Condiciones del trabajo de la escuela de vela | Monitores a bordo de un semirrígido, mojados, con radio portátil. No hay dispositivo que sobreviva de forma confiable a esa exposición sin una especificación adecuada. |

> La compañía ha sido explícita en cuatro puntos. Primero: nada de lo que se proponga puede retrasar una maniobra de amarre ni una maniobra de travelift; en ambas hay personas junto a cargas y cabos en tensión. Segundo: la radio marítima seguirá siendo el medio de coordinación operacional y la solución debe convivir con ella, no pretender sustituirla. Tercero: la operación del recinto no puede detenerse porque se cayó el enlace de datos. Cuarto: cualquier equipamiento que se instale en los pantalanes, en la zona de combustibles o en el campo de boyas debe acreditar que resiste las condiciones descritas y tener su plan de reposición costeado.

## CAPÍTULO 7 · LO QUE DUELE: INDICADORES DEL PROBLEMA

Los siguientes datos corresponden al ejercicio 2025 y a la temporada 2025-2026, y provienen de los registros de la compañía. Se entregan porque dimensionan el problema y porque el PROPONENTE deberá comprometer mejoras verificables sobre ellos.

### 7.1 Amarras, visitantes y ocupación

| Indicador | Valor 2025 | Referencia |
|---|---|---|
| Ocupación media anual de amarras | 84 % | sobre 92 % |
| Ocupación en temporada alta | 98 % | — |
| Embarcaciones en lista de espera para eslora sobre 15 m | 90 | — |
| Amarras ocupadas por una eslora que no corresponde al tramo contratado | 22 % | cero |
| Tiempo medio para asignar amarra a un visitante que llama por radio | 11 minutos | bajo 1 minuto |
| Recaladas de visitantes no registradas como servicio facturable | 9 % | cero |
| Canales por los que se reciben reservas de visitantes, sin registro común | 4 | 1 |
| Boyas de Bahía Ilque con estado de ocupación conocido en tiempo real | 0 de 40 | 40 |
| Trenes de fondeo con registro de su última inspección | parcial, en planilla | completo y trazable |

### 7.2 Seguridad de la navegación y de las personas

| Indicador | Valor 2025 |
|---|---|
| Zarpes tramitados al año | ≈ 4.800; hasta 90 en un fin de semana largo |
| Tiempo medio de tramitación de un zarpe en el mostrador | 18 minutos |
| Zarpes que requieren corregir a mano al menos un dato | 34 % |
| Registro del regreso de una embarcación a su amarra | inexistente |
| Capacidad de responder si una embarcación determinada está en su amarra | requiere que alguien camine el pantalán y mire |
| Planes de navegación dejados en la torre que se revisan después | ninguno; se archivan en una carpeta |
| Armadores contactados efectivamente en el aviso de marejada del 8 de julio de 2026 | 190 de 296, equivalente al 64 % |
| Contratos vigentes con al menos un dato de contacto obsoleto | 47 % |
| Evidencia del aviso de marejada entregable al seguro y a la autoridad | inexistente |
| Tiempo que tomó establecer si un alumno estaba en el agua el 12 de enero de 2026 | 40 minutos |
| Registro de qué alumno navega en qué embarcación y con qué monitor | inexistente; sólo hoja de asistencia firmada en la mañana |
| Menores de edad que navegan en la escuela cada año | 470 |

### 7.3 Varadero, contratistas y medio ambiente

| Indicador | Valor 2025 | Referencia |
|---|---|---|
| Movimientos de travelift al año | 1.150 | — |
| Concentración en dos campañas de seis semanas | 62 % del total | — |
| Duración media de un ciclo de varada | 74 minutos, con 3 personas | — |
| Embarcaciones con plan de izaje documentado | 0 de 296 | 296 |
| Siniestros con daño a embarcación en maniobra, últimos 5 años | 4, por $ 96 millones | cero |
| Empresas contratistas con acreditación documental completa y vigente | 41 % de 62 | 100 % |
| Trazabilidad de residuos peligrosos por embarcación generadora | inexistente | completa |
| Derrames menores registrados en el año | 7, de los cuales 2 con acta y seguimiento | 7 de 7 |
| Amarras con medición individual de agua y energía | 0 de 320 | 320 |
| Consumo de servicios pagado a la distribuidora y no recuperado de los armadores | 38 % | bajo 5 % |
| No conformidades abiertas de la auditoría de certificación ambiental | 3 | cero, a la temporada 2029 |

### 7.4 Administración y tecnología

| Indicador | Valor 2025 |
|---|---|
| Personas dedicadas a tecnologías de información | ninguna |
| Años que lleva el sistema principal sin proveedor ni soporte | 5, desde 2021 |
| Personas capaces de ejecutar el cierre mensual del sistema | 1 |
| Duración del cierre mensual | 9 días |
| Días-persona al mes dedicados a armar la facturación | 10, entre 2 personas |
| Documentos emitidos que terminan en nota de crédito por error | 6 % |
| Contratos de amarra en mora | 11 % |
| Deuda acumulada | $ 214 millones |
| Embarcaciones abandonadas, con deuda y sin propietario que responda | 14, con 26 meses de deuda promedio |
| De ellas, ubicadas en tramos de eslora con lista de espera | 4 |
| Última verificación registrada de que un respaldo puede restaurarse | no existe registro |
| Segmentos de red que separan socios, administración, cámaras y sistemas | ninguno; la red es única |

> Ninguno de estos indicadores se resuelve comprando software. Esta es una empresa pequeña que administra bienes ajenos de alto valor, hace navegar a cuatrocientos setenta niños al año, expende combustible, recibe residuos peligrosos y depende del clima para poder trabajar. El PROPONENTE que entienda que aquí el producto no es una amarra sino una custodia —de una embarcación, de una persona y de un compromiso ambiental— y que además debe operarse durante treinta y seis meses en una organización sin ninguna persona de informática, tendrá una ventaja evidente sobre quien ofrezca módulos.

---

# TÍTULO III
## LO QUE DICEN QUIENES OPERAN

## CAPÍTULO 8 · ENTREVISTAS DE LEVANTAMIENTO

Las siguientes son transcripciones editadas de las entrevistas de levantamiento sostenidas entre febrero y julio de 2026, en temporada alta y en invierno. Se entregan con sus contradicciones intactas, porque las contradicciones son parte del problema.

El PROPONENTE debe leerlas como lo que son: la palabra de personas que conocen muy bien su parte de la operación y que no tienen por qué conocer la de los demás, ni tienen por qué saber de sistemas. Distinguir el hecho de la opinión, la necesidad del capricho y el problema de la solución que la persona ya se imaginó es parte del trabajo profesional que se está licitando.

> **Ximena Bassa Undurraga** · Gerenta General
>
> Voy a partir por lo que el directorio quiere oír y ustedes probablemente no. Esta empresa factura cuatro mil doscientos millones al año, tiene treinta y nueve personas en invierno y no tiene ni una sola dedicada a informática. Cualquier propuesta que suponga que aquí hay alguien que va a administrar un sistema está mal hecha desde la primera página.
>
> Dicho eso, tenemos tres problemas que ya no podemos seguir postergando. Uno es que no puedo demostrar lo que hago. Avisamos la marejada y no lo puedo probar. Eso me costó un reclamo, una discusión con el seguro y una pregunta incómoda de la autoridad marítima.
>
> El segundo es la escuela. Cuarenta minutos sin saber si un niño estaba en el agua. No pasó nada y esa es la parte que me tiene despierta: no pasó nada porque tuvimos suerte, no porque tuviéramos procedimiento.
>
> El tercero es la plata. Tengo un veintidós por ciento de amarras ocupadas por embarcaciones que no corresponden al tramo que pagan, un treinta y ocho por ciento de la cuenta de luz que no recupero, catorce barcos abandonados que ocupan amarras que tengo con lista de espera, y doscientos catorce millones de deuda. Ninguna de esas cuatro cosas es un problema tecnológico y las cuatro se explican porque no tengo información.
>
> Y una advertencia sobre el voto de minoría del directorio, que pedí que quedara en el acta: van a evaluar la propuesta económica con lupa. No basta con que la solución sea buena. Tiene que ser una solución que una empresa de este tamaño pueda pagar y, sobre todo, operar durante tres años.

> **Cap. (r) Ernesto Quilodrán Vera** · Jefe de Operaciones Marítimas y Torre de Control
>
> Mi trabajo es que la gente salga y vuelva. Todo lo demás es administración.
>
> Y hoy tengo un agujero que me avergüenza: registro las salidas y no registro los regresos. Cuatro mil ochocientos zarpes al año y ni uno solo tiene su contrapartida. Si mañana me llaman de una familia a preguntar si el velero está en su amarra, mando a alguien a caminar el pantalán y a mirar. En 2026.
>
> En verano la mitad de las embarcaciones que zarpan de aquí se van a los canales. Allá no hay señal por días. Algunos me dejan un plan de navegación escrito en un papel; yo lo guardo en una carpeta y nadie lo revisa. Si un plan dice que volvía el jueves y hoy es domingo, no hay nada ni nadie que levante la mano.
>
> Lo que yo necesito es simple de decir y por lo visto difícil de hacer: saber quién salió, con quién a bordo, a dónde, hasta cuándo, y que alguien o algo me avise cuando ese plazo se venció sin noticias.
>
> De la asignación de amarras: yo tengo un plano plastificado y un lápiz graso, y funciona porque llevo once años acá. Pero cuando un visitante me llama a dos millas con viento, me demoro once minutos en darle un puesto, y en esos once minutos el tipo está dando vueltas frente a la entrada. Eso es una maniobra innecesaria y las maniobras innecesarias son donde ocurren los golpes.
>
> Última cosa, y es la que más me importa: la radio se queda. Ustedes propongan lo que quieran, pero el marinero del pantalán me habla por radio y me va a seguir hablando por radio, porque tiene las manos mojadas y un cabo en la otra.

> **Eleodoro Chávez Painén** · Operador de travelift, 22 años en la marina
>
> Yo levanto barcos de setenta toneladas con dos eslingas. Cuando el barco está en el aire, no miro nada más que el barco.
>
> Lo que la gente no entiende es que cada embarcación tiene su punto. Dónde van las eslingas depende del casco, de dónde está el eje, de si tiene bulbo, de si tiene transductor, de si el timón es colgado o de mecha. Si me equivoco por treinta centímetros, le aplasto la hélice o le quiebro el transductor, y esos son dos millones de pesos y un cliente enojado.
>
> Eso yo lo sé de memoria de casi todos los barcos de acá. Y el Manuel, que lleva ocho meses, no lo sabe todavía. Y en abril vamos a estar los dos sacando barcos de las siete de la mañana a las siete de la tarde, seis semanas seguidas, porque hay uno solo travelift y trescientos barcos que quieren salir el mismo mes.
>
> Si me van a hacer anotar algo antes de cada maniobra, dígamelo ahora: no lo voy a hacer con el barco en el aire. Después, con el barco en los calzos, sí.
>
> Lo que sí me serviría de verdad es que el barco llegue con la ficha lista. Que yo abra algo y diga: éste va con las eslingas a tres coma dos metros de la proa y a uno coma ocho de la popa, ojo con el transductor de babor. Eso me ahorra veinte minutos de andar preguntándole al dueño, que muchas veces tampoco sabe.
>
> Y de la agenda: es un cuaderno. Cuando se atrasa una varada, se corre todo a lápiz y hay que llamar a diez personas. En abril eso pasa todos los días.

> **Marisol Ovando Kuschel** · Jefa de la Escuela de Vela
>
> Cuatrocientos setenta menores de edad al año, en el agua, en el Reloncaví. Ese es mi número y con ese número parto todas las conversaciones.
>
> El 12 de enero contamos los botes al volver y faltaba uno. Cuarenta minutos hasta saber que el niño nunca había salido, porque la mamá lo retiró antes y lo avisó en la portería, en un cuaderno que yo no reviso. Nadie corrió peligro. Pero yo estuve cuarenta minutos sin poder responder una pregunta que se debería contestar apretando algo.
>
> Mi registro es una hoja de asistencia que se firma a las nueve de la mañana. A las once ya no dice la verdad: uno se fue, otro llegó tarde, tres se cambiaron de bote porque uno tenía la vela rota.
>
> Yo necesito tres cosas: saber quién está autorizado a navegar hoy, saber quién salió efectivamente y en qué bote y con qué monitor, y saber que volvieron todos. Y necesito que eso lo pueda hacer un monitor de temporada, contratado hace dos semanas, mojado, arriba de un semirrígido.
>
> Ahí está mi problema con la tecnología: mis monitores están mojados. Un teléfono común no dura una temporada acá. Y si me dicen que cada niño va a llevar un dispositivo, les digo de inmediato que no: son niños de nueve años en un Optimist que se da vuelta cuatro veces por clase.
>
> Y por favor no me propongan resolverlo con una cámara. Ya lo dijeron los papás en la reunión: nadie quiere que sus hijos estén filmados. Quieren saber que salieron y volvieron, que es otra cosa.

> **Nelson Cárcamo Aguilar** · Marinero de pantalán, 6 temporadas
>
> Yo trabajo con las manos mojadas, arriba de un pantalán que se mueve, con lluvia gran parte del año. En una mano tengo un cabo y en la otra la radio.
>
> Cuando llega un barco, lo primero es que no golpee. Después viene todo lo demás. Si en ese momento alguien me pide que saque un aparato del bolsillo, no lo voy a sacar, y si lo saco se me cae al agua. Ya se me cayó un teléfono el año pasado.
>
> Lo que sí puedo hacer es anotar después, cuando el barco quedó amarrado y me seco las manos. Pero tiene que ser algo de dos toques, no una pantalla con cinco cosas que llenar.
>
> En verano somos diecinueve y como diez somos nuevos cada temporada. La gente nueva no sabe qué barco es cuál, no conoce a los dueños y no sabe qué amarra está libre de verdad. Por eso preguntan todo por radio, y la radio se satura los viernes en la tarde.
>
> Si me preguntan qué me serviría: que yo pudiera ver en algo dónde poner al barco que viene entrando, sin tener que llamar a la torre y esperar. Y que cuando un dueño me pregunta si su barco está bien, yo pueda decirle algo más que «yo lo vi ayer».
>
> Ah, y una cosa que nadie pregunta: yo sé cuándo un barco está mal amarrado o tiene una defensa mala. Lo veo todos los días. No hay dónde dejar eso escrito, así que se lo digo al dueño si me lo encuentro.

> **Ítalo Bianchi Ruiz** · Encargado de Varadero y de Contratistas
>
> Tengo sesenta y dos empresas registradas y como ciento cuarenta personas que entran a trabajar acá. No son mis trabajadores. Yo no les mando, les cobro un derecho y les exijo papeles.
>
> Los papeles los revisamos en la portería mirando carpetas. La última vez que hicimos una revisión de verdad, cuarenta y uno por ciento tenía todo al día. El resto tenía algo vencido: un seguro, una iniciación de actividades, una autorización de trabajo en caliente.
>
> El auditor ambiental me preguntó cuántos kilos de residuo de pintura generó cada barco esa temporada. No tengo idea. El residuo llega a la bodega en tambores y adentro va lo de todos.
>
> Y ojo con una cosa: si ustedes me diseñan una aplicación para que los contratistas registren su residuo, no la van a usar. Son empresas chicas, algunos son maestros que trabajan solos, y no van a instalar nada. Lo que sí puedo hacer es no dejarlos entrar si no cumplen algo en la portería. Ahí sí tengo palanca.
>
> Del travelift: yo le pido a don Eleodoro que documente los puntos de eslingado desde hace cuatro años. Nunca ha pasado, y lo entiendo, porque en abril no hay tiempo ni para almorzar. Si eso no queda escrito de una forma que se pueda hacer en treinta segundos, no va a quedar escrito nunca.
>
> Y me falta algo básico: saber en qué orden están los barcos en la explanada. Hoy es mirar. Cuando en septiembre me piden botar el barco del fondo, hay que mover tres.

> **Paulina Agüero Mansilla** · Jefa de Administración, Socios y Cobranza
>
> Yo soy la única persona que sabe cerrar el sistema. Eso lo digo con vergüenza y no con orgullo. Si me enfermo la última semana del mes, no se factura.
>
> El sistema es del 2014 y el proveedor cerró el 2021. No hay a quién llamar. Está en un computador de esta oficina y lo respaldamos con un disco que conecto los viernes, cuando me acuerdo. Nunca hemos probado si ese respaldo sirve.
>
> Armar la facturación del mes me toma cinco días con dos personas: junto los cuadernos del travelift, las boletas del surtidor, las hojas del varadero, las anotaciones del pantalán y las reservas que llegaron por Instagram. Después emitimos, y un seis por ciento termina en nota de crédito porque algo estaba mal.
>
> Los catorce barcos abandonados son mi tema personal. Veintiséis meses de deuda promedio, dueños que no contestan, y cuatro de ellos están en amarras que yo tengo con lista de espera. No los puedo mover, no los puedo rematar y no los puedo arrendar.
>
> Yo quisiera bloquear el portón del pantalán a los morosos. Me han dicho que no se puede, que hay un tema legal y que además varios de esos morosos son accionistas de la empresa. Alguien tiene que zanjar eso, porque hoy la cobranza es llamar por teléfono y poner cara de pena.
>
> Y de la luz: pago la cuenta completa y recupero el sesenta y dos por ciento. El barco que vive con calefacción todo el invierno paga lo mismo que el que está cerrado desde marzo. Eso lo sabe todo el mundo y nadie lo arregla porque no hay medidores.

> **Rodrigo Vidal Ampuero** · Socio, accionista y armador. Navega los canales desde 1998
>
> Yo llevo veintiocho años saliendo de acá y me voy tres semanas a los canales cada verano. Voy a decir algo impopular: parte de lo que estoy comprando cuando pago una amarra es que nadie me esté mirando.
>
> Si me dicen que le van a poner un aparato a mi barco para saber dónde está, mi respuesta es no. Y no soy el único: en la asamblea eso se vota y se pierde.
>
> Ahora, hay una diferencia que a lo mejor ustedes ven y la marina no. Una cosa es que la marina sepa que mi barco salió y volvió, que me parece razonable y hasta necesario. Otra muy distinta es que la marina sepa dónde estoy mientras navego. Lo primero lo acepto. Lo segundo no.
>
> Y le voy a decir algo más: si yo pudiera dejar mi plan de navegación en algo, decir que salgo el viernes y vuelvo el jueves, y que si el jueves a las ocho de la noche no he dado señales alguien lo note, eso yo lo firmo hoy. Pero tiene que ser porque yo lo pedí, no porque me vigilan.
>
> Allá abajo no hay señal. Si algo me van a poner, tiene que funcionar mandando un mensaje corto cuando aparece un pedacito de cobertura o por el equipo satelital que ya llevo. No hay banda ancha en el Comau.
>
> Y de la marejada de julio: a mí sí me llamaron, y llegué a doblar amarras. Pero me consta que a varios no. Hay dos barcos al lado del mío cuyos dueños yo no he visto en dos años.

> **Sophie Berthier** · Directora de Operaciones, operadora internacional de charter
>
> Mantenemos catorce embarcaciones basadas aquí y operamos temporada de noviembre a marzo. Somos el veintidós por ciento de sus ingresos por amarra y probablemente el cliente más exigente que tienen.
>
> Nuestro problema no es la marina: es la información. Yo tengo tripulaciones que llegan de Europa un sábado a las seis de la mañana y necesito que la embarcación esté lista, con el combustible cargado, el agua llena, el chequeo hecho y la documentación en regla. Hoy eso lo coordino por correo con tres personas distintas y ninguna me confirma nada por escrito.
>
> Les pedimos tres cosas para la renovación. Reservar y contratar servicios en línea, sin correos. Una interfaz en inglés, porque mis clientes no hablan español y hoy dependen de que alguien les traduzca en el mostrador. Y facturación con el consumo real de cada embarcación, porque hoy me cobran un cargo fijo de electricidad que no tiene relación con lo que consumimos.
>
> Y una cuarta que puse en una línea al final de la carta: la certificación ambiental vigente. No es un gesto. Nuestros clientes corporativos y las agencias europeas con las que trabajamos nos la piden a nosotros, y nosotros se la pedimos a nuestros puertos base.
>
> Sobre plazo: la temporada 2029. No es un ultimátum, es el tiempo que tarda en renovarse nuestro contrato marco. Si para entonces no está, tendremos que basar la flota en otra parte, y no hay muchas alternativas en esta zona, lo cual es exactamente el motivo por el que preferiría que lo resolvieran.

> **Verónica Sandoval Millán** · Presidenta del Centro de Padres de la Escuela de Vela
>
> Le voy a hablar como mamá, que es lo que soy. Mi hija tiene once años y sale a navegar tres veces por semana en verano.
>
> Después de lo del 12 de enero nos juntamos con la escuela. No fuimos a reclamar: fuimos a preguntar cómo se controla. Y la respuesta fue una hoja que se firma en la mañana.
>
> Lo que pedimos es lo mínimo. Que quede claro quién autorizó a mi hija a navegar hoy, con qué monitor salió, y que yo pueda saber que volvió. Nada más que eso.
>
> Y quiero ser clara en lo que NO pedimos, porque en la reunión se propuso y lo rechazamos. No queremos cámaras filmando a los niños, no queremos que se publique dónde está cada uno, y no queremos que los niños anden con aparatos. Queremos saber que salió y volvió.
>
> También hay algo que nos incomoda a varios: en la ficha de matrícula nos piden datos de salud de los niños, alergias, medicamentos. Esa ficha hoy está en un archivador en una oficina que comparte llave con otras cosas. Si van a hacer un sistema, esa información tiene que estar mejor guardada de lo que está.
>
> Y una cosa práctica: la mitad de los apoderados retiramos a los niños antes de que termine la clase, porque los horarios no calzan con el trabajo. Eso hoy se anota en portería y la escuela no lo ve. Ese es el error del 12 de enero y va a volver a pasar.

> **Sobre las contradicciones.**
>
> El PROPONENTE habrá advertido que estas entrevistas no son consistentes entre sí. La torre de control necesita saber si una embarcación volvió y el armador se niega a que se sepa dónde está. La administración quiere bloquear el acceso a los morosos y varios morosos son accionistas de la empresa. La escuela de vela necesita saber quién está en el agua y los apoderados rechazan cámaras y dispositivos en los niños. El encargado de varadero necesita trazar los residuos de cada embarcación y advierte que los contratistas no instalarán ninguna aplicación. El operador del travelift no anotará nada con el barco en el aire, y el plan de izaje es exactamente lo que debe registrarse. La operadora de charter exige medición de consumo real y no hay un solo medidor por amarra. Y la gerente general recuerda que todo esto debe pagarlo y operarlo una empresa sin ninguna persona de informática.
>
> Estas tensiones son reales y no se resolverán antes de la adjudicación. Resolverlas —o, cuando no sea posible, proponer una arquitectura que permita convivir con ellas y dejar constancia de la decisión y de su costo— es parte de lo que se está licitando.

---

# TÍTULO IV
## LO QUE EL MANDANTE ESPERA

## CAPÍTULO 9 · EXPECTATIVAS DE NEGOCIO

Las siguientes son las expectativas del CLIENTE expresadas como resultados de negocio. Deliberadamente no están escritas como requerimientos. Traducirlas en requerimientos funcionales y no funcionales, priorizarlos, asignarlos a una etapa y hacerlos verificables es trabajo del PROPONENTE.

### 9.1 Que se sepa quién salió y quién volvió

El CLIENTE espera saber, en cualquier momento, qué embarcaciones están en su amarra, cuáles salieron, cuándo, con qué autorización y con quiénes a bordo, y espera que la ausencia de un regreso comprometido sea advertida por alguien o por algo, y no descubierta por un familiar que llama.

Espera lograrlo respetando una distinción que sus propios armadores plantearon con claridad: que la marina sepa que una embarcación salió y volvió es aceptable; que la marina sepa dónde está esa embarcación mientras navega, no lo es, salvo que el armador lo pida.

Esta es la primera expectativa y es la que originó la licitación.

### 9.2 Que un aviso de marejada se pueda demostrar

El CLIENTE espera que, ante un aviso de la autoridad, la notificación a los armadores ocurra en minutos y no en horas, por varios medios, con registro de a quién se avisó, cuándo, por qué canal, si acusó recibo y qué instrucción dejó.

Espera además que los datos de contacto de los contratos dejen de envejecer sin que nadie lo note.

### 9.3 Que se sepa quién está en el agua en la escuela de vela

El CLIENTE espera poder responder en segundos, y no en cuarenta minutos, quién de los cuatrocientos setenta menores está autorizado a navegar hoy, quién salió efectivamente, en qué embarcación, con qué monitor, y si volvió.

Espera lograrlo sin cámaras sobre los niños, sin dispositivos a bordo de las embarcaciones menores y sin depender de que un monitor de temporada, mojado y con las manos ocupadas, complete un formulario largo. Los apoderados fueron explícitos en los tres puntos.

### 9.4 Que cada amarra esté ocupada por la embarcación correcta

El CLIENTE espera que la asignación de puestos deje de depender de un plano plastificado y de la memoria de una persona, que la eslora, la manga y el calado de cada embarcación determinen dónde puede ir, y que un puesto que queda libre se ofrezca a la lista de espera sin que nadie tenga que acordarse.

### 9.5 Que una embarcación visitante reciba respuesta de inmediato

El CLIENTE espera que, cuando una embarcación llama por radio pidiendo amarra, la respuesta con el puesto asignado sea inmediata, y espera que las reservas anticipadas dejen de llegar por cuatro canales distintos que terminan en cuatro registros distintos.

Espera además que ninguna recalada quede sin cobrarse por no haber quedado registrada.

### 9.6 Que el zarpe deje de digitarse desde cero

El CLIENTE espera que la información que ya obra en su poder —la embarcación, sus certificados, el armador, los patrones habituales— se reutilice en la preparación del trámite, que la vigencia de los documentos se conozca antes de que el armador llegue al mostrador, y que la fila de las mañanas de fin de semana largo desaparezca.

El otorgamiento del zarpe es facultad de la autoridad marítima y no cambia. Lo que cambia es lo que la marina hace antes.

### 9.7 Que el varadero opere con un plan y no con memoria

El CLIENTE espera una programación de varadas y botaduras que se pueda reordenar cuando el clima obliga, que considere el orden físico de las embarcaciones en la explanada, y que cada embarcación tenga su plan de izaje registrado y disponible antes de la maniobra.

Espera que registrarlo tome segundos y ocurra cuando la embarcación ya está en los calzos, y no con la carga suspendida.

### 9.8 Que se pueda demostrar la gestión ambiental, no sólo afirmarla

El CLIENTE espera cerrar las tres no conformidades de la auditoría: trazar los residuos peligrosos desde la embarcación que los genera hasta el gestor autorizado que los recibe, medir el consumo de agua y energía por amarra, y acreditar la capacitación ambiental de las personas que trabajan en el varadero.

### 9.9 Que el consumo se cobre a quien lo consume

El CLIENTE espera dejar de absorber el treinta y ocho por ciento de la cuenta de servicios, y espera que la medición por amarra sirva simultáneamente para facturar y para el indicador ambiental, con una sola fuente de dato.

### 9.10 Que la cobranza deje de ser un llamado telefónico

El CLIENTE espera conocer el estado de cuenta de cada armador en tiempo real, que la mora se detecte y se gestione por sí sola en sus primeras etapas, y que la situación de las catorce embarcaciones abandonadas tenga un expediente completo y trazable que permita, cuando la compañía lo decida, iniciar la acción que corresponda.

### 9.11 Que la marina pueda operar sin un área de informática

El CLIENTE espera una solución que una organización sin personal de tecnologías de información pueda usar, mantener y controlar, y espera que todo lo que exija un especialista esté ofrecido como servicio y esté costeado por los treinta y seis meses.

Esta expectativa no es una más de la lista: condiciona a todas las anteriores.

## CAPÍTULO 10 · RESTRICCIONES NO NEGOCIABLES

Las siguientes condiciones no están en discusión. Una propuesta que no las respete será evaluada como falta de comprensión del caso.

| N° | Restricción |
|---|---|
| 1 | Nada de lo que se proponga puede retrasar ni interferir una maniobra de amarre o una maniobra de izaje. En ambas hay personas junto a cabos en tensión y cargas suspendidas. Ninguna interacción con un dispositivo puede exigirse durante la maniobra. |
| 2 | No se instalarán dispositivos de seguimiento a bordo de embarcaciones de armadores sin su consentimiento expreso. La asamblea de socios ya rechazó la medida. Cualquier función que dependa de datos del armador debe ser voluntaria y con consentimiento revocable. |
| 3 | No habrá cámaras dirigidas a los alumnos de la escuela de vela ni dispositivos a bordo de las embarcaciones menores. El centro de padres lo planteó expresamente. |
| 4 | La radio marítima se mantiene como medio de coordinación operacional. La solución debe convivir con ella y no puede suponer su reemplazo. |
| 5 | El otorgamiento del zarpe es facultad de la autoridad marítima y su formato es de ella. La solución prepara, valida y traza; no sustituye ni simula el acto de la autoridad. |
| 6 | El sistema contable se mantiene y sigue siendo el único emisor de documentos tributarios. |
| 7 | La compañía no tiene personal de tecnologías de información y no lo tendrá. Toda función que requiera un especialista debe ofrecerse como servicio y estar costeada por los 36 meses de operación. |
| 8 | El recinto sigue operando cuando se cae el enlace de datos. La recepción de embarcaciones, el amarre, el registro de salida y regreso y el expendio de combustible no pueden depender de la conectividad hacia el exterior. |
| 9 | Todo equipamiento a instalar en pantalanes debe acreditar su comportamiento en estructura flotante, con flexión permanente del cableado y atmósfera marina, y tener su plan de reposición costeado. |
| 10 | El equipamiento que se instale en la zona del surtidor debe acreditar su idoneidad para un recinto clasificado por almacenamiento y manipulación de combustibles. |
| 11 | Prohibido intervenir sistemas entre el 15 de diciembre y el 15 de marzo, durante las 14 regatas y eventos del calendario, y durante las campañas de varada de abril-mayo y de septiembre-noviembre en lo que afecte al varadero. |
| 12 | Toda actividad programada queda suspendida ante un aviso de marejadas de la autoridad marítima, que se emite con 24 a 48 horas de anticipación y varias veces al año. El plan debe absorber esas cancelaciones sin desplazar hitos contractuales. |
| 13 | Las interfaces destinadas a clientes y visitantes deben estar disponibles en español e inglés como mínimo. |
| 14 | Los datos de salud de los alumnos de la escuela de vela y los datos personales de menores de edad reciben tratamiento reforzado. Ninguna función puede exponerlos a personal que no los requiera para la actividad. |
| 15 | Ninguna medida de cobranza puede impedir a un armador el acceso a su embarcación sin que exista una decisión formal de la compañía que lo autorice, registrada y con fundamento. La embarcación está bajo custodia de la marina y varios deudores son accionistas de la sociedad. |

## CAPÍTULO 11 · EXCLUSIONES EXPLÍCITAS

Para evitar sorpresas, el CLIENTE declara expresamente qué NO está pidiendo:

- No se pide reemplazar el sistema contable ni la emisión de documentos tributarios.
- No se pide desarrollar ni sustituir el sistema de la autoridad marítima para el zarpe.
- No se pide gestión de remuneraciones ni administración de personal.
- No se pide operar la cobranza judicial ni el procedimiento aplicable a las embarcaciones abandonadas; sí construir y mantener el expediente trazable que ese procedimiento requiera.
- No se pide administrar el restaurante concesionado ni su punto de venta; sí registrar su consumo de servicios y su relación contractual con la marina.
- No se pide construir infraestructura: canalizaciones, obras eléctricas, torretas y postación que la solución requiera deben especificarse y costearse, y las ejecuta el CLIENTE.
- No se pide certificar ambientalmente la marina: se pide dejarla en condiciones de cerrar las tres no conformidades y sostener el esquema, con los datos y la evidencia que exija.
- No se pide instrumentar las embarcaciones de los armadores ni proveerles equipamiento de a bordo.
- No se pide mantener las boyas ni su tren de fondeo; sí registrar su estado, su ocupación y el cumplimiento de su programa de inspección.
- El hardware —medidores de agua y energía, lectores de credencial, dispositivos de terreno, instrumentación del surtidor, equipamiento de red— lo adquiere el CLIENTE; el PROPONENTE debe especificar exactamente qué comprar, cuánto y con qué características, conforme al Capítulo 8 de las Bases Técnicas Transversales.

> Que algo esté excluido del alcance no significa que pueda ignorarse en el diseño. La solución debe convivir con todo lo excluido, y las dependencias que ello genera deben estar identificadas, documentadas y consideradas en el plan y en el riesgo.

## CAPÍTULO 12 · MARCO NORMATIVO Y COMPROMISOS CON TERCEROS

El PROPONENTE deberá identificar, investigar y considerar en su propuesta el marco que aplica a esta industria. El CLIENTE entrega la orientación inicial; la profundización es parte del trabajo.

| Ámbito | Referencia | Por qué importa aquí |
|---|---|---|
| Concesión marítima | Concesión sobre sector de playa y fondo de mar, vigente hasta 2044, con obligaciones de uso, conservación y reporte. | Es el título que habilita a la marina a existir. Su incumplimiento tiene consecuencias sobre la concesión misma. |
| Autoridad marítima | Normativa sobre deportes náuticos, zarpe de naves menores, matrícula de embarcaciones, títulos de patrón y equipamiento de seguridad exigible. | Determina qué se acredita en cada uno de los 4.800 zarpes anuales y qué debe estar vigente. |
| Seguridad de la vida humana en el mar | Obligaciones de reporte y de colaboración ante emergencias y búsqueda y salvamento. | Es lo que convierte el registro de regreso de una embarcación en algo distinto de una comodidad administrativa. |
| Actividades deportivas con menores | Normativa aplicable a la práctica deportiva de niños, niñas y adolescentes, autorizaciones de los apoderados y responsabilidad del organizador. | Involucra a 470 menores al año en el agua y define qué debe acreditarse antes de cada salida. |
| Protección de datos personales | Ley N° 21.719, con tratamiento reforzado de datos de menores y de datos relativos a la salud. | Se tratan fichas de salud de niños, datos de armadores y datos de trabajadores de empresas contratistas. |
| Residuos peligrosos | Reglamento sanitario sobre manejo de residuos peligrosos, declaración y trazabilidad hasta el destinatario autorizado. | Es la primera no conformidad de la auditoría: hoy los residuos llegan a la bodega sin identificar al generador. |
| Prevención de la contaminación marina | Normativa nacional e instrumentos internacionales sobre descargas, aguas de sentina, aceites y respuesta a derrames. | Se registraron 7 derrames menores en el año, 2 de ellos con acta. |
| Almacenamiento y expendio de combustibles | Reglamento de instalaciones de combustibles líquidos y sus exigencias de operación, registro y clasificación de recintos. | Condiciona qué equipamiento puede instalarse en la zona del surtidor y qué debe registrarse de cada despacho. |
| Distribución de energía a terceros | Marco aplicable al suministro y al traspaso de costos de energía y agua a ocupantes. | Determina cómo puede la marina medir y cobrar el consumo por amarra, hoy inexistente. |
| Certificación ambiental de marinas | Esquema internacional de certificación ambiental de playas y marinas, con sus criterios, indicadores y auditoría. | Es la exigencia con plazo a la temporada 2029 y una condición contractual de la operadora de charter. |
| Protección del consumidor y contratos | Normativa aplicable a contratos de servicio, cobros, garantías y publicidad de tarifas. | Los contratos de amarra son contratos de adhesión y varios titulares son a la vez accionistas. |
| Depósito y custodia de bienes de terceros | Régimen aplicable a la tenencia de bienes de terceros y a la retención por deudas. | Es el marco de las 14 embarcaciones abandonadas y de cualquier medida que restrinja el acceso de un moroso a su embarcación. |
| Seguridad y salud en el trabajo | Normativa de prevención de riesgos aplicable a faenas de izaje, trabajo sobre estructuras flotantes y trabajo de empresas contratistas en instalaciones de terceros. | Es el fundamento de las restricciones no negociables N° 1 y N° 9, y del régimen de acreditación de las 62 contratistas. |

> Este listado es orientador, no exhaustivo. El PROPONENTE es responsable de identificar la normativa aplicable completa y de acreditar en su propuesta cómo la solución la satisface. Invocar una norma sin explicar qué control concreto la implementa se evaluará como no acreditada.

## CAPÍTULO 13 · HORIZONTE, PRIORIDADES Y ETAPAS

### 13.1 Lo que el comité quiere primero

El comité expresó, sin transformarlo en instrucción técnica, un orden de urgencia: primero la seguridad de las personas —el registro de salida y regreso, la notificación de marejada y el control de la escuela de vela—, porque son los dos episodios que originaron la licitación; luego el ordenamiento comercial —asignación de amarras, visitantes, facturación y cobranza—; y por último la medición por amarra, la trazabilidad ambiental y el portal de clientes.

La gerenta general dejó una objeción registrada que conviene tomar en serio: «la certificación vence la temporada 2029 y el indicador ambiental exige serie de mediciones. Si los medidores se instalan el último año, el indicador no existe y perdemos la certificación igual, con el sistema funcionando».

El jefe de operaciones marítimas dejó otra: «el registro de regreso no se puede hacer sin resolver antes cómo sé que una embarcación está en su amarra. Si eso no está decidido, lo demás es una pantalla bonita».

Ese orden es una preferencia del mandante, no una definición de alcance. La distribución concreta entre la Etapa 1 y la Etapa 2 la propone el PROPONENTE y debe justificarla en función de las dependencias técnicas, del riesgo, de los hitos externos del numeral 13.2 y de la capacidad de absorción del CLIENTE, que en este caso es particularmente limitada.

> Una propuesta que se limite a repetir el orden de preferencia del comité sin analizarlo será evaluada como falta de criterio profesional. Si el PROPONENTE considera que hay una dependencia técnica que obliga a alterar ese orden, debe decirlo y fundamentarlo. El CLIENTE contrata ingeniería, no obediencia.

### 13.2 Hitos externos que condicionan el proyecto

| Fecha | Hito externo | Consecuencia |
|---|---|---|
| 15 de noviembre al 31 de marzo | Temporada alta. 98 % de ocupación, la dotación se duplica, opera la escuela de vela con 470 menores y se concentran los visitantes y los charters. | Congelamiento del 15 de diciembre al 15 de marzo y máxima exigencia sobre cualquier componente ya en producción. |
| Abril y mayo | Campaña de varada. El 62 % de los movimientos anuales de travelift se concentra, junto con septiembre-noviembre, en dos campañas de seis semanas. | El varadero no admite intervención en esas ventanas. El resto del recinto sí. |
| Septiembre a noviembre | Campaña de botadura y preparación de temporada. | Segunda ventana cerrada para el varadero, y última oportunidad de dejar todo operativo antes del 15 de noviembre. |
| 14 fechas del calendario náutico | Regatas y eventos, el mayor con 120 embarcaciones y 800 personas en el recinto. | Congelamientos locales de uno a tres días, con fechas conocidas con un año de anticipación. |
| Sin fecha, varias veces al año | Avisos de marejadas anormales de la autoridad marítima, con 24 a 48 horas de anticipación. | Cancelan cualquier actividad programada, incluidas las del proyecto. Es un riesgo de plazo que no se puede planificar, sólo absorber. |
| Temporada 2029 | Plazo de la auditoría ambiental para cerrar las tres no conformidades, y renovación del contrato marco de la operadora de charter con sus cuatro condiciones. | La operadora representa el 22 % de los ingresos por amarra. El indicador ambiental exige serie histórica previa, por lo que la medición no puede comenzar en 2029. |
| Permanente | Renovación anual de los 296 contratos de amarra y de los seguros de las embarcaciones. | Es la oportunidad natural para actualizar datos de contacto y documentación, hoy obsoletos en el 47 % de los casos. |
| 2031 – 2033 | Evaluación de ampliar los pantalanes en 60 amarras y el campo de boyas a 70 unidades. | No es seguro. Si ocurre, el CLIENTE espera incorporarlas sin rehacer la solución. |

### 13.3 Estrategia de puesta en producción esperada

El CLIENTE no impone una estrategia de implantación, pero sí declara las condiciones que cualquier estrategia debe respetar:

1. Nada entra en producción sin haber convivido con la forma actual de trabajar durante la marcha blanca correspondiente, con conciliación entre ambas y con la posibilidad de volver atrás.
2. Ninguna actividad puede interferir una maniobra de amarre, de izaje o de expendio de combustible, ni la salida de una clase de la escuela de vela.
3. El paso a producción no puede ocurrir entre el 15 de diciembre y el 15 de marzo, ni en las fechas del calendario náutico.
4. El plan debe absorber la cancelación imprevista de actividades por aviso de marejadas, que ocurre varias veces al año con 24 a 48 horas de anticipación y que no admite negociación.
5. El despliegue debe poder hacerse por proceso o por zona —pantalanes, torre y zarpes, escuela de vela, varadero y contratistas, surtidor, administración y portal— y no como un único evento.
6. La migración desde el sistema de 2014, sin proveedor ni documentación, debe contemplar convivencia, conciliación de saldos y un procedimiento de retorno probado, considerando que sólo una persona sabe operar el sistema de origen.
7. El despliegue de medición por amarra debe verificarse en pantalán con estructura en movimiento y cableado a la flexión, y debe iniciarse con anticipación suficiente para acumular la serie histórica que exige el indicador ambiental.
8. La capacitación debe considerar que más de la mitad del personal de temporada es nuevo cada año, que los monitores de la escuela se renuevan cada temporada, y que el congelamiento impide capacitar en el peak.
9. La estabilización posterior a cada paso a producción debe tener dotación y duración declaradas, y contemplar presencia en terreno en los pantalanes y en el varadero, incluidos fines de semana de temporada.
10. La transferencia de la operación no puede suponer un área de tecnologías de información en el CLIENTE, porque no existe.

> El CLIENTE es una empresa pequeña que custodia bienes ajenos de alto valor y hace navegar niños. Un error durante la marcha blanca no se traduce en un dato mal registrado: se traduce en un armador al que nadie avisó antes de una marejada, o en cuarenta minutos sin saber si un niño está en el agua. La estrategia de puesta en producción, y el modelo de operación durante los 36 meses siguientes, pesan en la evaluación de este caso tanto como la arquitectura.

---

# TÍTULO V
## ANTECEDENTES PARA EL DIMENSIONAMIENTO

## CAPÍTULO 14 · VOLUMETRÍA: LO QUE SE ENTREGA Y LO QUE SE DEBE ESTIMAR

El CLIENTE entrega los volúmenes que efectivamente conoce, porque son los que gobiernan su operación. Los volúmenes propios del dimensionamiento de un sistema —concurrencia, transacciones por segundo, almacenamiento, integraciones, telemetría— no los conoce, y no tiene por qué conocerlos: derivarlos es trabajo de ingeniería del PROPONENTE.

> Las celdas marcadas como «a estimar» deben completarse en la propuesta con el valor estimado, el método de estimación y los supuestos empleados. Entregar la propuesta con esas celdas vacías, o con valores sin derivación, se evaluará como dimensionamiento no realizado.

### 14.1 Volumetría operacional entregada por el CLIENTE

| Dimensión | Valor actual | Proyección a 3 años |
|---|---|---|
| Amarras en el agua | 320 | hasta 380, si se ejecuta la ampliación en evaluación |
| Contratos permanentes de amarra vigentes | 296 | ≈ 350 |
| Puestos de invernada en seco | 180, con 152 ocupados | 200 |
| Boyas de fondeo en Bahía Ilque | 40 | hasta 70 |
| Recaladas de embarcaciones visitantes al año | ≈ 1.900 | ≈ 2.400 |
| Zarpes tramitados al año | ≈ 4.800 | ≈ 5.600 |
| Zarpes en el peak de un fin de semana largo | hasta 90, concentrados en dos mañanas | hasta 110 |
| Movimientos de travelift al año | 1.150 | 1.350 |
| Litros de combustible expendidos al año | 1.900.000 | 2.200.000 |
| Socios del club | 1.240 | ≈ 1.450 |
| Alumnos de la escuela de vela al año | 640, de ellos 470 menores de edad | 800, de ellos ≈ 590 menores |
| Salidas de clase al agua al año | ≈ 1.100, con hasta 18 embarcaciones menores cada una | ≈ 1.400 |
| Regatas y eventos náuticos al año | 14; el mayor con 120 embarcaciones y 800 personas | 18 |
| Empresas contratistas registradas | 62, con ≈ 140 personas | 75, con ≈ 170 personas |
| Puntos de medición de agua y energía a instalar | 0 hoy; 320 amarras × 2 servicios | hasta 760 puntos con la ampliación |
| Torretas de servicio en pantalán | 168 | 200 |
| Cámaras de videovigilancia | 38 | 60 |
| Documentos de cobro emitidos al mes | ≈ 1.950 | ≈ 2.300 |
| Personal propio | 39 en invierno, hasta 78 en peak | 44 y 88 |
| Personas distintas que ingresan al recinto en un mes de temporada | ≈ 3.400 entre socios, tripulantes, apoderados, contratistas y visitas | ≈ 4.000 |

### 14.2 Volumetría de sistema que el proponente debe estimar

| Dimensión | Valor |
|---|---|
| Transacciones por segundo en régimen normal | *A estimar y declarar como supuesto* |
| Transacciones por segundo en el peak de una mañana de viernes largo, con zarpes, visitantes y clases simultáneas | *A estimar y declarar como supuesto* |
| Eventos por segundo generados por la medición de agua y energía de las 320 amarras, según la frecuencia de muestreo que se proponga | *A estimar y declarar como supuesto* |
| Frecuencia de muestreo justificada para consumo eléctrico, consumo de agua y estado de ocupación de amarra | *A estimar y declarar como supuesto* |
| Personas usuarias internas concurrentes en un día de temporada | *A estimar y declarar como supuesto* |
| Personas usuarias externas concurrentes en el portal, distinguiendo armadores, apoderados, visitantes y contratistas | *A estimar y declarar como supuesto* |
| Volumen anual de almacenamiento transaccional | *A estimar y declarar como supuesto* |
| Volumen anual de almacenamiento de las series de consumo por amarra | *A estimar y declarar como supuesto* |
| Volumen de la evidencia documental digitalizada: contratos, matrículas, seguros, títulos, fichas de escuela y actas ambientales | *A estimar y declarar como supuesto* |
| Volumen total de datos históricos a migrar desde el sistema de 2014 | *A estimar y declarar como supuesto* |
| Número de integraciones y volumen de mensajes por integración | *A estimar y declarar como supuesto* |
| Cobertura y ancho de banda necesarios en los cinco pantalanes, con estructura en movimiento | *A estimar y declarar como supuesto* |
| Tamaño máximo, frecuencia y latencia tolerable de los mensajes intercambiados con una embarcación en navegación por enlace de baja capacidad | *A estimar y declarar como supuesto* |
| Volumen de datos generado por el recinto durante 24 horas sin enlace hacia el exterior | *A estimar y declarar como supuesto* |
| Tiempo de sincronización tras 24 horas de operación desconectada | *A estimar y declarar como supuesto* |
| Contactos mensuales a la mesa de ayuda, en español e inglés, distinguiendo personal interno de clientes externos | *A estimar y declarar como supuesto* |
| Dotación de la mesa de ayuda y del equipo de operación, considerando que el CLIENTE no aporta ninguna persona de tecnologías de información | *A estimar y declarar como supuesto* |
| Esfuerzo mensual del rol de administración funcional de la solución y a quién se asigna | *A estimar y declarar como supuesto* |

> Preste atención a tres particularidades del perfil de carga de este caso. La primera es que el volumen transaccional es modesto —es una empresa pequeña— pero la concurrencia se concentra brutalmente: una mañana de viernes largo de enero puede reunir noventa zarpes, veinte recaladas de visitantes, tres clases en el agua y una campaña de varada, todo entre las siete y las once. La segunda es que la telemetría de las 320 amarras puede, según la frecuencia de muestreo que se elija, superar en órdenes de magnitud al resto de las transacciones; esa frecuencia es una decisión de diseño con consecuencias directas de costo. La tercera es que existe un canal de comunicación cuyo perfil no aparece en ningún otro caso: mensajes muy cortos, muy espaciados, con latencia de horas y sin garantía de orden de llegada, hacia embarcaciones que navegan fuera de toda cobertura.

## CAPÍTULO 15 · PARÁMETROS DEL CASO PARA LOS REQUISITOS «SEGÚN CASO»

Las Bases Técnicas Transversales marcan un conjunto de requisitos como «Según caso»: son obligatorios, pero su valor concreto lo fija cada industria. Los valores para el Caso 07 son los siguientes. Cuando este capítulo endurece un umbral del documento transversal, prevalece el más exigente.

| Código | Materia | Valor para el Caso 07 |
|---|---|---|
| RT-02.12 | Replicación a nuevas unidades | Exigible. La compañía evalúa ampliar a 380 amarras y a 70 boyas entre 2031 y 2033. La solución debe admitir nuevos pantalanes, amarras, puestos de invernada y boyas por parametrización, sin rediseño y sin intervención de un especialista. |
| RT-03.10 | Operación desconectada del componente on-premise | Mínimo 24 horas continuas de operación del recinto sin enlace hacia el exterior: recepción de embarcaciones, asignación de amarra, registro de salida y regreso, preparación de zarpes, expendio de combustible y registro de la escuela de vela. Los dispositivos de terreno de pantalán, varadero y escuela deben sostener 12 horas continuas fuera de cobertura sin pérdida de registro. La embarcación de inspección de boyas debe operar 8 horas sin cobertura alguna. |
| RT-03.13 | Sincronización tras la reconexión | No debe superar 30 minutos tras 24 horas de desconexión, sin intervención manual y sin pérdida de ningún registro de salida, regreso, despacho de combustible ni asistencia de la escuela de vela. |
| RT-03.24 | Red de los sitios operacionales | Exigible el despliegue de cobertura de datos en los cinco pantalanes y en el varadero, con verificación en estructura flotante, con marea en su rango completo y con el cableado sometido a flexión. Exigible la segregación efectiva de la red de socios, la red administrativa, la red de las cámaras y la red operacional, hoy inexistente: el recinto opera con un único segmento. Exigible la contratación y verificación de un respaldo del enlace principal, hoy inexistente. |
| RT-05.10 | Retención de datos históricos y de auditoría | Registros de la escuela de vela relativos a menores, incluidas autorizaciones y fichas de salud: hasta que el alumno cumpla 18 años y 5 años más, con un mínimo de 10 años. Registros de salida y regreso de embarcaciones y antecedentes de zarpe: 5 años. Contratos de amarra, custodia y estado de cuenta: 6 años. Trazabilidad de residuos peligrosos y actas de derrame: 6 años. Series de consumo por amarra: 5 años, por exigencia del esquema de certificación. Registros de inspección de trenes de fondeo: vida útil del elemento y 5 años más. Registros de despacho de combustible: 5 años. Videovigilancia: 6 meses. |
| RT-05.15 | Datos históricos a migrar | Padrón de socios y de armadores: la totalidad. Contratos de amarra vigentes con su documentación asociada: la totalidad. Historia de pagos y saldos: 6 años. Antecedentes completos de las 14 embarcaciones abandonadas: la totalidad, sin excepción, por su valor probatorio. Registro de embarcaciones e invernadas: la totalidad. Matrícula de la escuela de vela de los últimos 3 años. El sistema de origen no tiene proveedor desde 2021 ni documentación de su modelo de datos, y sólo una persona sabe operarlo. |
| RT-05.23 | Estándares sectoriales de intercambio | Formatos y canales que la autoridad marítima disponga para los antecedentes del zarpe y para la recepción de avisos meteorológicos y de marejadas. Estándares de declaración y trazabilidad de residuos peligrosos ante la autoridad sanitaria. Marco de indicadores del esquema de certificación ambiental de marinas. Estándares de mensajería de baja capacidad para comunicación con embarcaciones en navegación. El PROPONENTE deberá identificar y justificar cada uno, y verificar su disponibilidad efectiva. |
| RT-05.29 | Latencia de la capa analítica | Estado de ocupación de una amarra: no superior a 60 segundos desde el evento. Consumo acumulado por amarra: actualización al menos horaria. Estado de cuenta de un armador: en tiempo real. Indicadores ambientales del esquema de certificación: consolidación diaria. Situación de la escuela de vela —quién está en el agua— en tiempo real, sin excepción. |
| RT-06.01 | Tipología del emplazamiento on-premise | El CLIENTE no dispone de sala de equipos: hoy sólo existe un armario de 12 U en una oficina, sin climatización dedicada ni respaldo adecuado de energía, y no habrá personal que la administre. El componente on-premise debe reducirse al mínimo imprescindible para satisfacer RT-03.10, ser autoadministrado, no requerir intervención humana en operación normal y contar con un gabinete apropiado en administración y gabinetes de borde en pantalán y varadero con grado de protección acreditado para intemperie marina. |
| RT-09.01 | Transacción operacional crítica | Asignación y confirmación de amarra a una embarcación visitante que llama por radio: no superior a 45 segundos desde la consulta. Registro de salida o de regreso de una embarcación por el personal de pantalán: no superior a 10 segundos y con un máximo de dos interacciones. Conformación de la nómina de personas a bordo y del legajo de antecedentes para el zarpe: no superior a 90 segundos. Registro de la salida al agua de una clase completa de la escuela de vela: no superior a 60 segundos para hasta 18 embarcaciones. Notificación de emergencia a los 296 armadores: no superior a 10 minutos hasta el último envío. Alerta por plan de navegación vencido sin cierre: no superior a 15 minutos desde el vencimiento. |
| RT-09.02 | Concurrencia y volumen de transacciones | El PROPONENTE lo deriva de la volumetría del numeral 14.1, considerando la concentración descrita en la mañana de un fin de semana largo de temporada, y lo declara conforme al numeral 14.2. |
| RT-10.05 | Ventana operacional protegida | Congelamiento total del 15 de diciembre al 15 de marzo. Congelamiento del varadero durante las campañas de abril-mayo y de septiembre-noviembre. Congelamiento local en las 14 fechas del calendario náutico. Suspensión inmediata de toda actividad programada ante aviso de marejadas de la autoridad, emitido con 24 a 48 horas de anticipación y varias veces al año: el plan debe absorberla sin desplazar hitos contractuales. |
| RT-11.10 | Cifrado a nivel de campo | Exigible para los datos de salud declarados en la ficha de matrícula de los alumnos, para todo dato personal de menores de edad, para los datos personales de armadores, tripulantes y trabajadores de empresas contratistas, y para la posición de una embarcación cuando el armador haya consentido en compartirla. |
| RT-12.11 | Autenticación en el perfil operacional | Personal de pantalán con las manos mojadas, con guantes y frecuentemente con lluvia, sobre estructura en movimiento. Operador de travelift que no puede interactuar durante la maniobra. Monitores de la escuela de vela a bordo de un semirrígido, mojados. Más de la mitad del personal de temporada es nuevo cada año y los monitores se renuevan cada temporada. No existe en el CLIENTE ninguna persona que administre identidades y accesos. |
| RT-12.12 | Personas usuarias externas | Armadores y socios; apoderados de los alumnos de la escuela de vela; tripulaciones de embarcaciones visitantes, nacionales y extranjeras; empresas contratistas del varadero y sus trabajadores; la operadora internacional de charter; proveedores y gestores autorizados de residuos; y la autoridad marítima y la autoridad sanitaria, en lo que corresponda. |
| RT-13.08 | Interfaces de terreno y de atención | Pantalán flotante, mojado y resbaladizo, con lluvia y manos ocupadas por un cabo. Cabina de travelift con carga suspendida. Semirrígido de la escuela de vela, con salpicadura permanente. Embarcación de servicio en el campo de boyas, sin cobertura. Torre de control con radio en escucha permanente. Mostrador de zarpes con fila. Toda interfaz de terreno debe acreditar operación con guantes, con pantalla mojada y con luz solar directa, y no incrementar la exposición al riesgo, conforme a la restricción no negociable N° 1. |
| RT-13.12 | Multiidioma | Obligatorio, y no deseable como en el documento transversal: español e inglés en todas las interfaces y comunicaciones destinadas a visitantes, tripulaciones extranjeras y a la operadora de charter. La atención de la mesa de ayuda debe cubrir el inglés en temporada. |
| RT-15.02 | Certificaciones sectoriales del adjudicatario | Conocimiento acreditado de la normativa de la autoridad marítima aplicable a naves menores y deportes náuticos, y de la normativa de manejo de residuos peligrosos. Experiencia comprobable en soluciones operadas como servicio gestionado para organizaciones que no cuentan con área de tecnologías de información. |
| RT-16.09 | Registro de consultas a información sensible | Exigible sobre todo acceso a datos de salud y datos personales de menores de edad, sobre el acceso a la posición de embarcaciones cuyos armadores la hayan compartido, y sobre el acceso a los antecedentes de deuda de los armadores, además del registro de modificaciones. |
| RT-16.14 | Firma electrónica | Exigible en el contrato de amarra y sus renovaciones, en la autorización del apoderado para que un menor navegue, en la conformidad de recepción y entrega de una embarcación en custodia, en las actas de maniobra de izaje y en la entrega de residuos peligrosos al gestor autorizado, en la modalidad que la normativa admita para cada caso. |
| RT-16.21 | Canales de notificación | Notificación masiva de emergencia por al menos tres canales simultáneos —mensaje de texto, mensajería instantánea y correo—, con acuse de recibo registrado por destinatario y con escalamiento a llamada telefónica registrada para quienes no acusen. Canal de baja capacidad para embarcaciones en navegación, tolerante a latencia de horas y a entrega desordenada. Notificación al apoderado del retorno de una clase de la escuela. Notificación al armador de eventos de su embarcación y de su estado de cuenta. |
| RT-16.30 | Portal público | Obligatorio. Sin autenticación: disponibilidad y tarifas de amarra de visita, condiciones de acceso, estado del recinto y avisos vigentes, en español e inglés. Autenticado: reserva y pago de amarra de visita; portal del armador con su contrato, consumos, estado de cuenta, documentación de la embarcación y declaración de su plan de navegación; portal del apoderado con la autorización de su hijo y la confirmación de salida y regreso de la clase; portal del contratista con acreditación documental y su declaración de residuos. |
| RT-17.01 | Aplicación móvil | Exigible en cinco perfiles: marinero de pantalán, con operación con guantes, máximo dos interacciones por registro y funcionamiento sin conexión; monitor de la escuela de vela, para armar y cerrar la salida al agua; varadero, para la maniobra y el plan de izaje; inspección del campo de boyas, con operación totalmente desconectada; y armador, con declaración y cierre de plan de navegación y con un modo de baja capacidad para uso en navegación. |
| RT-17.06 | Periféricos a integrar | Medidores de agua y de energía por amarra, aptos para instalación en torreta de pantalán flotante; detección del estado de ocupación de amarra, según la tecnología que el PROPONENTE resuelva; lectores de credencial en portería y en portones de pantalán; instrumentación de despacho del surtidor, con equipamiento apto para recinto clasificado por combustibles; estación meteorológica y recepción de los avisos de la autoridad; y el sistema de control de acceso y las 38 cámaras existentes. |
| RT-21.06 | Horario del centro de atención | Atención de 06:00 a 24:00 todos los días en temporada alta y de 08:00 a 20:00 el resto del año, en español e inglés. El canal de notificación de emergencia y la recepción de alertas por plan de navegación vencido operan 24×7×365 sin excepción. El PROPONENTE debe justificar el modelo con que sostiene esa cobertura reducida sin degradar la respuesta a incidentes críticos. |
| RT-21.16 | Traslado a sitios alejados | Exigible. El campo de 40 boyas de Bahía Ilque está a 6 millas náuticas por mar y a 22 km por camino de ripio, sin energía, sin datos y sin personal, y sólo es accesible con embarcación y en condiciones de mar favorables. Toda instalación, mantención o reposición allí debe considerar esa restricción en plazo y en costo. |
| RT-22.04 | Restricción de la capacitación | Más de la mitad del personal de temporada es nuevo cada año y los monitores de la escuela de vela se renuevan íntegramente cada temporada. El congelamiento del 15 de diciembre al 15 de marzo impide capacitar en el peak, que es cuando ese personal está presente. El CLIENTE no dispone de nadie que pueda impartir capacitación interna sobre la solución. |

## CAPÍTULO 16 · LO QUE ESTE DOCUMENTO DELIBERADAMENTE NO RESUELVE

Las decisiones que siguen son necesarias para que la solución sea coherente. El CLIENTE no las ha tomado, y no las va a tomar por el PROPONENTE. Resolverlas, dejarlas escritas como supuesto y hacerse cargo de sus consecuencias en la arquitectura, en el alcance y en el costo forma parte del trabajo profesional que se licita.

### 16.1 Decisiones de diseño pendientes

| N° | Decisión no tomada | Por qué importa |
|---|---|---|
| 1 | Cómo se establece de forma confiable si una embarcación está en su amarra, salió o no ha regresado: declaración del armador, observación del marinero, sensor en el puesto, lectura en la boca del canal, o una combinación. | Es la decisión de arquitectura más importante del caso. De ella dependen la seguridad, la facturación de visitantes, la ocupación real y el aviso de marejada, y cada alternativa tiene un costo y una fiabilidad radicalmente distintos. |
| 2 | Qué se hace con el sistema de 2014 y cómo se migran doce años de contratos, pagos y registro de embarcaciones, sin proveedor, sin documentación y con una sola persona que sabe operarlo. | Contiene la información que la marina necesitará para cualquier acción sobre las 14 embarcaciones abandonadas. |
| 3 | Cómo se mide el consumo por amarra: medidor por amarra, medidor por torreta con reparto declarado, o un esquema mixto; y qué marco regula el traspaso del costo al armador. | Son hasta 760 puntos en estructuras flotantes con cableado a la flexión. Es simultáneamente la solución al 38 % no recuperado y al indicador ambiental. |
| 4 | Qué es exactamente un plan de navegación para esta marina: qué se declara, quién lo cierra, qué plazo de gracia existe, a quién se avisa cuando ese plazo vence y —sobre todo— qué NO significa. | La marina no es un servicio de búsqueda y salvamento. El alcance de su compromiso debe quedar escrito antes de ofrecer la función, o creará una expectativa que no puede cumplir. |
| 5 | Quién cierra el regreso de una embarcación y con qué evidencia, si el armador se niega a llevar cualquier dispositivo a bordo. | La restricción no negociable N° 2 cierra la alternativa evidente y la asamblea de socios ya la rechazó. |
| 6 | Cómo se registra que un alumno salió al agua y en qué embarcación, sin dispositivos en los niños, sin cámaras y con un monitor mojado a bordo de un semirrígido. | Es exactamente el vacío del 12 de enero y las tres alternativas obvias están prohibidas por la restricción no negociable N° 3. |
| 7 | Cómo se concilia el retiro anticipado de un alumno, que hoy se anota en portería, con la asistencia que lleva la escuela. | Fue la causa raíz del episodio y volverá a ocurrir mientras existan dos registros separados. |
| 8 | Qué dato de salud de un menor puede ver un monitor de temporada, cuál no, y quién autoriza esa visibilidad. | Un monitor necesita saber que un niño es alérgico o asmático; no necesita ver su ficha completa. La ley y los apoderados exigen que esa distinción esté hecha. |
| 9 | Cuál es la regla de asignación de amarra —eslora, manga, calado, tipo de embarcación, exposición al viento— y quién puede saltársela y con qué registro. | El 22 % de amarras mal asignadas y las 90 embarcaciones en lista de espera dependen de esta regla. |
| 10 | Qué ocurre cuando un puesto queda libre y hay lista de espera: oferta automática por orden estricto, criterio comercial, o subasta interna. | La lista de espera involucra a socios accionistas y cualquier regla tendrá consecuencias societarias. |
| 11 | Cómo se cobra a un visitante que llega, amarra y se va antes de pasar por la oficina. | Es el 9 % de recaladas no facturadas, y la solución obvia —cobrar por adelantado— choca con quien llega de noche sin reserva. |
| 12 | Cómo y cuándo se registra el plan de izaje de cada embarcación, quién lo valida y quién responde si está mal. | El operador no anotará nada con la carga suspendida, y ese plan es la diferencia entre una maniobra segura y $ 96 millones en siniestros. |
| 13 | Cómo se reprograma la agenda del travelift cuando el clima cancela un día completo en plena campaña de seis semanas. | Ocurre varias veces por campaña y hoy se resuelve corriendo un cuaderno a lápiz y llamando a diez personas. |
| 14 | Cómo se determina qué residuo peligroso generó cada embarcación, si los contratistas no van a instalar ni usar una aplicación. | Es la primera no conformidad de la auditoría y el propio encargado de varadero advierte que la vía obvia fracasará. |
| 15 | En qué punto del proceso tiene la marina palanca real sobre una empresa contratista, y qué se le exige allí. | El encargado de varadero identificó la portería como el único punto con poder efectivo. Diseñar contra esa realidad o ignorarla cambia todo el enfoque. |
| 16 | Cómo se acredita la capacitación ambiental de 140 personas de empresas externas, quién la imparte y cada cuánto se renueva. | Es la tercera no conformidad y no hay nadie en la marina a quien asignarla hoy. |
| 17 | Qué medida de cobranza es admisible sobre un armador moroso, quién la autoriza y cómo se registra, considerando que la embarcación está bajo custodia de la marina y que varios morosos son accionistas. | La restricción no negociable N° 15 exige una decisión formal, pero no dice quién la toma ni con qué criterio. |
| 18 | Qué expediente se necesita para poder actuar sobre las embarcaciones abandonadas, quién lo construye y qué se conserva. | 26 meses de deuda promedio y 4 de ellas en amarras con lista de espera. Sin expediente no hay acción posible. |
| 19 | Cómo se sabe qué boya está ocupada y por quién, a 6 millas, sin energía y sin datos. | 40 boyas que hoy sólo se conocen dos veces por semana desde una libreta. |
| 20 | Cómo se registra el estado del tren de fondeo de cada boya, con qué periodicidad y qué gatilla su reemplazo. | Dos boyas se soltaron en cuatro años y en ninguno de los dos casos había registro de la última inspección de ese tren. |
| 21 | Qué ocurre en el mostrador cuando el enlace de datos cae una mañana con noventa zarpes por tramitar, y cómo se reconcilia después. | Es el escenario que la restricción no negociable N° 8 exige resolver y el que más gente afecta al mismo tiempo. |
| 22 | Quién ejerce el rol de administrador funcional de la solución en una empresa sin ninguna persona de informática: un servicio del ADJUDICATARIO, una persona de la marina con dedicación parcial, o una combinación; y qué ocurre en vacaciones, licencias y rotación. | Sin esta decisión resuelta y costeada, la solución funciona el primer año y se degrada el segundo. El directorio pidió expresamente verla en la evaluación económica. |

Esta lista no es exhaustiva. Encontrar los demás vacíos es parte del ejercicio, y el PROPONENTE que identifique vacíos no listados aquí será evaluado favorablemente por ello.

### 16.2 Materias que el proponente deberá investigar

El CLIENTE no espera que el PROPONENTE conozca la actividad náutica de antemano. Sí espera que la estudie. Las siguientes materias son necesarias para formular una propuesta competente y no se explican en este documento:

- Régimen de concesiones marítimas en Chile: obligaciones del concesionario, uso del borde costero y reporte a la autoridad.
- Normativa de la autoridad marítima sobre naves menores y deportes náuticos: matrícula, zarpe, títulos de patrón y equipamiento de seguridad exigible.
- Búsqueda y salvamento marítimo: cómo se activa, qué antecedentes se piden y qué se espera de un puerto deportivo como último punto de contacto.
- Planes de navegación: qué contienen en la práctica internacional, cómo se abren y se cierran, y cuál es el alcance de responsabilidad de quien los recibe.
- Sistemas de gestión de marinas: qué funciones cubren y cómo modelan la amarra, la embarcación, el contrato, la estadía y el servicio.
- Identificación de embarcaciones menores: matrícula, nombre y numeral, y alcance y límites de los sistemas de identificación automática en esta categoría de naves.
- Detección del estado de ocupación de una amarra: tecnologías aplicadas en marinas, su desempeño en agua salada y su comportamiento en estructuras móviles.
- Instalación eléctrica y de datos en pantalanes flotantes: normativa aplicable, cableado sometido a flexión, protecciones diferenciales, corrosión galvánica y protección catódica.
- Submedición de energía y de agua y traspaso de su costo a ocupantes: marco regulatorio chileno y sus límites.
- Maniobra de izaje con travelift: puntos de eslingado, planes de izaje, prácticas de la industria y régimen de responsabilidad por daño a la embarcación.
- Manejo de residuos peligrosos en varaderos y astilleros menores: pinturas antiincrustantes, aceites, solventes, declaración y trazabilidad hasta el destinatario autorizado.
- Prevención de la contaminación marina en marinas: aguas de sentina, instalaciones de recepción y respuesta a derrames menores.
- Esquemas internacionales de certificación ambiental de playas y marinas: criterios, indicadores exigidos, metodología de medición y proceso de auditoría.
- Normativa de almacenamiento y expendio de combustibles líquidos, y clasificación de recintos para la instalación de equipamiento eléctrico y electrónico.
- Actividad deportiva con menores de edad: autorizaciones del apoderado, razón monitor-alumno, certificación de monitores y tratamiento reforzado de datos personales de niños.
- Comunicaciones marítimas: uso de la radio en banda marina y sus canales, y mensajería satelital de baja capacidad aplicable a embarcaciones menores.
- Régimen de custodia de bienes ajenos, derecho de retención y procedimientos aplicables a embarcaciones abandonadas en recintos portuarios deportivos.
- Modelos de servicio gestionado para organizaciones sin área de tecnologías de información: alcance, niveles de servicio, gobierno y costo real en un horizonte de 36 meses.

> La calidad de esta investigación se hará evidente en el Informe 1 y en la defensa técnica. Una propuesta que ofrezca «seguimiento de embarcaciones» sin haber notado que la asamblea de socios ya lo rechazó, o que prometa trazabilidad de residuos sin haber pensado quién la registra cuando el generador es una empresa externa que no usará ninguna aplicación, quedará en evidencia frente a la Comisión de Expertos.

---

# TÍTULO VI
## LO QUE DEBE PRODUCIR EL PROPONENTE

## CAPÍTULO 17 · EL TRABAJO DE TRADUCCIÓN EXIGIDO

Este documento describe una operación y sus problemas. No contiene un catálogo de requerimientos. Construirlo es la primera tarea del PROPONENTE y la que condiciona todas las demás.

### 17.1 De la necesidad al requerimiento

El PROPONENTE deberá recorrer este documento y producir un catálogo de requerimientos trazable a su origen. Cada requerimiento debe indicar de qué párrafo, entrevista, indicador o restricción proviene, de modo que el CLIENTE pueda verificar que nada quedó fuera y nada fue inventado.

| Producto | Contenido esperado |
|---|---|
| Catálogo de requerimientos funcionales | Qué debe hacer la solución, expresado en términos verificables, con identificador, descripción, actor, precondición, resultado esperado, prioridad y origen en este documento. |
| Catálogo de requerimientos no funcionales | Desempeño, disponibilidad, seguridad, usabilidad, operabilidad, mantenibilidad, portabilidad, multiidioma y cumplimiento, con umbral numérico y método de verificación. Deben incorporar los parámetros del Capítulo 15 y los requisitos del documento transversal. |
| Registro de supuestos | Toda decisión que el PROPONENTE tomó por el CLIENTE, con su fundamento, su impacto si resulta equivocada y la instancia en que se validará. Incluye obligatoriamente las veintidós decisiones del numeral 16.1, y en particular la primera y la vigesimosegunda. |
| Registro de reglas de negocio | Las reglas propias de la actividad que la solución debe respetar y que este documento no explicita: compatibilidad entre embarcación y puesto, prelación de la lista de espera, tarificación de la estadía de visita, cálculo del consumo imputable, criterios de suspensión de faenas por clima, y razón monitor-alumno en el agua, entre otras. |
| Matriz de trazabilidad | Correspondencia entre origen, requerimiento, componente de la arquitectura, paquete de la EDT, prueba de verificación y criterio de aceptación. |
| Registro de vacíos y consultas | Aquello que el PROPONENTE no puede resolver por sí solo y que someterá al CLIENTE durante el período de consultas. |

> Un requerimiento no es una frase copiada de este documento. «Hay que saber quién está en el agua» no es un requerimiento: es un resultado esperado. El requerimiento indica quién declara la salida, qué se declara —alumno, embarcación, monitor, hora, condiciones—, en cuántas interacciones y desde qué dispositivo se hace estando mojado, qué ocurre si un alumno se cambia de bote a mitad de clase, cómo se cierra el regreso, qué pasa si el cierre no ocurre, y a quién se notifica.

### 17.2 Distinguir lo funcional de lo no funcional

Buena parte de lo que este documento describe puede leerse de las dos maneras, y la clasificación no es indiferente: determina quién lo verifica, cómo se prueba y en qué momento del proyecto se comprueba. Se ofrecen deliberadamente sin resolver algunos casos limítrofes:

- «El registro de una salida debe tomar dos interacciones»: ¿es usabilidad, es desempeño, o es funcional porque de ello depende que el registro exista o no exista?
- «El recinto debe operar veinticuatro horas sin enlace»: ¿es disponibilidad, es una decisión de arquitectura, o es un conjunto de requerimientos funcionales sobre qué se puede hacer y qué no en modo desconectado?
- «Nadie llevará dispositivos a bordo sin consentimiento»: ¿es una restricción de diseño, un requerimiento de protección de datos, o un requerimiento funcional de gestión del consentimiento y de su revocación?
- «La notificación de marejada debe llegar a los 296 armadores en diez minutos»: ¿es desempeño del sistema, o es funcional porque incluye reintentos, acuse de recibo y escalamiento a llamada?
- «Los residuos deben poder trazarse hasta la embarcación generadora»: ¿es trazabilidad, es una funcionalidad de registro en el punto de generación, o es cumplimiento ambiental con evidencia conservada?
- «La solución debe poder operarse sin un área de informática»: ¿es operabilidad, es mantenibilidad, es una restricción de arquitectura, o es un requerimiento sobre el servicio y no sobre el software?

Se evaluará el criterio con que el PROPONENTE resuelve estos casos y la consistencia con que aplica su propio criterio a lo largo de la propuesta, no la coincidencia con una respuesta preestablecida.

### 17.3 Definir el alcance y su reparto entre etapas

A partir del catálogo, el PROPONENTE deberá delimitar el alcance de la Etapa 1 y de la Etapa 2, declarar las exclusiones y justificar el reparto en función de las dependencias técnicas, del riesgo, de los hitos externos del numeral 13.2 y de la capacidad de absorción del CLIENTE, que en este caso es la más limitada de cualquier mandante: treinta y nueve personas en invierno y ninguna de informática.

La justificación debe hacerse cargo explícitamente de la preferencia del comité del numeral 13.1 y de las dos objeciones registradas allí mismo: que el indicador ambiental exige serie histórica y no puede empezar a medirse en 2029, y que el registro de regreso no puede construirse antes de decidir cómo se sabe que una embarcación está en su amarra.

### 17.4 Diseñar la arquitectura

La arquitectura lógica y física debe ser propia de este caso y reconocible como tal. Debe hacerse cargo, como mínimo, de los siguientes asuntos, todos ellos derivados de lo descrito en este documento:

1. Cómo se determina el estado de ocupación de una amarra y el hecho de una salida y de un regreso, con qué combinación de declaración, observación e instrumentación, y con qué grado de confianza declarado.
2. Cómo se sostiene la operación del recinto durante veinticuatro horas sin enlace hacia el exterior, con un componente on-premise mínimo que nadie administrará.
3. Qué se ejecuta en la nube y qué en el recinto, y por qué, sabiendo que no hay sala de equipos, no hay respaldo de energía adecuado y no hay ninguna persona de informática.
4. Cómo se despliega cobertura de datos en cinco pantalanes flotantes que suben y bajan con la marea, y cómo se protege el cableado sometido a flexión permanente en atmósfera marina.
5. Cómo se instrumentan hasta setecientos sesenta puntos de medición de agua y energía en torretas flotantes, con qué frecuencia de muestreo y con qué procesamiento en el borde.
6. Cómo funciona el canal de baja capacidad hacia embarcaciones en navegación: qué mensajes, de qué tamaño, con qué tolerancia a la latencia y al desorden de llegada, y qué ocurre cuando un mensaje nunca llega.
7. Cómo se detecta y se escala un plan de navegación vencido sin cierre, y qué límite de responsabilidad se declara.
8. Cómo se notifica a doscientos noventa y seis armadores en diez minutos, con acuse de recibo por destinatario y escalamiento, y cómo se mantiene vigente la información de contacto.
9. Cómo se registra la salida al agua de una clase completa de la escuela de vela sin dispositivos en los niños, sin cámaras y desde un semirrígido.
10. Cómo se separan la red de socios, la red administrativa, la red de las cámaras y la red operacional, hoy inexistentes como segmentos distintos.
11. Qué equipamiento puede instalarse en la zona del surtidor conforme a su clasificación, y qué se hace si no existe alternativa apta a costo razonable.
12. Cómo opera la inspección del campo de boyas de forma totalmente desconectada, a seis millas y sin energía.
13. Cómo se protegen los datos de salud y los datos personales de cuatrocientos setenta menores, y cómo se limita su visibilidad al mínimo que la actividad exige.
14. Qué crecimiento admite el diseño ante la ampliación evaluada a 380 amarras y 70 boyas, y qué componente se satura primero en la mañana de un fin de semana largo de enero.

### 17.5 Planificar de forma realista

El plan de trabajo debe ser específico de esta marina. Un cronograma que podría servir para cualquier proyecto será evaluado como deficiente. En particular deberá reflejar:

- El cronograma contractual obligatorio de 56 meses del Artículo 17° de las Bases Administrativas, sin proponer plazos alternativos.
- El congelamiento del 15 de diciembre al 15 de marzo, las 14 fechas del calendario náutico y las dos campañas de varada de seis semanas.
- La cancelación imprevista de actividades por aviso de marejadas, con 24 a 48 horas de anticipación, varias veces al año y sin negociación posible. El plan debe declarar cuánta holgura reserva para ello y sobre qué base la calculó.
- La instalación de medición en torretas de pantalán flotante, que sólo puede ejecutarse con la embarcación desconectada o fuera del agua, y por lo tanto se coordina con las campañas de varada.
- La necesidad de acumular serie histórica de consumo antes de la temporada 2029, y la dependencia de que la medición esté operativa mucho antes.
- El trabajo en el campo de boyas, accesible sólo por mar y sujeto a condiciones de navegación.
- La migración desde el sistema de 2014 sin proveedor, sin documentación y con una sola persona que sabe operarlo, incluida la reconstrucción íntegra del expediente de las 14 embarcaciones abandonadas.
- La actualización de los datos de contacto y de la documentación de 296 contratos, hoy obsoletos en el 47 % de los casos, que sólo puede hacerse en las renovaciones anuales o con una campaña específica que debe estar costeada.
- La capacitación de un personal de temporada que se renueva en más de la mitad cada año y de monitores que se renuevan por completo, con el agravante de que el congelamiento coincide con el período en que ese personal está presente.
- El solapamiento de los meses 13 a 15 y 19 a 20, con la dotación efectivamente necesaria para sostener dos frentes simultáneos en una organización de este tamaño.

### 17.6 Proponer una estrategia de puesta en producción y de operación

El CLIENTE es una empresa pequeña que custodia bienes ajenos y hace navegar niños, y que no tiene a nadie de informática. La propuesta deberá contener una estrategia explícita y no una declaración de intenciones:

1. Qué entra en producción primero, en qué zona y con qué criterio de avance. Se espera fundamento sobre si conviene empezar por la torre y los zarpes, por la escuela de vela o por la administración.
2. Cómo se hace la marcha blanca del reemplazo del sistema de 2014, que es el punto de mayor riesgo administrativo: cómo se concilian saldos, con qué frecuencia y con qué umbral de discrepancia se detiene el avance, sabiendo que la única persona que conoce el sistema de origen es también quien debe operar el nuevo.
3. Cómo se verifica en terreno el inventario real de embarcaciones, sus esloras y su ubicación efectiva al momento del corte, considerando el 22 % de amarras mal asignadas.
4. Qué indicadores se medirán durante la marcha blanca y con qué umbral se declara cerrada, conforme al Artículo 17.3 de las Bases Administrativas.
5. Cómo se revierte un paso a producción fallido en una mañana con noventa zarpes y una campaña de varada en curso.
6. Qué dotación de acompañamiento habrá en terreno, en pantalán y en el varadero, incluidos fines de semana de temporada, que es cuando ocurre la operación real.
7. Cómo se capacita a un personal de temporada que llega en noviembre, es nuevo en más de la mitad, y sobre el cual no puede intervenirse a partir del 15 de diciembre.
8. Cómo se logra la adopción de un marinero con las manos mojadas que ya perdió un teléfono al agua, y de un operador de travelift con veintidós años que no anotará nada con la carga suspendida.
9. Cómo se obtiene y se mantiene el consentimiento de los armadores para todo dato voluntario, y qué funciona cuando el armador no consiente.
10. Cómo se transfiere la operación a un CLIENTE que no tiene ninguna persona de tecnologías de información: qué rol asume el ADJUDICATARIO, qué rol mínimo debe asumir la marina, quién lo ejerce y qué ocurre cuando esa persona está de vacaciones o con licencia.
11. Cómo se opera durante los 36 meses siguientes, con el horario reducido del numeral RT-21.06, la cobertura 24×7 del canal de emergencia, y la atención en inglés en temporada, y con qué costo mensual sostenido.

## CAPÍTULO 18 · CRITERIOS DE ACEPTACIÓN DEL CASO

Los siguientes resultados de negocio son los que el CLIENTE utilizará para juzgar si el PROYECTO fue exitoso. El PROPONENTE deberá comprometerse con ellos, proponer la meta cuando este documento no la fije, indicar en qué momento del cronograma se alcanzará cada uno y cómo se medirá.

| N° | Resultado esperado | Situación actual |
|---|---|---|
| 1 | En cualquier momento se sabe qué embarcaciones están en su amarra y cuáles salieron. | Hay que caminar el pantalán y mirar. |
| 2 | El regreso de una embarcación queda registrado, y la ausencia de un regreso comprometido genera una alerta. | No existe registro de regreso. |
| 3 | Un armador puede declarar y cerrar su plan de navegación, y decidir voluntariamente qué comparte. | Un papel en una carpeta que nadie revisa. |
| 4 | Ante un aviso de marejada, los 296 armadores quedan notificados en minutos, con evidencia de a quién, cuándo, por qué canal y con qué acuse. | 190 de 296 contactados; evidencia inexistente. |
| 5 | Los datos de contacto de los contratos se mantienen vigentes y su obsolescencia se detecta. | 47 % con al menos un dato obsoleto. |
| 6 | Se responde en segundos quién de la escuela está autorizado a navegar hoy, quién salió, en qué bote, con qué monitor y si volvió. | Hoja firmada en la mañana; 40 minutos el 12 de enero. |
| 7 | El retiro anticipado de un alumno registrado en portería es visible de inmediato para la escuela. | Dos cuadernos separados que nadie concilia. |
| 8 | Cada amarra está ocupada por una embarcación compatible con el puesto y con el tramo que paga. | 22 % de amarras mal asignadas. |
| 9 | Un puesto que queda libre se ofrece a la lista de espera sin que nadie deba acordarse. | 90 embarcaciones en espera y asignación por memoria. |
| 10 | Una embarcación visitante que llama por radio recibe su puesto asignado de inmediato. | 11 minutos, dando vueltas frente a la entrada. |
| 11 | Ninguna recalada de visitante queda sin registrarse como servicio facturable. | 9 % no se registra. |
| 12 | Las reservas de visitantes llegan a un único registro, cualquiera sea el canal de origen. | 4 canales, 4 registros distintos. |
| 13 | El zarpe se prepara con la información que la marina ya tiene y la vigencia de los documentos se conoce antes del mostrador. | 18 minutos por trámite; 34 % con corrección a mano. |
| 14 | Cada embarcación tiene su plan de izaje registrado y disponible antes de la maniobra. | 0 de 296; está en la memoria de dos personas. |
| 15 | La agenda del travelift se reprograma sin llamar a diez personas cuando el clima cancela un día. | Cuaderno corrido a lápiz. |
| 16 | El residuo peligroso se traza desde la embarcación que lo genera hasta el gestor autorizado que lo recibe. | Tambores comunes; trazabilidad inexistente. |
| 17 | Las 62 empresas contratistas mantienen su acreditación documental y su capacitación ambiental vigentes, verificadas en el acceso. | 41 % con documentación completa; capacitación sin evidencia. |
| 18 | El consumo de agua y energía se mide por amarra y sirve a la vez para facturar y para el indicador ambiental. | 0 de 320 medidas; 38 % del costo no recuperado. |
| 19 | Las tres no conformidades de la auditoría ambiental quedan cerradas con serie de datos suficiente antes de la temporada 2029. | 3 abiertas; sin mediciones que acumulen. |
| 20 | Se sabe qué boya está ocupada y por quién, y el estado de cada tren de fondeo con su última inspección. | Una libreta, dos veces por semana. |
| 21 | La facturación mensual se emite sin reunir cuadernos y sin 6 % de notas de crédito. | 10 días-persona al mes; 6 % de error. |
| 22 | Las 14 embarcaciones abandonadas tienen un expediente completo y trazable que permite actuar. | 26 meses de deuda promedio y ningún expediente. |
| 23 | Doña Verónica sabe desde su teléfono que su hija salió a navegar y que volvió, sin llamar a nadie y sin que nadie la filme. | Se entera cuando la va a buscar. |
| 24 | Don Eleodoro abre la ficha de la embarcación antes de izarla y ve dónde van las eslingas; y el operador que lleva ocho meses ve exactamente lo mismo. | Está en la memoria de una persona con 22 años. |
| 25 | La marina opera la solución durante 36 meses sin contratar un área de informática y sin degradarse. | Cero personas de TI; un proveedor externo dos veces al mes. |

> Los criterios 23, 24 y 25 parecen menores y son los tres decisivos. El 23 mide si el PROPONENTE entendió que a una madre no le interesa un tablero de control, sino una certeza. El 24 mide si entendió que veintidós años de conocimiento tácito se transfieren registrándolos en el momento correcto —con el barco en los calzos y no en el aire— o no se transfieren nunca. Y el 25 mide si entendió que en esta empresa la solución no tiene a quién dejársela: si no está diseñada para sobrevivir sin un administrador, no sobrevive.

## CAPÍTULO 19 · CÓMO SE EVALUARÁ ESTE CASO

La evaluación se rige por el Título V de las Bases Administrativas y por la ponderación del Formulario T-21. Este capítulo precisa qué se buscará específicamente en el Caso 07 al aplicar esos criterios.

| Ítem | Qué se buscará en este caso |
|---|---|
| Comprensión del problema | Que el PROPONENTE entienda que aquí el producto no es una amarra sino una custodia: de una embarcación ajena de alto valor, de un menor de edad en el agua y de un compromiso ambiental con plazo. Y que entienda que la dificultad no viene del volumen —es una empresa pequeña— sino de que cinco negocios distintos comparten el mismo recinto, las mismas personas y ninguna capacidad informática. |
| Esquema de solución y alcance | Que la decisión sobre cómo se conoce el estado de una amarra y el hecho de una salida y un regreso esté tomada, fundada y costeada, y no resuelta por omisión. Que el alcance sea consecuencia del catálogo y que las exclusiones sean explícitas. |
| Arquitectura lógica y física | Que resuelva de forma verificable la operación de 24 horas sin enlace con un on-premise que nadie administra, la cobertura en pantalanes flotantes, la medición en hasta 760 puntos en torretas móviles, el canal de baja capacidad hacia embarcaciones en navegación y la clasificación del recinto del surtidor. Que sea propia de esta marina y no un diagrama de referencia con el nombre cambiado. |
| Modelo y gestión de datos | Que el tratamiento de los datos de menores y de sus fichas de salud esté resuelto con visibilidad mínima y con registro de acceso. Que el consentimiento de los armadores sea gestionable y revocable. Que las veintidós decisiones pendientes del numeral 16.1 estén resueltas y declaradas como supuesto. |
| Plan de trabajo, EDT y cronograma | Que refleje el congelamiento de temporada, las 14 fechas náuticas, las dos campañas de varada, el acceso al campo de boyas sólo por mar y —de forma explícita y cuantificada— la holgura reservada para las cancelaciones por marejada. Que la ruta crítica sea creíble para una organización de 39 personas. |
| Plan de riesgos | Que los riesgos sean de este proyecto: rechazo de los armadores a cualquier dispositivo, rechazo de los apoderados a cámaras, negativa de los contratistas a usar una aplicación, pérdida de la única persona que sabe operar el sistema de origen, falla de instalaciones en pantalán por corrosión y flexión, cancelación reiterada de ventanas por marejada, y la ausencia total de contraparte técnica en el CLIENTE. |
| Servicios de operación y niveles de servicio | Que el modelo de soporte se haga cargo de que el CLIENTE no aporta ninguna persona de informática. Que el horario reducido esté justificado y que el canal de emergencia 24×7 esté cubierto. Que la dotación esté dimensionada con método y que el costo de los 36 meses sea sostenible para una empresa que factura $ 4.200 millones. |
| Innovaciones | Que las cinco innovaciones sean pertinentes a un puerto deportivo y a los problemas de esta marina, y no un catálogo de tecnologías de moda. Que la de sostenibilidad se articule con las tres no conformidades concretas de la auditoría y con la condición de la operadora de charter. |
| Consolidación | Que la propuesta sea internamente coherente: que la arquitectura sostenga el alcance, que la EDT contenga la arquitectura, que el cronograma refleje la EDT y que el costo derive de todo lo anterior. En este caso, además, que la evaluación económica demuestre que una empresa de este tamaño puede pagar el proyecto y operarlo durante tres años. |

> **Una advertencia final del mandante.**
>
> En el acta del directorio quedó consignado el voto de minoría que la gerenta general pidió transcribiera: esta empresa factura cuatro mil doscientos millones al año y no tiene una sola persona dedicada a informática, y antes de aprobar el proyecto el directorio quiere ver una evaluación económica que demuestre que puede pagarlo y operarlo, y no sólo comprarlo.
>
> Una propuesta técnicamente sofisticada que suponga un administrador de sistemas que no existe será superada por una propuesta más sobria que se haga cargo de operar durante treinta y seis meses en una organización que no puede sostenerla sola. Y por debajo de toda la discusión económica hay una frase que la jefa de la escuela de vela dejó en su entrevista y que conviene tener presente al diseñar: ese día tuvimos suerte, y la suerte no es un procedimiento.

---

# TÍTULO VII
## ANEXOS DEL CASO

## CAPÍTULO A · MAPA DE SISTEMAS Y FLUJOS DE INFORMACIÓN ACTUALES

Descripción de los flujos de información tal como ocurren hoy. La columna «cómo viaja» es la que explica buena parte de los problemas descritos en el Capítulo 7.

| Origen | Destino | Qué información | Cómo viaja hoy |
|---|---|---|---|
| Armador | Administración | Contrato de amarra y documentación de la embarcación | Papel firmado en dos copias, archivado en carpeta |
| Administración | Sistema de 2014 | Contrato, tarifa y estado de cuenta | Digitación manual en un computador de la oficina |
| Jefe de operaciones | Nadie | Asignación de cada embarcación a su puesto | Plano plastificado anotado con lápiz graso |
| Embarcación visitante | Torre de control | Solicitud de amarra, eslora, manga y calado | Radio marítima, a dos millas de la entrada |
| Torre de control | Marineros de pantalán | Confirmación de que la amarra está realmente libre | Radio; 11 minutos hasta responder al visitante |
| Visitante | Administración | Reserva anticipada | Correo, teléfono, radio y mensaje directo en redes sociales; sin registro común |
| Armador | Torre de control | Antecedentes del zarpe | Verbal o en papel en el mostrador; 18 minutos por trámite |
| Torre de control | Autoridad marítima | Formulario de zarpe | Formato de la autoridad, completado a mano |
| Embarcación | Nadie | Regreso a la amarra | No se registra |
| Armador | Torre de control | Plan de navegación | Papel entregado en el mostrador, archivado en una carpeta que no se revisa |
| Autoridad marítima | Torre de control | Aviso de marejadas | Canal oficial; recibe en la torre |
| Administración | 296 armadores | Aviso de marejada y solicitud de reforzar amarras | Llamadas telefónicas desde una planilla; 190 contactados; sin registro |
| Armador | Encargado de varadero | Solicitud de varada o botadura | Teléfono; se anota en un cuaderno de doble página |
| Encargado de varadero | Operador de travelift | Programación del día y orden de las maniobras | Verbal, con el cuaderno a la vista |
| Operador de travelift | Nadie | Puntos de eslingado de la embarcación | Memoria de dos personas; 0 de 296 documentados |
| Empresa contratista | Portería | Acreditación documental de la empresa y sus trabajadores | Carpetas revisadas a mano; 41 % completa |
| Empresa contratista | Bodega de residuos | Residuo peligroso generado en un trabajo | Tambores comunes, sin identificar la embarcación generadora |
| Bodega de residuos | Gestor autorizado | Retiro de residuos | Documento de retiro por lote, sin desglose por generador |
| Apoderado | Escuela de vela | Matrícula, autorización y ficha de salud del alumno | Ficha de papel archivada en un archivador de oficina |
| Escuela de vela | Nadie | Asistencia del día y salida al agua | Hoja firmada a las 09:00 que queda en la caseta |
| Apoderado | Portería | Retiro anticipado de un alumno | Cuaderno de portería que la escuela no revisa |
| Surtidor | Administración | Litros despachados y a quién | Boleta manual; control de existencias por varillaje diario |
| Embarcación de servicio | Torre de control | Estado y ocupación de las 40 boyas de Bahía Ilque | Libreta, dos veces por semana |
| Pantalán, varadero, surtidor y escuela | Administración | Hechos facturables del mes | Cuadernos, boletas y hojas reunidas a mano; 5 días con 2 personas |
| Distribuidora eléctrica | Administración | Cuenta total del recinto | Documento mensual con un solo medidor; se reparte por eslora |
| Sistema de 2014 | Sistema contable | Cobros del mes | Digitación manual; 6 % termina en nota de crédito |
| Auditor de certificación ambiental | Gerencia | Hallazgos y no conformidades | Informe anual en papel |

## CAPÍTULO B · CALENDARIO Y PERFIL OPERACIONAL DE REFERENCIA

### B.1 Perfil de un día de temporada

| Tramo horario | Qué ocurre | Carga sobre la solución |
|---|---|---|
| 00.00 – 06.00 | Recinto cerrado al público, con control de acceso y ronda de seguridad. Ocasionalmente llega una embarcación de travesía nocturna. | Dotación mínima. Una recalada nocturna debe poder resolverse sin oficina abierta. |
| 06.00 – 08.00 | Salidas tempranas. Tripulaciones que zarpan con la primera luz y con la marea. | Primer peak de zarpes y de registro de salida. La oficina de administración aún no abre. |
| 07.00 – 11.00 | Peak de zarpes de fin de semana. Hasta 90 en dos mañanas de un fin de semana largo. Fila en el mostrador de la torre. | Es la máxima concentración de todo el año y coincide con el peak del pantalán. |
| 09.00 – 13.00 | Clases de la escuela de vela. Hasta 18 embarcaciones menores y tres monitores por salida. | Registro de quién sale, en qué bote y con qué monitor, y cierre del regreso. |
| 10.00 – 18.00 | Faenas de varadero: varadas, botaduras y trabajos de contratistas en los 14 puestos. | Programación del travelift, plan de izaje, acceso y acreditación de 140 personas externas. |
| 12.00 – 20.00 | Expendio de combustible y llegada de embarcaciones visitantes. | Registro de despacho y asignación de amarra de visita, muchas veces coordinada por radio. |
| 15.00 – 21.00 | Peak de regresos. Las embarcaciones que salieron en la mañana vuelven a su amarra. | Es el momento en que hoy no se registra nada, y donde debería cerrarse el ciclo del día. |
| Todo el día | Escucha permanente de radio en la torre y coordinación de maniobras. | La solución convive con la radio y no la reemplaza. |
| Cualquier momento | Recepción de un aviso de marejadas de la autoridad marítima. | Dispara notificación masiva a 296 armadores y suspende todas las faenas programadas. |

### B.2 Estacionalidad y ventanas

| Período | Efecto | Consecuencia para el proyecto |
|---|---|---|
| 15 de noviembre al 31 de marzo | Temporada alta. 98 % de ocupación, la dotación se duplica y llegan los charters y los visitantes. | Máxima exigencia sobre lo que esté en producción. Congelamiento total entre el 15 de diciembre y el 15 de marzo. |
| Abril y mayo | Campaña de varada. La mayoría de la flota sale del agua en seis semanas, con un solo travelift. | El varadero no admite intervención. Es, en cambio, la única ventana práctica para instalar medición en torretas con la embarcación fuera del agua. |
| Junio a agosto | Invierno. Menor actividad, clima adverso, mayor frecuencia de marejadas y de temporales. | Mejor ventana para intervención mayor en tierra, con la advertencia de que es también cuando más se cancelan actividades por marejada. |
| Septiembre a noviembre | Campaña de botadura y preparación de la temporada. | Segunda ventana cerrada para el varadero y última oportunidad de dejar todo operativo antes del 15 de noviembre. |
| 14 fechas del calendario náutico | Regatas y eventos. El mayor reúne 120 embarcaciones y hasta 800 personas en el recinto. | Congelamiento local de uno a tres días, con fechas conocidas con un año de anticipación. |
| Fines de semana largos de temporada | Concentración extrema de zarpes, regresos y visitantes en dos mañanas. | Es el escenario de diseño de la concurrencia, no la excepción. |
| Sin fecha, varias veces al año | Avisos de marejadas anormales, emitidos con 24 a 48 horas de anticipación. | Cancelan cualquier faena programada, incluidas las del proyecto, y activan el protocolo de notificación masiva. |
| Renovación anual de contratos | 296 contratos de amarra y sus seguros se renuevan cada año en fechas escalonadas. | Única oportunidad natural para actualizar los datos de contacto y la documentación, hoy obsoletos en el 47 % de los casos. |

## CAPÍTULO C · GLOSARIO DE LA INDUSTRIA

Vocabulario mínimo para leer este documento. No sustituye la investigación exigida en el numeral 16.2.

| Término | Significado |
|---|---|
| Amarra | Puesto de atraque asignado a una embarcación en un pantalán, con acceso a servicios. Es la unidad de inventario y de contrato de una marina. |
| Armador | Persona natural o jurídica propietaria o responsable de una embarcación. Es el titular del contrato de amarra. |
| Botadura | Operación de poner una embarcación en el agua desde tierra. Es la inversa de la varada. |
| Calado | Profundidad que necesita una embarcación bajo la línea de flotación. Determina en qué puestos puede estar con marea baja. |
| Campo de boyas | Conjunto de boyas de fondeo dispuestas en una bahía para amarre de embarcaciones fuera de un pantalán. |
| Concesión marítima | Título que autoriza a ocupar y explotar un sector de playa y fondo de mar, con obligaciones de uso y conservación. |
| Eslinga | Faja con la que el travelift suspende la embarcación. Su posición correcta depende de la geometría de cada casco. |
| Eslora, manga y puntal | Largo, ancho y altura de una embarcación. La eslora define el tramo tarifario; la manga y el calado definen en qué puesto cabe. |
| Fondeadero | Lugar apto para que una embarcación quede sujeta al fondo, con ancla propia o con una boya de fondeo. |
| Invernada | Permanencia de una embarcación fuera del agua durante la temporada baja, sobre calzos en una explanada. |
| Marejada | Estado de mar con oleaje de mayor altura y energía. La autoridad marítima emite avisos que obligan a extremar medidas y suspender faenas. |
| Marina base y marina de destino | La marina base es donde una embarcación reside y opera habitualmente; la de destino es donde recala en travesía. |
| Nave menor | Categoría de embarcación bajo un límite de tonelaje, sujeta a un régimen propio de matrícula, dotación y zarpe. |
| Pantalán | Estructura flotante que da acceso a las amarras y soporta las torretas de servicio. Sube y baja con la marea. |
| Patrón | Persona habilitada por la autoridad marítima para conducir una embarcación deportiva, según el título que posee. |
| Pintura antiincrustante | Recubrimiento del casco que impide la adherencia de organismos marinos. Su residuo de lijado es un residuo peligroso. |
| Plan de navegación | Declaración voluntaria del destino, la ruta, la duración estimada y las personas a bordo, dejada en tierra antes de zarpar. |
| Recalada | Llegada de una embarcación a un puerto o marina. En una marina de destino es la unidad de servicio de la embarcación visitante. |
| Ronda de pantalán | Recorrido de inspección visual del estado de las embarcaciones y de sus amarras. |
| Tren de fondeo | Conjunto de muerto, cadena, grillete y boya que sujeta una embarcación al fondo. Tiene vida útil y programa de inspección. |
| Travelift | Pórtico móvil que levanta embarcaciones con eslingas para sacarlas del agua o ponerlas en ella. |
| Varada | Operación de sacar una embarcación del agua para dejarla en tierra. |
| Varadero | Zona en tierra donde se ejecutan trabajos de casco, motor y aparejo sobre embarcaciones varadas. |
| Zarpe | Autorización de la autoridad marítima para que una embarcación salga a navegar, previa acreditación de sus condiciones y de su dotación. |

---

*Caso 07 · Servicio de Puerto Deportivo · TFEP-01/2026*
