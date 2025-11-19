# Sistema de Gestión de Biblioteca Descripción breve:
Pequeño sistema para registrar libros y préstamos.
-1. Propósito y alcance:
Propósito: El propósito del sistema es proporcionar una herramienta sencilla para la
gestión de una biblioteca pequeña (por ejemplo, de una escuela o comunidad),
permitiendo registrar libros y usuarios, administrar préstamos y devoluciones, y
consultar el estado de los ejemplares.
Alcance:
 Registro y edición de libros (título, autor, editorial, año, categoría, ISBN opcional).
 Registro y edición de usuarios (nombre, identificación, contacto o correo).
 Registro de préstamos y devoluciones con fecha de préstamo y fecha esperada de
devolución.
 Consulta de libros disponibles y libros en préstamo.
 Restricciones: no contempla gestión avanzada como reservas múltiples, multas
automáticas ni integración con catálogos externos (puede ampliarse en versiones
posteriores).
2. Descripción general del Sistema:
El sistema contará con una interfaz web o de escritorio simple. Las funciones
principales estarán organizadas en módulos:
 Módulo Libros: crear, editar, eliminar (opcional) y listar libros.
 Módulo Usuarios: crear, editar y listar usuarios.
 Módulo Préstamos: registrar préstamos y devoluciones; verificar disponibilidad.
 Módulo Consultas/Reportes: lista de libros disponibles, lista de préstamos por
usuario, historial básico.
La persistencia de datos puede implementarse en una base de datos relacional
(SQLite para desarrollo/simulación, MySQL o PostgreSQL para producción).
 Actores y usuarios
 Administrador / Bibliotecario: gestiona libros, usuarios y préstamos.
 Usuario de biblioteca: persona que puede solicitar préstamos (no necesariamente
interactúa directamente con el sistema si la interfaz es interna).
 Sistema (automático): validaciones y control de reglas (por ejemplo: impedir
préstamo si libro no está disponible).
lOMoARcPSD|592 718 89
3. Requerimientos funcionales (RF).
El requerimiento funcional está numerado y redactado claramente en base a su utilidad.
RF1 - Registrar libro: El sistema debe permitir al bibliotecario registrar un nuevo libro con los campos:
título, autor, año, categoría y opcionalmente ISBN.
RF2 - Registrar usuario: El sistema debe permitir registrar un usuario con nombre, identificación (ID o
cédula) y contacto (correo o teléfono).
RF3 - Registrar préstamo: El sistema debe permitir registrar un préstamo indicando el libro, el usuario,
la fecha de préstamo y la fecha esperada de devolución. Al registrar el préstamo, el libro debe cambiar
su estado a "no disponible".
RF4 - Listar libros disponibles: El sistema debe mostrar una lista filtrable de libros que actualmente
estén disponibles para préstamo.
RF5 - Registrar devolución: El sistema debe permitir registrar la devolución de un libro, actualizando su
estado a "disponible" y almacenando la fecha de devolución.
RF6 - Prevención de préstamos duplicados: El sistema debe impedir que un libro ya prestado sea
prestado nuevamente hasta que sea devuelto.
Requerimientos no funcionales (RNF).
RNF1 - Usabilidad: La interfaz debe ser sencilla e intuitiva; cualquier usuario con conocimientos básicos
debe poder realizar operaciones esenciales sin manual extenso.
RNF2 - Rendimiento: Las operaciones CRUD (crear/leer/actualizar) deben responder en menos de 3
segundos en condiciones normales.
RNF3 - Persistencia e integridad: Los datos deben persistir en una base de datos; las transacciones
críticas (registro de préstamo/devolución) deben mantener la integridad ante fallos.
RNF4 - Seguridad básica: Acceso protegido por autenticación para el rol bibliotecario (usuario/clave).
Los datos personales deben tratarse con confidencialidad.
RNF5 - Escalabilidad básica: El diseño debe permitir agregar más campos o módulos en el futuro sin
reescritura total del sistema.
4. Criterios de aceptación
1. Un libro registrado mediante la interfaz aparece en la lista de libros con todos los campos
ingresados.
2. Al registrar un préstamo, el libro debe dejar de aparecer en la lista de disponibles y el préstamo
debe guardarse con usuario y fechas.
3. No se debe permitir registrar un préstamo para un libro que ya está prestado: el sistema
mostrará un mensaje de error claro.
4. Al registrar la devolución, el estado del libro debe actualizarse a disponible y el registro de
devolución debe guardarse con fecha.
5. Los criterios de tiempo de respuesta y usabilidad se validan mediante pruebas de usuario
sencillas (3 operaciones comunes ejecutadas en menos de 3 segundos en un entorno razonable)
