# Creador de ebooks profesionales

Una skill para Codex que acompaña a personas con poca experiencia desde una idea inicial hasta un libro completo en **Microsoft Word**, con portada, imágenes y un diseño interior coherente.

El proceso se desarrolla mediante una conversación: describes lo que tienes en mente, eliges entre propuestas y revisas los avances. Codex se encarga de redactar, guardar los archivos, generar los recursos visuales y preparar el documento.

No necesitas saber programar, escribir Markdown ni manejar herramientas de diseño.

## Qué es esta skill

Una skill es un conjunto de instrucciones y referencias que orienta a Codex para realizar una tarea de manera consistente. Esta se basa en el documento **«System Prompt 2.0 — Arquitecto de eBooks Premium y Productos Digitales»**, adaptado a un flujo de trabajo con archivos locales, revisiones y entrega en Word.

Su objetivo es que puedas participar en las decisiones de tu libro sin tener que resolver la parte técnica. La escritura y el diseño avanzan por etapas, con una demo temprana para comprobar el resultado antes de desarrollar todo el contenido.

## Cómo comenzar

Con la skill disponible en Codex, inicia una conversación y escribe, por ejemplo:

```text
Usa $creador-ebooks-profesionales.
Quiero crear un ebook sobre organización del hogar para personas
que tienen poco tiempo. Tengo algunas ideas, pero necesito ayuda
para ordenar el contenido y elegir el diseño.
```

También puedes comenzar con una idea mucho más breve. No es necesario tener un título, un índice ni capítulos escritos.

La carpeta que contiene la skill se llama `creador-ebooks-profesionales`. Su archivo principal es `SKILL.md`; la carpeta `references` contiene las pautas de escritura, revisión y producción. Para instalarla manualmente en otro entorno, copia la carpeta completa dentro de la carpeta personal de skills de Codex, normalmente `~/.codex/skills/`.

## El recorrido, paso a paso

### 1. Describir tu idea

Codex comienza pidiéndote que expliques, con tus palabras, de qué quieres que trate el ebook. Te ayuda a definir:

- A quién estará dirigido.
- Qué aprenderá, resolverá o experimentará el lector.
- Qué enfoque te interesa darle.
- Qué conocimientos, experiencias o materiales puedes aportar.
- Qué tono prefieres y para qué quieres utilizar el libro.

Las preguntas se hacen de forma gradual. Si ya proporcionaste información, se utiliza sin volver a preguntarla. Cuando el tema es demasiado amplio, la skill propone enfoques más concretos para que puedas elegir.

En ficción, memorias u otros géneros, adapta las preguntas a la historia, la voz y la experiencia de lectura.

### 2. Elegir el nombre del ebook

La skill propone tres títulos distintos, acompañados de subtítulos y una explicación breve. Recomienda una opción, pero puedes elegir otra, combinar propuestas o pedir nuevas alternativas.

El título elegido queda registrado para mantener la coherencia entre la portada y el contenido.

### 3. Definir el índice y el alcance

Codex presenta una propuesta de capítulos con el objetivo de cada uno y el orden de lectura. También plantea una extensión aproximada, ajustada al tema y a la profundidad que buscas.

Puedes agregar, quitar, reorganizar o cambiar capítulos antes de comenzar la redacción. La cantidad de páginas no se considera definitiva hasta que el libro esté maquetado.

**Resultado de esta etapa:** un índice acordado que funciona como guía para escribir el libro.

### 4. Elegir el diseño de portada y del interior

La skill te pregunta cómo te gustaría que se vea la portada: qué sensación quieres transmitir, qué colores te gustan y si prefieres fotografías, ilustraciones o un diseño centrado en el texto.

Si no tienes una preferencia clara, ofrece direcciones visuales fáciles de comparar. Puedes aportar referencias, aunque no es obligatorio.

A partir de tus respuestas, propone una identidad visual con colores, tipografías, composición y estilo de imágenes. También acuerda el formato de página; A4 vertical es una opción inicial.

Codex genera una portada real con las herramientas disponibles, te la muestra y solicita tus comentarios. Esa dirección visual se aplica después al interior, a las aperturas de capítulo y a las infografías.

**Resultado de esta etapa:** una portada aprobada y una dirección de diseño para el libro.

### 5. Preparar el primer capítulo y una demo en Word

Antes de desarrollar el resto del libro, Codex redacta el primer capítulo en un archivo `.md` y lo presenta para revisión. Un archivo Markdown es un documento de texto con una estructura sencilla de títulos, párrafos y listas; puedes revisarlo sin conocer su sintaxis.

La demo incluye normalmente:

- La portada.
- Una introducción breve, si aporta contexto.
- El primer capítulo, preferentemente completo.
- Una imagen relacionada con ese capítulo.
- Un ejemplo o recurso práctico, si corresponde al género.
- Una infografía cuando ayude a explicar el contenido.

Con esos materiales, genera un archivo como `demo-v01.docx`. Codex revisa visualmente sus páginas antes de entregártelo.

La demo permite evaluar el aspecto real del libro: portada, tamaño del texto, espacios, imágenes, estilo interior y profundidad del contenido. Puedes pedir cambios y recibir una nueva versión antes de avanzar.

**La aprobación del diseño y la del texto se registran por separado.** Que te guste la apariencia no significa que hayas aprobado automáticamente el contenido. La demo puede producirse sin la confirmación que se pedirá más adelante para el Word final.

### 6. Crear y revisar cada capítulo

Con la dirección acordada, se repite este ciclo para los capítulos restantes:

1. Codex presenta el objetivo del capítulo y consulta si quieres aportar experiencias, ejemplos o puntos específicos que todavía no hayas indicado.
2. Redacta el capítulo completo y lo guarda en su propio archivo `.md`.
3. Revisa claridad, continuidad, repeticiones y afirmaciones que requieran verificación.
4. Genera al menos una imagen pertinente, en el estilo visual acordado.
5. Propone infografías cuando el contenido se beneficie de una explicación visual y genera las seleccionadas.
6. Te entrega el enlace al capítulo y muestra los recursos visuales para que puedas revisarlos.
7. Aplica tus comentarios y registra las versiones que apruebas.

Puedes responder de forma natural, por ejemplo:

```text
El texto del capítulo está aprobado. Quiero cambiar la imagen
por una ilustración más cálida y con menos elementos.
```

```text
Me gusta la imagen, pero necesito que el ejemplo del capítulo
sea más sencillo y esté pensado para alguien que empieza de cero.
```

El flujo habitual avanza de a un capítulo. Si pides trabajar varios juntos, se mantienen igualmente archivos y revisiones individuales. El primer capítulo aprobado en la demo se reutiliza; no se reescribe automáticamente.

### 7. Completar las páginas complementarias

Además de los capítulos, se preparan y revisan las piezas que correspondan al libro:

- Introducción.
- Información del autor.
- Créditos y fuentes.
- Avisos pertinentes al tema, cuando sean necesarios.
- Conclusión y próximos pasos para el lector.

La skill no inventa biografías, credenciales, testimonios ni enlaces. Si faltan datos opcionales, propone completarlos u omitirlos de manera acordada para evitar textos pendientes en la edición final.

### 8. Revisar el conjunto y confirmar el Word final

Una vez terminadas las piezas, Codex revisa la coherencia del libro completo: orden, continuidad, ortografía, fuentes, imágenes y cumplimiento del índice.

Después presenta un inventario de los capítulos y recursos aprobados, con las versiones que se incluirán, y pregunta:

> ¿Confirmas que genere la versión final en Word con estos capítulos y estas imágenes aprobadas?

**El Word final se genera únicamente después de tu confirmación explícita sobre esa selección.** El silencio o la aprobación de una pieza aislada no sustituyen esta confirmación.

Si todavía faltan revisiones, se resuelven primero. Si cambia el contenido o la selección de imágenes después de confirmar, se presenta la selección actualizada para una nueva confirmación.

### 9. Generar y comprobar el archivo final

Tras la confirmación, Codex reúne los archivos aprobados en el orden acordado y genera el `.docx`.

La conversión conserva el contenido completo: no resume capítulos ni introduce cambios editoriales sin revisión. El texto permanece editable en Word y las imágenes se incorporan dentro del documento.

La comprobación incluye:

- Correspondencia entre el Word y los archivos aprobados.
- Presencia de capítulos e imágenes, sin duplicaciones ni omisiones.
- Títulos, listas, tablas y numeración.
- Proporciones y legibilidad de las imágenes.
- Saltos de página, márgenes y ausencia de recortes o superposiciones.
- Inspección visual de todas las páginas mediante un renderizador.

Si aparecen defectos de composición, se corrigen y se vuelve a revisar. La inspección mediante renderizador se distingue de una apertura directa en Microsoft Word.

### 10. Recibir el libro y conservar sus materiales

Recibes un enlace al Word final, por ejemplo `libro-final-v01.docx`, junto con la ubicación de los capítulos y las imágenes del proyecto.

Los archivos de trabajo se conservan para que puedas retomar el ebook, solicitar cambios o preparar una nueva edición.

## Cómo se organizan los archivos

Cada libro tiene una carpeta propia. Esta es una estructura orientativa; los archivos se crean a medida que se necesitan:

```text
ebooks/nombre-del-libro/
├── proyecto.md                 Idea y decisiones del proyecto
├── estado.json                 Avances, versiones y aprobaciones
├── indice.md                   Orden y objetivos de los capítulos
├── estilo-visual.md             Diseño acordado
├── fuentes.md                  Referencias utilizadas
├── editorial/                  Introducción, autor, créditos y cierre
├── capitulos/                  Un archivo .md por capítulo y versión
├── imagenes/                   Portada, imágenes e infografías
├── produccion/                 Inventario y controles de calidad
├── entregables/                Demo y Word final
└── revision-visual/             Archivos internos de inspección
```

Codex mantiene esta organización. No necesitas administrar los archivos técnicos para utilizar la skill.

## Revisiones y continuidad

Cada pieza puede estar en borrador, en revisión, con cambios solicitados o aprobada. Una aprobación corresponde a una versión concreta. Si solicitas cambios sobre una pieza aprobada, se conserva la versión anterior y la nueva pasa por revisión.

La skill comprueba que los archivos seleccionados no hayan cambiado desde su aprobación. Esto evita incorporar por error borradores o versiones diferentes en el Word final.

Para continuar otro día, indica la carpeta del proyecto y pide retomar el trabajo. Codex utiliza los registros guardados para identificar qué está listo y qué falta; necesita tener acceso a esos archivos.

## Atajos opcionales

Puedes conversar normalmente o utilizar estos atajos dentro del flujo de la skill:

| Atajo | Para qué sirve |
| --- | --- |
| `/nuevo` | Comenzar otro proyecto sin borrar el anterior. |
| `/status` | Consultar el avance y el siguiente paso. |
| `/estructura` | Trabajar sobre el índice. |
| `/portada` | Trabajar sobre la portada. |
| `/demo` | Preparar o revisar la muestra en Word. |
| `/capitulo N` | Trabajar sobre un capítulo específico. |
| `/infografia` | Proponer o desarrollar una infografía. |
| `/auditoria` | Revisar el proyecto completo. |
| `/final` | Iniciar la revisión y confirmación de la edición final. |

Estos atajos son instrucciones conversacionales para la skill. `/final` no aprueba automáticamente piezas pendientes ni reemplaza la confirmación del inventario.

## Herramientas necesarias y alcance

Para completar el proceso, el entorno de Codex necesita acceso a archivos, generación de imágenes y herramientas para crear y renderizar documentos Word. La skill utiliza las capacidades de documentos e imágenes disponibles en el entorno.

Si falta alguna herramienta, Codex debe explicar qué parte está bloqueada y continuar con las tareas independientes que sí pueda realizar. Una descripción de imagen no cuenta como imagen generada, y un documento sin inspección no se presenta como un Word final validado.

Las infografías se incluyen cuando aportan valor. PDF, materiales promocionales, bonos y estrategias de venta son extras opcionales que se realizan si los solicitas.

## Créditos

**Creación y dirección de la skill: José Marin de la Fuente.**

Sitio web: [www.marindelafuente.com.ar](https://www.marindelafuente.com.ar)

Basada en el documento «System Prompt 2.0 — Arquitecto de eBooks Premium y Productos Digitales» y adaptada para un proceso guiado de creación de ebooks en Codex.
