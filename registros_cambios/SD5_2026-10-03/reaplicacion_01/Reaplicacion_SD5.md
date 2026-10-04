# Reaplicación de cambios del SD5

3 de octubre de 2026. Registro interno, fuera del proyecto de entrega.

La reaplicación se completó sobre la nueva versión del equipo. El proyecto vigente está en `Subdocumento_5___SYNAPTIX`; su entrada para Overleaf es `SYNAPTIX-Subdocumento5.tex`.

## Cambios incorporados

- Portada, identidad, estilos, pies, firmas, índice y numeración continua conforme al SD1. Se recuperaron los metadatos de la emisión común.
- Referencias y declaración de IA con la estructura común. El registro conserva la plantilla base e identifica el alcance editorial de José Lara, Líder de Operación / SRE. No declara revisiones humanas pendientes como realizadas.
- Tamaños de las figuras F5_12, F5_13 y F5_16 ajustados al margen; fuentes en las 17 figuras y comandos corporativos de leyendas. Se retiraron 21 ajustes locales de interlineado de tablas.
- Redacción sobre datos pendientes, origen de residuos, respaldo de datos históricos y estimación de carga centrada en los criterios operacionales de Synaptix. Se ajustaron las atribuciones del cuadro de calidad y los ejemplos de plantilla, conservando las fuentes citadas.

Se modificaron `estilo/propuesta-tecnica.sty`, `componentes/portada.tex`, `config/metadatos.tex`, `subdocumento05.tex`, `componentes/cierre.tex`, `componentes/ejemplos.tex` y `capitulo05.tex`.

## Contenido conservado y comprobaciones

La sección 5.4 conserva el desarrollo nuevo del equipo. Los 21 bloques de tablas del capítulo son idénticos a los recibidos, incluidos sus datos, cálculos, títulos y etiquetas. Se conservaron las 17 figuras y todas las imágenes recibidas, incluidas las revisiones de F5_15 y F5_16 y la nueva F5_17. La bibliografía y `latexmkrc` permanecen idénticos a la versión recibida.

Se comprobaron la estructura de las fuentes, las rutas activas, las citas bibliográficas, las etiquetas, los títulos de las cuatro secciones y la numeración desde la portada. El estilo, la portada y la identidad coinciden con el SD1. Ambos ZIP de esta reaplicación pasaron la comprobación de integridad.

## Respaldos

- `SD5_recibido.zip` y `manifest_recibido.json`: versión nueva antes de reaplicar los ajustes.
- `SD5_reaplicado.zip` y `manifest_reaplicado.json`: resultado completo e inventario con SHA-256.
- `cambios_reaplicados.diff`: comparación exacta con la versión recibida.

Los respaldos originales de `SD5_2026-10-03` se conservaron. El estado de la reaplicación se actualizó en `Registro_SD5.md`.

## Pendientes

El SD5 sigue en desarrollo. Esta reaplicación no acredita que las estimaciones técnicas, las remisiones a otros subdocumentos o los anexos estén completos. El equipo debe completar su revisión técnica y declarar los usos de IA de sus secciones según corresponda.

En Overleaf quedan por comprobar saltos, folios, tablas, pies, firmas y legibilidad de las imágenes al tamaño impreso. Para trasladar el resultado, actualizar el proyecto completo, incluidos `estilo/`, `componentes/`, `config/`, capítulos e imágenes, y usar `SYNAPTIX-Subdocumento5.tex` como archivo principal.
