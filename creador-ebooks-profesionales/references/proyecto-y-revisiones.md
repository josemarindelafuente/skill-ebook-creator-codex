# Archivos, revisiones y recuperación

Trabaja dentro de una carpeta propia del libro, en el destino elegido o en `ebooks/<nombre-corto>/` del espacio de trabajo. Antes de crearla comprueba que no exista otro proyecto con ese nombre. No sobrescribas proyectos ni borres versiones del usuario.

Estructura recomendada:

```text
ebooks/<nombre-corto>/
  proyecto.md
  estado.json
  indice.md
  estilo-visual.md
  editorial/
    introduccion-v01.md
    autor-y-creditos-v01.md
    cierre-v01.md
  capitulos/
    01-titulo-v01.md
    02-titulo-v01.md
  imagenes/
    portada-v01.png
    capitulo-01-v01.png
    infografia-01-v01.png
  fuentes.md
  produccion/
    visuales.md
    inventario-final.json
    control-calidad.md
    build_docx.py
  entregables/
    demo-v01.docx
    libro-final-v01.docx
  revision-visual/
```

Crea los archivos a medida que hacen falta; no entregues carpetas llenas de plantillas vacías. La extensión real de cada imagen debe coincidir con el archivo. El compilador puede ser Python o JavaScript según las herramientas disponibles.

## Fuente de verdad

`proyecto.md`: idea, lector, objetivo, idioma, tono, alcance, título, autor confirmado y decisiones con fecha. `estilo-visual.md`: dirección aprobada, formato, colores, fuentes, tratamiento de portada y visuales. `indice.md`: orden y objetivo de capítulos.

Cada Markdown de contenido lleva únicamente lo destinado al libro, con encabezados semánticos y enlaces de imágenes relativos al archivo, por ejemplo `![Descripción accesible](../imagenes/capitulo-01-v01.png)`. Pon los pies visibles como texto separado. No insertes aprobaciones, instrucciones de producción ni prompts en el manuscrito.

`produccion/visuales.md`: para cada imagen, propósito, capítulo, ubicación exacta, texto literal integrado, dirección tipográfica (familia o estilo, pesos, jerarquía, alineación y colores), prompt o método de creación, fuente si procede, ruta y feedback. Registra el resultado de la revisión de ortografía y legibilidad. Para infografías, registra también los datos verificados. Distingue insumos intermedios de la pieza completa lista para insertar: el inventario selecciona esta última.

`estado.json` debe guardar al menos:

- Identificador del proyecto y etapa actual.
- Decisiones pendientes y siguiente paso.
- Cada pieza: id, tipo, ruta, versión, estado (`borrador`, `en_revision`, `cambios_solicitados`, `aprobado`), hash SHA-256 y dependencias.
- Aprobaciones: fecha, respuesta real del usuario y piezas/versiones a las que aplica. Nunca fabriques respuestas ni fechas.
- Demo: ruta, versión y estados separados de revisión editorial y visual.
- Confirmación final: pendiente o confirmada, respuesta real, fecha y hash del inventario confirmado.

Codex mantiene estos archivos; el usuario no necesita editarlos. Calcula hashes con una herramienta local, por ejemplo `Get-FileHash -Algorithm SHA256`, no mediante estimación.

## Versiones y cambios

Conserva la versión aprobada al hacer una revisión. Crea una nueva versión y pásala a revisión. Una aprobación identifica una versión exacta, no cualquier futuro archivo con el mismo título.

La aprobación de una imagen se refiere a su composición completa, incluidos textos y tipografías. Si cambia un título, subtítulo, autor, rótulo o la dirección tipográfica, revisa las piezas afectadas y genera nuevas versiones cuando corresponda. Un cambio en Markdown no actualiza automáticamente el texto dentro de una imagen.

Antes de compilar, recalcula los hashes: si una pieza cambió externamente, no la trates como aprobada. Presenta el cambio y solicita revisión. Cambiar índice, título o estilo puede afectar otras piezas: identifica cuáles y revisa solo las afectadas. No invalidez todo por una corrección ajena a esas piezas.

El inventario final enumera explícitamente contenido editorial, capítulos e imágenes con ruta, versión, hash y orden de inclusión. Incluye también la versión de diseño aprobada. No ensambles usando un glob indiscriminado: podría incluir borradores, duplicados o versiones rechazadas.

La confirmación final se refiere a ese inventario. Si cambia el contenido o los visuales seleccionados, prepara otro inventario y solicita confirmación de la nueva selección. Ajustes técnicos de márgenes o saltos que no cambien las piezas aprobadas no requieren otra confirmación.

## Al retomar

Lee estado, proyecto, índice y estilo; comprueba la existencia de las piezas relevantes. Resume en pocas líneas dónde quedó el trabajo y retoma el próximo paso. Si falta un archivo aprobado, intenta localizar esa versión; no lo regeneres silenciosamente como si fuera el original. Una nueva pieza necesita revisión.
