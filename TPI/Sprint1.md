# Trabajo Práctico Integrador - Sprint 1 - Menús y Gestión de Usuarios

```
Advertencia

El código fuente entregado por un grupo debe ser escrito en su totalidad por dicho grupo.
```

***<u>Condiciones de entrega:</u>***

| <b>¿Qué se entrega?</b>         | <b>¿Qué no se entrega?</b>                        |
| ----                            |   ----                                            |
| Archivos fuente/source (.c)     | Archivos objeto (.o)                              |
| Archivos encabezado/header (.h) | Archivos ejecutables (programa, app, a.out, etc.) |
| Makefile                        |   |
| Doxyfile                        |   |

**Importante:** En esta primera entrega se evaluará principalmente la estructura del código y como se resuelven cada una de las partes solicitadas en diferentes módulos y diferentes funciones, que permitan abstraer la implementación de la lógica del programa (por ejemplo funciones tales como `registrar_usuario()`, `leer_linea()`, `existe_usuario()`, `encriptar_contrasenia()`, etc.).

**Fecha de Entrega:** El código del presente sprint deberá estar subido al repositorio el Domingo 31 de Octubre de 2021 a las 23:55hs.

<br>

## Tarea 1.1 - Estructura del Proyecto
Crear el proyecto en el repositorio y generar el primer commit. Adaptar el template para el grupo en particular, modiﬁcando donde sea necesario con la información del grupo.

## Tarea 1.2 - Base de Datos de Usuarios
Para la persistencia de la información de los usuarios (`usuario` y `contraseña`) se utilizarán archivos de texto en formato [CSV](https://es.wikipedia.org/wiki/Valores_separados_por_comas).

Desarrollar un módulo de manejo de archivos de texto, el cual debe poseer funciones para poder leer y escribir el archivo línea a línea. Tener en cuenta que la función de leer deberá realizar la reserva de memoria necesaria para almacenar la línea leída.

## Tarea 1.3 - Manejo de Usuarios
Para el manejo de la información de los usuarios (llamado [ABM](https://es.wikipedia.org/wiki/CRUD) por las siglas de `"Alta, Baja y Modificación"` o [CRUD](https://developer.mozilla.org/es/docs/Glossary/CRUD) por las siglas en inglés de `"Crear, Leer, Actualizar y Eliminar"`) se utilizarán arreglos dinámicos (vectores) de estructuras. Por una cuestión de performance, toda la información de los usuarios se debe cargar en un arreglo dinámico desde el archivo CSV al comenzar la ejecución, y todas las operaciones anteriormente mencionadas deberán realizarse sobre dicho arreglo. Tener en cuenta que se debe actualizar el archivo siempre que el arreglo sufra modiﬁcaciones, para mantener ambos siempre sincronizados.

Desarrollar un módulo de manejo de arreglos dinámicos (vectores) de estructuras, el cual debe poseer funciones para poder crear, leer, actualizar y eliminar elementos del mismo. Se recomienda implementar funciones lo más abstraídas del contenido de la estructura posibles. Recordar el [Principio de Responsabilidad Única](https://es.wikipedia.org/wiki/Principio_de_responsabilidad_%C3%BAnica), es decir que las funciones deben cumplir una sola tarea.

Tener en cuenta que tanto el nombre de usuario como la contraseña son **strings** de hasta **25 caracteres** de largo (aunque la contraseña se almacenará hasheada, ver **Tarea 1.7**).

## Tarea 1.4 - Menú Principal
Desarrollar un módulo de menú principal que imprima un mensaje de bienvenida al usuario y despliegue un menú de selección. Las opciones deben ser **`"Iniciar sesión"`**, **`"Registrarse"`** y **`"Salir"`**.

Si el usuario selecciona la opción `Iniciar sesión`, se deberá solicitar al usuario que ingrese su nombre de usuario y luego su contraseña. Luego se deberá corroborar la existencia de dicho usuario en la base de datos, y si el mismo **existe** y la contraseña es **válida**, se imprimirá la leyenda *"¡Bienvenido [nombre de usuario]!"* y se mostrará el menú de usuario (ver **Tarea 1.5**). Si el usuario **no existe** o la contraseña es **inválida**, se deberá imprimir *"Error: Datos ingresados erróneos"*, y se volverá a mostrar el menú principal.

Si el usuario selecciona la opción `Registrarse`, se deberá solicitar al usuario que ingrese el nombre de usuario y la contraseña deseados. Se deberá veriﬁcar que dicho usuario **no exista** ya en la base de datos. Si se encuentra disponible, se agregará dicho usuario y contraseña a la base de datos, se imprimirá la leyenda *"Usuario registrado exitosamente"* y se mostrará el menú de usuario (ver **Tarea 1.5**). Si el usuario **ya existe** en el sistema, se deberá imprimir *"Error: Usuario ya registrado"*, y se volverá a mostrar el menú principal.

Si el usuario selecciona la opción `Salir`, se terminará la ejecución.

Tener en cuenta que la contraseña **debe ser** [case-sensitive](https://es.wikipedia.org/wiki/Sensible_a_may%C3%BAsculas_y_min%C3%BAsculas) mientras que el usuario **no debe serlo**.

## Tarea 1.5 - Menú de Usuario
Desarrollar un módulo de menú de usuario que se utilizará cuando el usuario ya ingresó al sistema (luego de un login o registro exitoso), y desplegará un menú de selección. Las opciones deben ser **`"Cambiar contraseña"`**, **`"Eliminar cuenta"`** y **`"Cerrar sesión"`**.

Si el usuario selecciona la opción `Cambiar contraseña`, se deberá solicitar al usuario que ingrese la contraseña actual y la nueva contraseña. Si la contraseña actual es **válida**, se reemplazará la contraseña actual por la nueva, se imprimirá la leyenda *"Contraseña modificada exitosamente"* y se volverá al menú de usuario. Si la contraseña actual es **inválida**, se imprimirá la leyenda *"Error: Contraseña actual inválida"* y se volverá al menú de usuario.

Si el usuario selecciona la opción `Eliminar cuenta`, se eliminará dicho usuario de la base de datos, se imprimirá la leyenda *"Usuario eliminado exitosamente"* y se volverá al menú principal.

Si el usuario selecciona la opción `Cerrar sesión`, se imprimirá el mensaje de despedida *"¡Chau [nombre de usuario]!"* y se volverá al menú principal.

## Tarea 1.6 - Último Acceso
Se debe incorporar un tercer elemento a la información de cada cliente, el cual será la hora del último ingreso en formato [Unix Epoch Timestamp](https://es.wikipedia.org/wiki/Tiempo_Unix). A su vez, los usuarios en el arreglo (y por lo tanto también en el archivo CSV) deberán mantenerse ordenados en función del último ingreso (más recientes primero). Esto permite obtener tiempos de búsqueda menores para los usuarios más frecuentes de la aplicación.

## Tarea 1.7 - Encriptación de Contraseñas
Es una muy mala idea almacenar contraseñas en texto plano (tal cual son) en una base de datos debido a que en caso de que la misma se vea comprometida, todas las contraseñas quedarán expuestas. Una forma de resolver este problema es guardando una versión encriptada de la contraseña aplicándole una [función hash criptográfica](https://es.wikipedia.org/wiki/Funci%C3%B3n_hash_criptogr%C3%A1fica) a la misma en lugar de guardarla en el formato original. La propiedad principal de las funciones hash es que es muy fácil computar el hash para un determinado valor de entrada pero es difícil computar dicho valor de entrada a partir del hash.

Desarrollar un módulo de encriptación de contraseñas utilizando la [función hash sdbm](http://www.cs.yorku.ca/~oz/hash.html) lo cual permitirá que la contraseña se almacene en la base de datos de forma ofuscada. El hash deberá ser almacenado en la base de datos en formato **hexadecimal**.

**Ejemplo:**
```csv
johnconnor,576c941cdcedb2c6,1632016627
```
