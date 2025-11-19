**Qué es Markdown**

Markdown es un lenguaje de marcado ligero creado por JohnGruber y Aaron Swartz en 2004. Su principal objetivo es que el texto plano sealo más legible posible, tanto en su forma de entrada (el código) como una vezrenderizado (la salida). Permite a los usuarios escribir contenido utilizandouna sintaxis sencilla y fácil de entender —como asteriscos para negritas oguiones para listas— que luego se puede convertir en HTML u otros formatos parasu visualización. Esto significa que puedes dar formato (encabezados, listas,enlaces, etc.) a tu texto usando caracteres simples sin la complejidad del HTMLo un procesador de texto pesado.

**Uso en Proyectos de Software**

En proyectos de software, Markdown se utiliza extensamentepor varias razones clave, principalmente para la documentación:

**Archivos README**

 Casi todos los proyectos de software incluyen unarchivo README.md (la extensión .md o .markdown indica el formato Markdown) quees lo primero que ve un usuario o colaborador. Este archivo describe elproyecto, cómo instalarlo y cómo usarlo.

**Documentación General**

 Es el formato preferido para archivos de contribución(CONTRIBUTING.md), licencias (LICENSE.md), guías básicas y documentacióninterna.

**Sistemas de Control de Versiones**

 Plataformas como GitHub, GitLab y Bitbucket renderizanarchivos Markdown directamente, haciéndolos legibles y con buen formato sinnecesidad de pasos adicionales.

**Markdown y GitHub**

 Sinergia, Ventajas y Desventajas

GitHub utiliza una versión extendida de Markdown llamadaGitHub Flavored Markdown (GFM). Esto permite características adicionales comolistas de tareas (checkboxes), tablas, resaltado de sintaxis de código ymenciones de usuarios, lo que lo hace ideal para la colaboración y ladocumentación técnica.

**Ventajas de usar Markdown con GitHub**

**Legibilidad Universal**

Los archivos son legibles incluso en texto plano, peroGitHub los convierte automáticamente en páginas web atractivas y bienestructuradas (por ejemplo, el README en la página principal del repositorio).

**Simplicidad y Velocidad**

 Es mucho más rápido escribir documentación en Markdownque en HTML o con un editor WYSIWYG, lo que acelera el proceso dedocumentación.

**Control de Versiones Efectivo**

 Como los archivos Markdown son solo texto plano, lossistemas como Git pueden rastrear y gestionar los cambios (diferencias o diffs)de manera muy eficiente.

Soporte de Características Avanzadas: GFM soporta lasintaxis de GitHub para referencias a issues y pull requests (#123), lo cual escrucial para la gestión de proyectos.

**Desventajas de usar Markdown con GitHub**

**Funcionalidad Limitada**

Markdown, por diseño, es simple. Si necesitas un diseño muycomplejo, scripts incrustados o interactividad avanzada, Markdown no essuficiente y tendrás que recurrir a HTML o un generador de sitios estáticos máspotente.

**Estandarización Variable**

 Aunque GFM es muy popular, hay variaciones entrediferentes implementaciones de Markdown. Lo que funciona en GitHub podría norenderizarse exactamente igual en otra plataforma.

**Dependencia de la Plataforma**

 Para la mejor experiencia visual, dependes de queGitHub renderice el archivo. Si el archivo se visualiza en un entorno que no esGitHub, se verá solo como texto plano con los caracteres de formato visibles.