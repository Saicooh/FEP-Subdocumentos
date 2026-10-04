# Registro de cambios del SD5 para reaplicar

Fecha del registro: 3 de octubre de 2026.

Este registro es interno y queda fuera de `Subdocumento_5___SYNAPTIX`, para conservarse cuando se reemplace ese proyecto. La reaplicación sobre la nueva versión del equipo se completó el 3 de octubre de 2026; queda pendiente la comprobación visual en Overleaf. Las secciones siguientes conservan el registro previo como referencia histórica.

## Estado de la reaplicación

Se conservó el desarrollo nuevo de 5.4, las 21 tablas y las 17 figuras. El resultado y sus respaldos se documentan en [Reaplicación del SD5](C:/Users/Nijika/Documents/FEP-Subdocumentos/registros_cambios/SD5_2026-10-03/reaplicacion_01/Reaplicacion_SD5.md). La carpeta `reaplicacion_01` contiene las versiones recibida y reaplicada, la comparación y sus inventarios. Los respaldos originales se mantienen.

## Respaldo y comparación

- `SD5_con_correcciones.zip`: copia completa del estado actual del proyecto, incluidas fuentes, imágenes, bibliografía y configuración. Contiene los avances del equipo junto con las correcciones registradas.
- `antes_de_estandarizar.json`: fuentes disponibles inmediatamente antes de aplicar la estandarización del 3 de octubre. Las correcciones anteriores a esa captura ya estaban incorporadas.
- `cambios_estandarizacion.diff`: diferencias exactas de las fuentes respecto de esa captura. Sirve para localizar ajustes; aplicarlo exige comparar con la nueva versión.
- `manifest.json`: inventario, tamaños y SHA-256 de los archivos respaldados y del ZIP.

El ZIP se conserva como referencia. Para reaplicar los ajustes, partir de la nueva versión y combinar los cambios, conservando las revisiones técnicas, los datos, las referencias y las atribuciones que incorpore el equipo.

## Cambios que se deben conservar

| Archivo | Ajuste registrado |
|---|---|
| `estilo/propuesta-tecnica.sty` | Hoja de estilo compartida con SD1: página carta, tipografía, índice negro de 11 puntos, encabezados, pies, folios, campos de firma, tablas de 9 puntos y encabezado de referencias. Conserva `amsmath`, `float` y `comment`; incluye estilos vertical y horizontal y el entorno `paginaHorizontalSynaptix`. |
| `config/identidad.tex` | Identidad visual y tipográfica común. Coincide con la captura previa; mantener su compatibilidad con la hoja de estilo. |
| `componentes/portada.tex` | Portada empresarial reutilizable con razón social, RUT, licitación, representante, versión, fecha y clasificación; firma completa, media firma y folio. Numeración continua después de la portada. |
| `config/metadatos.tex` | Razón social Synaptix Ingeniería de Software SpA, RUT 76.913.482-4, licitación TFEP-01/2026, representante Ignacio Silva y oferta Puerto Deportivo Bahía Panitao. La captura usa versión 0.2, fecha 3 de octubre de 2026 y clasificación Confidencial; coordinar versión y fecha con la nueva emisión. |
| `subdocumento05.tex` | Numeración arábiga antes de la portada, sin reinicio de página después; portada titulada «Modelo y gestión de datos», índice automático, capítulo y cierre. Se retiró la carga redundante de `float`, ya incluida en el estilo. |
| `SYNAPTIX-Subdocumento5.tex` | Entrada de exportación que carga `subdocumento05.tex`, para obtener `SYNAPTIX-Subdocumento5.pdf`. |
| `componentes/cierre.tex` | Referencias mediante `referenciassynaptix`, seguidas de la Declaración de uso de IA; ambos apartados en el índice. Tabla de seis columnas con caption, etiqueta, encabezados repetidos, referencia previa y fuente. Registro editorial de José Lara, Líder de Operación / SRE, con control antes de la emisión. |
| `capitulo05.tex` | Correcciones de tamaños y leyendas de figuras; fuentes de tablas con el comando corporativo; retiro de ajustes locales de interlineado de tablas para que gobierne la hoja de estilo común. |

## Ajustes localizados en el capítulo

1. Conservar el capítulo «Introducción al Modelo y gestión de datos», su contador de capítulo en 4 y las cuatro secciones obligatorias: Modelo, Gestión de datos, Estrategia de migración y Estrategia de desempeño.
2. Retirar las redefiniciones locales `\renewcommand{\arraystretch}{1.2}` y `\renewcommand{\arraystretch}{1.15}` en los bloques de tablas donde impedían una configuración común. Conservar `tabcolsep` y las compensaciones de ancho necesarias para cada tabla.
3. Usar `\FuenteTabla{...}` para las leyendas activas de tablas, conservando el texto de fuente y las citas que corresponden a la versión nueva.
4. Cambiar las anchuras que excedían el margen a `width=\linewidth`: F5_12.png (antes 1.2), F5_13.png (antes 1.1) y F5_16.png (antes 1.2). Se conservaron las imágenes originales.
5. Incorporar las leyendas de fuente a las figuras existentes mediante `\FuenteFigura`. La tabla siguiente identifica los ajustes por imagen y etiqueta, que siguen siendo localizables si cambian sus números o posiciones.

| Figura/imagen | Etiqueta de la captura | Leyenda conservada |
|---|---|---|
| F5_1 a F5_11 | `fig:entidades_responsabilidades`, `fig:clientes_contratos`, `fig:operacion_maritima`, `fig:escuela_nautica`, `fig:varadero_contratistas`, `fig:combustible`, `fig:ambiente`, `fig:finanzas`, `fig:infraestructura`, `fig:auditoria`, `fig:notificaciones` | Modelo de datos de Synaptix; dominios y relaciones descritos en esta sección. |
| F5_12.png | `fig:datos_maestros` | Flujo de conciliación de Synaptix; autoridad y correspondencias descritas en esta sección. |
| F5_13.png | `fig:sincronizacion` | Flujo de sincronización de Synaptix; persistencia, acuses y aceptación descritos en esta sección. |
| F5_14.png | `fig:explotacion` | Arquitectura de persistencia de Synaptix; separación transaccional y analítica descrita en esta sección. |
| F5_15.png | `fig:ruta_migracion` | Estrategia de migración de Synaptix; etapas y controles descritos en esta sección. |
| F5_16.png | `fig:decision_corte` | Se conserva la fuente existente de PUCV (2026b, RT-05.11 y RT-20.02--RT-20.03), con el comando `\FuenteFigura`. |

La leyenda de F5_12 sustituyó un bloque comentado que no aparecía en el documento. Las leyendas se revisan contra las figuras de la nueva versión; si cambia una imagen o su origen, adaptar su atribución.

## Correcciones anteriores y criterios permanentes

La redacción presenta a Synaptix y a sus funciones empresariales. La declaración de IA identifica la herramienta, su finalidad y las responsabilidades de revisión; no narra pedidos ni decisiones de la conversación.

En calidad de datos se conserva la operación y su evidencia cuando existen lecturas, asociaciones, identidades o documentos pendientes. El pasaje localizado como «Lecturas, identidades y documentos pendientes» mantiene la lectura con medidor, época, secuencia, unidad y vigencia, y la separa del cálculo facturable hasta conciliarla. Una identidad provisional mantiene el hecho y su origen hasta la resolución trazable del propietario. Conservar ese comportamiento y una redacción centrada en el tratamiento de la información.

La captura previa a la estandarización ya incluía estos ajustes editoriales. Para recuperar su texto exacto, consultar el capítulo dentro del ZIP. No atribuir todo el contenido técnico del capítulo a estos cambios: el documento reúne trabajo del equipo.

## Reaplicación sobre la próxima versión

1. Identificar los archivos que reemplazó la versión nueva y comparar su contenido con el respaldo.
2. Mantener las secciones técnicas, imágenes, referencias y revisiones humanas incorporadas por el equipo.
3. Recuperar la portada, la numeración y los estilos comunes usando la versión vigente del SD1. Conservar dependencias adicionales válidas del proyecto nuevo.
4. Reaplicar los ajustes del capítulo por etiquetas e imágenes, conservando las fuentes nuevas y corrigiendo las anchuras o leyendas sólo donde siga correspondiendo.
5. Combinar la declaración de IA con las filas de los compañeros. La captura tiene dos filas: Plantilla base y Formato y registro de IA. No sustituir una declaración más completa por esas dos filas ni presentar revisiones pendientes como realizadas.
6. Verificar rutas, títulos, referencias, datos de tablas y correspondencia de citas. Conservar los pendientes técnicos que todavía no estén resueltos.
7. Revisar el PDF en Overleaf: saltos, folios, pies, tablas y tamaño de letra de las imágenes. Los campos de firma requieren las rúbricas antes de entregar. El trabajo se mantiene en los archivos existentes; no abrir otra pestaña del editor ni dedicar trabajo a compilar localmente.

El SD5 sigue en desarrollo. El respaldo no acredita que su contenido técnico ni la revisión visual estén terminados. No se modificaron los datos de sus tablas, su bibliografía ni sus imágenes durante la estandarización.
