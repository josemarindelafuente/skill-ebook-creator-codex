# Producción visual y Word

## Herramientas y portabilidad

Al producir Word, usa la skill `documents` disponible y lee sus instrucciones actuales, incluidos el registro de operaciones y la revisión visual exigida. Resuelve los runtimes y bibliotecas mediante `load_workspace_dependencies` cuando esté disponible. No fijes rutas personales ni versiones de plugins en esta skill.

Para ilustraciones o fotografías generadas, usa la skill `imagegen` disponible y la herramienta integrada de generación de imágenes. Una descripción o prompt no reemplaza una imagen. No cambies silenciosamente a una API de pago ni solicites claves si la herramienta integrada funciona. Si faltan herramientas, explica qué etapa está bloqueada y continúa con el texto y las revisiones independientes. No declares completos visuales ausentes.

Si no hay skill de documentos, usa las capacidades locales verificadas para generar OOXML con una biblioteca compatible y un renderizador disponible. Si no puedes producir o renderizar un `.docx`, informa la limitación concreta y conserva los materiales; no presentes un documento sin inspección como un resultado final validado.

## Dirección visual

Usa la portada aprobada como referencia de paleta, estilo de ilustración, composición y tono. Conserva variedad de temas entre capítulos sin perder unidad. No impongas portadillas a página completa para todos los capítulos: acuerda con la demo si conviene una apertura completa o una imagen integrada.

Entrega cada imagen como una composición editorial terminada con textos y tipografías integrados. El usuario debe poder utilizar la pieza por sí sola, con el mismo diseño que ve en la demo y en el Word final. No delegues la colocación de textos en Canva ni consideres terminado un fondo que dependa de texto añadido en Word.

Antes de generar cada pieza, registra el texto exacto y la dirección tipográfica. Reutiliza los títulos, subtítulos y datos ya acordados sin volver a preguntarlos; presenta los textos nuevos junto con la pieza para revisión. Usa los siguientes criterios:

- Tapa: título, subtítulo acordado y autor o marca si el usuario indicó que deben aparecer. Compón una jerarquía que priorice el título y conserve espacio de lectura.
- Apertura de capítulo: número y título exactos, con una composición propia dentro de la misma identidad visual. Una frase breve es opcional, si aporta valor.
- Imágenes adicionales: título breve, rótulos o texto explicativo vinculado al concepto representado. Evita repetir el título del capítulo en todas ellas o agregar frases de relleno.
- Infografías: título, etiquetas, pasos y datos necesarios, integrados en una composición completa y legible.

Especifica en el prompt el texto literal, respetando acentos, signos y mayúsculas, además del estilo tipográfico, pesos, tamaños relativos, jerarquía, alineación, color y márgenes. Utiliza la portada aprobada como referencia visual cuando la herramienta lo permita. No prometas que una fuente generada coincide exactamente con una familia instalada si no puedes verificarlo.

Inspecciona cada imagen completa y sus textos al tamaño de lectura previsto. Comprueba palabra por palabra la ortografía, números, acentos, texto faltante o inventado, contraste, cortes y consistencia tipográfica. OCR puede ayudar a detectar errores, pero no sustituye la inspección visual. Si falla, corrige con la herramienta de edición o regenera la pieza y vuelve a comprobarla; no elimines los textos como solución ni marques la pieza como aprobada por tu cuenta. Para editar una imagen local, inspecciónala antes y sigue la herramienta de edición disponible.

Cuando se necesite una familia tipográfica exacta que la generación no reproduzca, explica la limitación y plantea composición tipográfica determinista como alternativa. Si el usuario autoriza ese método para editar o componer la imagen, usa fuentes disponibles y exporta igualmente una pieza final con todo el texto integrado. Los insumos sin texto y los archivos de composición no sustituyen esa entrega.

Guarda copias de las imágenes seleccionadas dentro del proyecto, preserva su formato y relación de aspecto, y enlázalas desde el Markdown. No dependas de enlaces remotos ni de archivos temporales o del historial del chat. Nunca reemplaces un archivo aprobado sin conservar su versión.

Diseña para el tamaño físico acordado. Evalúa resolución a tamaño de impresión y no prometas calidad de 300 ppp por cambiar solo los metadatos. Evita ampliaciones que degraden el arte; genera una alternativa adecuada cuando haga falta.

## Infografías

Selecciona la estructura por el contenido: secuencia para pasos, cuadrantes para cuatro componentes, comparación para alternativas, diagrama para relaciones, gráfico para datos verificables. No fuerces cuatro categorías si el contenido tiene otra estructura.

Mantén textos cortos, jerarquía clara, contraste y espacio de seguridad. No agregues datos ni conclusiones para llenar huecos. Para gráficos y diagramas creados desde datos, puede utilizarse diagramación determinista con tipografía precisa; para editar imágenes generadas, sigue el método y las autorizaciones de la herramienta de imágenes. Exporta una pieza completa con todo el texto integrado, compatible con Word, preservando además la fuente editable cuando exista. Verifica rótulos, flechas, unidades y correspondencia con el capítulo.

## Compilación

Mantén un constructor reproducible dentro de `produccion/`, adaptado al diseño aprobado. Tanto demo como final deben usar la misma configuración de estilos. No hace falta implementar un convertidor Markdown universal; sí conservar fielmente las estructuras que contiene el manuscrito.

- Interpreta encabezados, párrafos, énfasis, listas, enlaces, tablas e imágenes presentes; no entregues sintaxis Markdown cruda.
- Usa estilos nativos de Word y texto editable, sin convertir las páginas enteras del libro en capturas.
- El texto narrativo del libro permanece editable; los textos integrados en las piezas gráficas forman parte de esas imágenes y no se anuncian como editables en Word. Inserta las piezas completas aprobadas sin reconstruir su tipografía durante la compilación. Conserva encabezados semánticos para navegación e índice, evitando duplicar visualmente el título de una portadilla de forma innecesaria.
- Configura tamaño físico, márgenes, tipografías disponibles, jerarquías, interlineado y saltos de sección deliberadamente.
- Incluye portada integrada y capítulos completos en el orden aprobado. Configura aperturas, encabezados y numeración sin números indeseados en la tapa.
- Inserta imágenes en el archivo, con proporciones correctas y texto alternativo; conserva pies y referencias. Evita vínculos a recursos externos.
- Incluye siempre un índice de contenidos visible, editable y navegable en el Word final, salvo omisión solicitada expresamente por el usuario. Aplica las reglas de la sección siguiente; no basta con crear `indice.md` ni activar el panel de navegación de Word.
- Evita viudas, títulos huérfanos, pies separados, tablas recortadas, páginas vacías accidentales y texto ilegible. Conserva tablas para información que realmente requiere comparación o filas de datos.
- Nunca sustituyas capítulos por resúmenes para resolver problemas de paginación.

Antes del final, comprueba que todos los elementos del inventario existen, conservan su hash y tienen aprobación. Verifica la confirmación del inventario. Para la demo, selecciona explícitamente sus componentes sin activar este requisito final.

## Índice de contenidos en Word

- Ubícalo después de la tapa y las páginas preliminares que correspondan, antes del cuerpo del libro, con el encabezado «Índice». Su diseño debe acompañar la identidad visual aprobada, pero se construye como texto de Word, no como imagen.
- Incluye todos los capítulos con los títulos exactos y en el orden del inventario aprobado. Añade introducción, conclusión y anexos cuando existan; incluye subsecciones si aportan orientación y no vuelven excesivamente largo el índice. Excluye la tapa y el propio índice.
- Prefiere una tabla de contenido nativa de Word basada en encabezados semánticos. Si los títulos están integrados en imágenes, usa marcadores o campos de entrada de índice asociados a las aperturas para conservar destinos correctos sin duplicar títulos visibles innecesariamente.
- Cada entrada debe enlazar internamente con la sección correspondiente. Incluye números de página reales de la edición maquetada cuando puedan calcularse y verificarse. Actualiza los campos después de insertar todas las piezas y de cualquier cambio que afecte la paginación, y vuelve a renderizar hasta que las referencias coincidan con las páginas finales.
- No entregues un campo de índice vacío o con un mensaje de actualización como único índice. Si el entorno no puede materializar una tabla de contenido nativa, crea un índice visible con hipervínculos internos. Si no puedes verificar la paginación, omite los números y comunica esa limitación; no omitas el índice ni inventes páginas. No anuncies actualización automática o páginas verificadas cuando no lo estén.
- Comprueba que todas las entradas tengan un destino existente y correcto, que no falte ningún capítulo ni haya duplicados y que los números visibles coincidan con la numeración del documento. La comprobación debe cubrir también capítulos cuya apertura sea una imagen.
- En la demo, incluye un índice de las secciones presentes para revisar su aspecto. Un esquema adicional del libro futuro debe identificarse como provisional y no simular enlaces o páginas inexistentes.

## Comprobación de entrega

1. Comprueba el paquete `.docx`, extracción de texto y relaciones de imágenes. Contrasta con los Markdown aprobados para detectar secciones omitidas, duplicaciones o texto truncado. Verifica que no haya notas internas ni marcadores pendientes. Comprueba el índice visible, la cobertura de capítulos, los destinos de sus enlaces y las páginas mostradas según las reglas anteriores.
2. Ejecuta `render_docx.py` de la skill de documentos cuando esté disponible y abre los PNG de todas las páginas, no solo la portada. Corrige errores de composición y vuelve a renderizar la versión que se entregará.
3. Guarda en `produccion/control-calidad.md` el archivo revisado, fecha, método, páginas inspeccionadas, comprobaciones y limitaciones reales. Distingue validación por renderizador de apertura en Microsoft Word.
4. Entrega Word mediante enlace absoluto. Los Markdown y las imágenes siguen accesibles para revisión y reutilización. Las capturas de QA y PDF intermedios se conservan para control interno, salvo pedido del usuario.
