# Sistema de Gestión de Biblioteca Descripción breve:
# Sistema de Gestión de Biblioteca
# 1. Propósito y Alcance
Propósito
El propósito del sistema es ofrecer una herramienta sencilla para la gestión de una biblioteca pequeña (por ejemplo, escolar o comunitaria). El sistema permitirá registrar libros y usuarios, administrar préstamos y devoluciones, y consultar el estado actual de los ejemplares.
Alcance
El sistema incluye:
•	Registro y edición de libros (título, autor, editorial, año, categoría, ISBN opcional).
•	Registro y edición de usuarios (nombre, identificación y contacto).
•	Registro de préstamos y devoluciones, incluyendo fecha de préstamo y fecha esperada de devolución.
•	Consulta de disponibilidad de libros y visualización de libros en préstamo.
Restricciones
Quedan fuera del alcance:
•	Reservas múltiples.
•	Multas automáticas por retrasos.
•	Integración con catálogos externos.
Estas funciones podrían considerarse para versiones futuras del sistema.
# 2. Descripción General del Sistema
El sistema ofrecerá una interfaz web o de escritorio simple, organizada en módulos funcionales para facilitar la gestión de la biblioteca.
Módulos del Sistema
•	Módulo Libros: Crear, editar, eliminar (opcional) y listar libros.
•	Módulo Usuarios: Crear, editar y listar usuarios.
•	Módulo Préstamos: Registrar préstamos y devoluciones, verificando la disponibilidad de los ejemplares.
•	Módulo Consultas/Reportes: Mostrar libros disponibles, préstamos por usuario e historial básico.
Persistencia de Datos
Los datos serán almacenados en una base de datos relacional:
•	SQLite (ideal para desarrollo o pruebas).
•	MySQL o PostgreSQL (para producción).
Actores del Sistema
•	Administrador / Bibliotecario: Gestiona libros, usuarios y préstamos.
•	Usuario de Biblioteca: Persona que solicita préstamos (puede no interactuar directamente con el sistema si el uso es interno).
•	Sistema: Encargado de validaciones automáticas (por ejemplo, impedir préstamos duplicados).

# 3. Requerimientos Funcionales (RF)
•	RF1 – Registrar libro: Permitir registrar un libro con título, autor, año, categoría e ISBN opcional.
•	RF2 – Registrar usuario: Permitir registrar un usuario con nombre, identificación y contacto.
•	RF3 – Registrar préstamo: Permitir registrar un préstamo indicando el libro, el usuario, la fecha de préstamo y la fecha esperada de devolución. El libro debe pasar a estado no disponible.
•	RF4 – Listar libros disponibles: Mostrar una lista filtrable de los libros disponibles para préstamo.
•	RF5 – Registrar devolución: Permitir registrar la devolución de un libro, actualizando su estado a disponible y guardando la fecha de devolución.
•	RF6 – Evitar préstamos duplicados: Impedir que un libro ya prestado sea prestado nuevamente antes de ser devuelto.
# Requerimientos No Funcionales (RNF)
•	RNF1 – Usabilidad: La interfaz debe ser intuitiva y fácil de usar sin necesidad de un manual extenso.
•	RNF2 – Rendimiento: Las operaciones CRUD deben ejecutarse en menos de 3 segundos en condiciones normales.
•	RNF3 – Persistencia e integridad: Todos los datos deben persistir en la base y las transacciones críticas deben mantener coherencia incluso ante fallas.
•	RNF4 – Seguridad básica: Acceso protegido mediante autenticación para el bibliotecario; los datos personales deberán manejarse de manera confidencial.
•	RNF5 – Escalabilidad básica: El sistema debe permitir agregar nuevos campos o módulos en el futuro sin reescribir todo el software_
# 4. Criterios de Aceptación
1.	Un libro registrado aparece correctamente en la lista de libros con todos los campos ingresados.
2.	Al registrar un préstamo, el libro deja de aparecer como disponible y se registra el préstamo con usuario y fechas.
3.	No debe permitirse registrar un préstamo de un libro ya prestado; el sistema debe mostrar un mensaje de error claro.
4.	Al registrar una devolución, el estado del libro vuelve a disponible y se almacena la fecha de devolución.
5.	La interfaz debe permitir realizar tres operaciones comunes (por ejemplo: registrar usuario, registrar libro, registrar préstamo) cada una en menos de 3 segundos.
# Reflexión sobre el Control de Versiones 
El uso de control de versiones es fundamental para el desarrollo del Sistema de Gestión de Biblioteca, ya que permite mantener un registro claro y ordenado de cada cambio realizado a lo largo del proyecto. Desde los primeros requerimientos hasta la implementación de módulos como Libros, Usuarios o Préstamos, GitHub asegura que todas las modificaciones queden documentadas y puedan revisarse cuando sea necesario.
Gracias a los commits, es posible identificar qué se cambió, cuándo se hizo y por qué, lo cual resulta especialmente útil en funciones críticas como el registro de préstamos, la actualización de estados de disponibilidad o la gestión de integridad en la base de datos. Si ocurre un error, GitHub permite volver a una versión anterior sin perder información ni afectar otros componentes del sistema.
Además, almacenar el proyecto en GitHub ofrece beneficios adicionales:
•	Un historial completo y organizado de versiones.
•	Comparación clara entre cambios, facilitando la detección de errores.
•	Trabajo colaborativo si varios desarrolladores participan en la mejora del sistema.
•	Un espacio seguro y accesible desde cualquier dispositivo.
En conjunto, GitHub no solo respalda la estabilidad del proyecto, sino que también facilita su mantenimiento y evolución. Gracias a esta herramienta, el Sistema de Gestión de Biblioteca puede crecer de manera ordenada, transparente y segura, asegurando que los nuevos módulos o mejoras futuras se integren sin afectar la funcionalidad existente.


