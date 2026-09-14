# Producción visual y Word

## Herramientas y portabilidad

Al producir Word, usa la skill `documents` disponible y lee sus instrucciones actuales, incluidos el registro de operaciones y la revisión visual exigida. Resuelve los runtimes y bibliotecas mediante `load_workspace_dependencies` cuando esté disponible. No fijes rutas personales ni versiones de plugins en esta skill.

Para ilustraciones o fotografías generadas, usa la skill `imagegen` disponible y la herramienta integrada de generación de imágenes. Una descripción o prompt no reemplaza una imagen. No cambies silenciosamente a una API de pago ni solicites claves si la herramienta integrada funciona. Si faltan herramientas, explica qué etapa está bloqueada y continúa con el texto y las revisiones independientes. No declares completos visuales ausentes.

Si no hay skill de documentos, usa las capacidades locales verificadas para generar OOXML con una biblioteca compatible y un renderizador disponible. Si no puedes producir o renderizar un `.docx`, informa la limitación concreta y conserva los materiales; no presentes un documento sin inspección como un resultado final validado.

## Dirección visual

Usa la portada aprobada como referencia de paleta, estilo de ilustración, composición y tono. Conserva variedad de temas entre capítulos sin perder unidad. No impongas portadillas a página completa para todos los capítulos: acuerda con la demo si conviene una apertura completa o una imagen integrada.

Prefiere título, subtítulo, autor y números de capítulo como texto editable en Word, con arte sin texto cuando ayude a evitar errores. Comprueba ortografía de cualquier texto incrustado en imágenes. Para editar una imagen local, inspecciónala antes y sigue la herramienta de edición disponible.

Guarda copias de las imágenes seleccionadas dentro del proyecto, preserva su formato y relación de aspecto, y enlázalas desde el Markdown. No dependas de enlaces remotos ni de archivos temporales o del historial del chat. Nunca reemplaces un archivo aprobado sin conservar su versión.

Diseña para el tamaño físico acordado. Evalúa resolución a tamaño de impresión y no prometas calidad de 300 ppp por cambiar solo los metadatos. Evita ampliaciones que degraden el arte; genera una alternativa adecuada cuando haga falta.

## Infografías

Selecciona la estructura por el contenido: secuencia para pasos, cuadrantes para cuatro componentes, comparación para alternativas, diagrama para relaciones, gráfico para datos verificables. No fuerces cuatro categorías si el contenido tiene otra estructura.

Mantén textos cortos, jerarquía clara, contraste y espacio de seguridad. No agregues datos ni conclusiones para llenar huecos. Para cifras, tablas y rótulos exactos, usa diagramación determinista o elementos editables, con ilustraciones generadas si aportan valor. Exporta una versión incrustable compatible con Word, preservando además la fuente editable cuando exista. Verifica rótulos, flechas, unidades y correspondencia con el capítulo.

## Compilación

Mantén un constructor reproducible dentro de `produccion/`, adaptado al diseño aprobado. Tanto demo como final deben usar la misma configuración de estilos. No hace falta implementar un convertidor Markdown universal; sí conservar fielmente las estructuras que contiene el manuscrito.

- Interpreta encabezados, párrafos, énfasis, listas, enlaces, tablas e imágenes presentes; no entregues sintaxis Markdown cruda.
- Usa estilos nativos de Word y texto editable, sin convertir las páginas enteras del libro en capturas.
- Configura tamaño físico, márgenes, tipografías disponibles, jerarquías, interlineado y saltos de sección deliberadamente.
- Incluye portada integrada y capítulos completos en el orden aprobado. Configura aperturas, encabezados y numeración sin números indeseados en la tapa.
- Inserta imágenes en el archivo, con proporciones correctas y texto alternativo; conserva pies y referencias. Evita vínculos a recursos externos.
- Añade índice navegable cuando el alcance lo justifique. Actualiza campos si las herramientas lo permiten y comprueba su resultado; no inventes números de página ni anuncies un índice actualizado si requiere actualización manual en Word.
- Evita viudas, títulos huérfanos, pies separados, tablas recortadas, páginas vacías accidentales y texto ilegible. Conserva tablas para información que realmente requiere comparación o filas de datos.
- Nunca sustituyas capítulos por resúmenes para resolver problemas de paginación.

Antes del final, comprueba que todos los elementos del inventario existen, conservan su hash y tienen aprobación. Verifica la confirmación del inventario. Para la demo, selecciona explícitamente sus componentes sin activar este requisito final.

## Comprobación de entrega

1. Comprueba el paquete `.docx`, extracción de texto y relaciones de imágenes. Contrasta con los Markdown aprobados para detectar secciones omitidas, duplicaciones o texto truncado. Verifica que no haya notas internas ni marcadores pendientes.
2. Ejecuta `render_docx.py` de la skill de documentos cuando esté disponible y abre los PNG de todas las páginas, no solo la portada. Corrige errores de composición y vuelve a renderizar la versión que se entregará.
3. Guarda en `produccion/control-calidad.md` el archivo revisado, fecha, método, páginas inspeccionadas, comprobaciones y limitaciones reales. Distingue validación por renderizador de apertura en Microsoft Word.
4. Entrega Word mediante enlace absoluto. Los Markdown y las imágenes siguen accesibles para revisión y reutilización. Las capturas de QA y PDF intermedios se conservan para control interno, salvo pedido del usuario.
