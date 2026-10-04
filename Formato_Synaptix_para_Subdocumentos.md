# Formato Synaptix para los subdocumentos

Revisión de la plantilla del SD1: 3 de octubre de 2026. Guía interna para trasladar el formato; no forma parte del contenido de la oferta.

Se contrastó la fuente con el artículo 40 de las Bases Administrativas y las secciones 1 a 7, 9 y 11 de `instrucciones_extras.txt`. Esta revisión no confirma el resultado visual del PDF de Overleaf.

## Archivos que se trasladan desde el SD1

| Archivo | Aplicación en cada subdocumento |
|---|---|
| `estilo/propuesta-tecnica.sty` | Copiar la versión revisada: tipografía, índice, encabezado, pie, campos de firma, tablas y encabezado de referencias. |
| `config/identidad.tex` | Mantener colores, marca y tipografía comunes. |
| `config/metadatos.tex` | Mantener razón social, RUT, representante y licitación; establecer la versión y fecha de cada documento. |
| `componentes/portada.tex` | Copiar la portada común, con variantes para subdocumentos y formularios. Adaptar el número y título en el archivo principal. |
| `componentes/cierre.tex` | Adaptar sólo la estructura: Referencias y Declaración de uso de IA. Conservar las fuentes y atribuciones propias de cada SD. Usar el encabezado `referenciassynaptix` para las referencias. |

Conservar el capítulo, las referencias bibliográficas y la declaración de IA de cada subdocumento. El registro del SD1 describe su trabajo específico y no se copia a otro SD.

## Forma común

- Página carta y orientación vertical. Usar páginas horizontales sólo donde lo permitan las bases y el comunicado para material gráfico de gran formato o tablas de anexos.
- Cuerpo e índice en 11 puntos como mínimo. Tablas, figuras y sus fuentes en 9 puntos como mínimo al tamaño final impreso; no reducir una figura completa si con ello su texto queda bajo ese mínimo.
- Portada con marca, razón social, RUT, licitación, número y título del subdocumento, versión, fecha, clasificación y representante legal. Sin docente, asignatura, ponderaciones académicas ni instrucciones de edición.
- Redactar desde Synaptix y las funciones empresariales de sus integrantes. Las declaraciones de IA identifican herramienta, finalidad y alcance del trabajo humano; no narran solicitudes del usuario, decisiones de la conversación ni el origen externo de los antecedentes empresariales.
- Encabezado y pie comunes. Folio correlativo visible abajo a la derecha, incluida la portada; no reiniciar el contador al comenzar el índice o el capítulo.
- Campo de firma completa en portada y documentos principales y campo de media firma junto al folio de cada página. Incorporar las rúbricas antes de entregar: las líneas preparadas no son firmas.
- Índice detallado automático, con enlaces, títulos completos y folios coincidentes con los impresos. Incluir las subsecciones desarrolladas y los dos apartados del cierre.
- Títulos obligatorios con numeración, texto y orden exactos del comunicado. Ajustar el contador de capítulo para que las secciones, figuras y tablas usen el número del SD correspondiente.
- Texto de apertura inmediatamente bajo cada título; ninguna sección comienza directamente con otra sección, tabla, figura o lista.
- Figuras y tablas numeradas y tituladas, citadas antes de aparecer, con fuente y explicación posterior. «Elaboración propia» es válida cuando acompaña al elemento efectivamente insertado; no usar una leyenda aislada como sustituto de la figura.
- Tablas con encabezado corporativo, tipografía y bordes comunes; texto a la izquierda y cifras a la derecha. En el cuerpo, sintetizar sin párrafos dentro de las celdas, hasta cinco columnas como referencia y sin superar una página. Los listados completos van en anexos o formularios.
- Tablas de varias páginas con encabezado repetido y filas completas. Mantener identificadores, palabras y unidades legibles, sin texto vertical ni columnas que obliguen a partir palabras.
- Cierre sin numeración, en este orden: Referencias y Declaración de uso de IA. Ambos aparecen en el índice. Citas y lista bibliográfica en APA 7, con correspondencia entre ellas. Las citas a las bases identifican documento, capítulo o artículo y página; completar los folios del Caso 07 desde su PDF original, sin inventarlos. Las remisiones deben apuntar a secciones y archivos existentes.
- Declaración de IA con texto introductorio y las seis columnas exigidas, aun cuando la regla general del cuerpo use cinco como referencia. Incluir cada sección y cada anexo o formulario asociado; registrar quién verificó qué y consolidar en A-6.

## Archivos de entrega

- Exportar el subdocumento como `SYNAPTIX-SubdocumentoX.pdf`.
- Si hay anexos, entregarlos aparte como `SYNAPTIX-SubdocumentoX-Anexos.pdf`, con su identificación, índice, foliación y firmas.
- Entregar un formulario por archivo, `SYNAPTIX-Formulario-T-X.pdf`. Citarlo donde se utilice; no incrustarlo en el capítulo ni en sus anexos.
- Cada formulario abre con una portada empresarial independiente mediante `\PortadaFormulario{T-X}{Título}`, seguida del índice y los campos oficiales. La portada comparte el diseño del SD1 y muestra código, título, razón social, RUT, licitación, versión, fecha y campos de firma. Su folio es el primero y la numeración continúa en el índice. No copiar los datos del T-6 a otros formularios.
- Preparar el índice de cada sobre con los folios iniciales y los archivos efectivamente incluidos, conforme al artículo 40.3; no sustituye al índice de cada documento.
- Comprobar texto seleccionable, apertura del archivo, ausencia de contraseña, nomenclatura y tamaño total del sobre digital de hasta 500 MB, o la segmentación declarada cuando corresponda. Empaquetar según la instancia del T-22.

## Comprobaciones pendientes en Overleaf

1. Tras actualizar índice, bibliografía y referencias internas, comprobar enlaces y folios, incluida la portada. Cada archivo conserva una secuencia continua.
2. Revisar a tamaño impreso portada, firma, pie, organigramas y tablas: sin superposiciones, cortes, texto fuera del margen ni filas partidas.
3. Confirmar que los nombres y fechas de los metadatos corresponden al archivo exportado, y que se incorporaron las firmas.
4. Completar las verificaciones humanas, los folios de las citas y los nombres requeridos, y retirar marcadores o notas de edición antes de entregar. Mantener un registro fiel de la revisión efectiva; no declarar una revisión que no se haya realizado.

## Ajustes incorporados en esta revisión

El SD1 y su T-6 ahora usan índice de 11 puntos, datos informativos de portada y firma completa de 11 puntos, apertura de referencias común y portada de formulario reutilizable. Se retiró de la plantilla el comando que imprimía una instrucción de «texto de apertura por completar». La declaración de IA del SD1 registra los cambios.

Las portadas del SD1, SD13, T-6 y T-19 usan el mismo componente empresarial. Los dos formularios tienen portada independiente y numeración continua. El SD13 y T-19 comparten además índice y campo de firma completa de 11 puntos. SD2, SD4 y SD5 ya comparten la portada, identidad y hoja de estilo del SD1. Sus metadatos están completos y la numeración comienza en la portada sin reiniciarse en el índice. Los cinco proyectos conservan sus referencias y atribuciones de IA; cada registro declara los ajustes de presentación realizados.


## Aplicación a los archivos disponibles

Se aplicó la plantilla a SD1, SD2, SD4, SD5 y SD13, a los anexos A2.1–A2.7 y a los formularios existentes T-6 y T-19. No se generaron contenidos para los subdocumentos o formularios que aún no están disponibles.

| Proyecto | Archivo principal para exportar en Overleaf |
|---|---|
| SD1 | `SYNAPTIX-Subdocumento1.tex` |
| SD2 | `SYNAPTIX-Subdocumento2.tex` |
| Anexos del SD2 | `SYNAPTIX-Subdocumento2-Anexos.tex` |
| SD4 | `SYNAPTIX-Subdocumento4.tex` (carga la entrada existente `subdocumento12.tex`) |
| SD5 | `SYNAPTIX-Subdocumento5.tex` |
| SD13 | `SYNAPTIX-Subdocumento13.tex` |
| T-6 | `SYNAPTIX-Formulario-T-6.tex` |
| T-19 | `SYNAPTIX-Formulario-T-19.tex` |

Cada proyecto conserva copias locales de la plantilla para trasladarlo por separado. Al actualizar Overleaf, reemplazar también `estilo/`, `componentes/` y `config/`, y los archivos de capítulos o anexos modificados. Mantener las imágenes y utilizar XeLaTeX o LuaLaTeX y Biber, conforme a las dependencias de la plantilla.

Los anexos del SD2 usan `paginaHorizontalSynaptix`: márgenes corporativos transpuestos, encabezado y pie orientados con la página, y media firma y folio en el extremo inferior derecho. Sus 83 tablas conservan los registros y usan títulos, etiquetas, fuentes, encabezados repetidos y anchos adaptados al espacio disponible. El archivo de anexos incluye su presentación, referencias y declaración de IA.

Las 18 tablas del SD4 ajustan su ancho al área de texto e incluyen remisiones automáticas. Usan los mismos separadores horizontales entre filas y fondos alternados `SynSurface` y blanco del SD1, además del encabezado corporativo común. Se retiraron de estos cuadros los separadores de `booktabs` que producían una apariencia diferente. Las tres figuras del SD5 que excedían el margen ahora caben en él, y las figuras existentes tienen leyendas de fuente. El ciclo de invernada del SD13 conserva su contenido, con texto de 9 puntos y más espacio entre bandas, sin escalar el dibujo.

La revisión de las fuentes no sustituye la comprobación visual del PDF en Overleaf. Quedan por verificar los saltos de página, la ubicación efectiva de los pies en las hojas horizontales, los enlaces y folios del índice, y la legibilidad de las imágenes al tamaño impreso. Si una imagen queda por debajo de 9 puntos, preparar vistas de detalle desde el diagrama original; no recortarla ni ampliar una parte de la imagen. Los contenidos técnicos pendientes y las revisiones humanas siguen pendientes, y las firmas deben incorporarse antes de entregar.
