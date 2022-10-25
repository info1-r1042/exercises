# Trabajo Práctico Integrador - Infotify - Sprint 1 - Aplicación de Escritorio

```
Advertencia

El código fuente entregado por un grupo debe ser escrito en su totalidad por dicho grupo.
```

**Condiciones de entrega:**

| **¿Qué se entrega?**            | **¿Qué no se entrega?**                           |
| ----                            |   ----                                            |
| Archivos fuente/source (.c)     | Archivos objeto (.o)                              |
| Archivos encabezado/header (.h) | Archivos ejecutables (programa, app, a.out, etc.) |
| Bibliotecas específicas (.a)    |                                                   |
| Makefile                        |                                                   |
| Doxyfile                        |                                                   |

**Importante:** En esta primera entrega se evaluará principalmente la estructura del código y como se resuelven cada una de las partes solicitadas en diferentes módulos y diferentes funciones, que permitan abstraer la implementación de la lógica del programa (por ejemplo funciones tales como `registrar_usuario()`, `existe_usuario()`, `iniciar_sesion()`, etc.).

**Fecha de Entrega:** El código del presente sprint deberá estar subido al repositorio el Domingo 05 de Noviembre de 2022 a las 23:55hs.

## Tarea 1.1 - Estructura del Proyecto
Crear el proyecto en el repositorio y generar el primer commit. Adaptar el template para el grupo en particular, modiﬁcando donde sea necesario con la información del grupo.

## Tarea 1.2 - Manejo de Usuarios
Para la persistencia de la información de los usuarios (`usuario` y `contraseña`) se utilizará un archivo binario llamado `usuarios.db`.

Para el manejo de la información de los usuarios se utilizarán arreglos dinámicos (vectores) de estructuras. Por una cuestión de performance, toda la información de los usuarios se debe cargar en memoria en un arreglo dinámico desde el archivo binario al comenzar la ejecución del programa, y las operaciones sobre usuarios deberán realizarse sobre dicho arreglo. Tener en cuenta que se debe actualizar el archivo siempre que el arreglo sufra modiﬁcaciones, para mantener ambos siempre sincronizados.

Desarrollar un módulo de manejo de usuarios, el cual debe poseer funciones para poder crear y leer usuarios. Recordar el [Principio de Responsabilidad Única](https://es.wikipedia.org/wiki/Principio_de_responsabilidad_%C3%BAnica), es decir que las funciones deben cumplir una sola tarea.

Tener en cuenta que tanto el nombre de usuario como la contraseña son **strings** de hasta **25 caracteres** de largo.

## Tarea 1.3 - Menú
Desarrollar un módulo de menú principal que imprima un mensaje de bienvenida al usuario y despliegue un menú de selección. Las opciones deben ser **`"Iniciar sesión"`**, **`"Registrarse"`** y **`"Salir"`**.

Si el usuario selecciona la opción `Iniciar sesión`, se deberá solicitar al usuario que ingrese su nombre de usuario y luego su contraseña. Luego se deberá corroborar la existencia de dicho usuario en la base de datos, y si el mismo **existe** y la contraseña es **válida**, se imprimirá la leyenda *"¡Bienvenido [nombre de usuario]!"* y se mostrará el menú de usuario (ver **Tarea 1.4**). Si el usuario **no existe** o la contraseña es **inválida**, se deberá imprimir *"Error: Datos ingresados erróneos"*, y se volverá a mostrar el menú principal.

Si el usuario selecciona la opción `Registrarse`, se deberá solicitar al usuario que ingrese el nombre de usuario y la contraseña deseados. Se deberá veriﬁcar que dicho usuario **no exista** ya en la base de datos. Si se encuentra disponible, se agregará dicho usuario y contraseña a la base de datos, se imprimirá la leyenda *"Usuario registrado exitosamente"* y se mostrará el menú de usuario (ver **Tarea 1.4**). Si el usuario **ya existe** en el sistema, se deberá imprimir *"Error: Usuario ya registrado"*, y se volverá a mostrar el menú principal.

Si el usuario selecciona la opción `Salir`, se terminará la ejecución.

## Tarea 1.4 - Manejo de Canciones
Desarrollar un módulo de menú de usuario que se utilizará cuando el usuario ya ingresó al sistema (luego de un login o registro exitoso), y desplegará un menú de selección. Las opciones deben ser **`"Listar canciones"`**, **`"Filtrar canciones"`** y **`"Salir"`**.

Si el usuario selecciona la opción `Listar canciones`, el programa relevará todos las canciones presentes en la base de datos y le mostrará al usuario un listado enumerado de las mismas, por ejemplo:

```
No - Tema - Artista - Album - Genero - Año
1 - Comfortably Numb - Pink Floyd - The Wall - Rock progresivo - 1979
2 - Instant Crush - Daft Punk - Random Access Memories - Dance rock - 2013
3 - Profugos - Soda Stereo - Signos - New wave - 1986
4 - ...
```

Para la persistencia de la información de las canciones se utilizarán un archivo de texto en formato [CSV](https://es.wikipedia.org/wiki/Valores_separados_por_comas) llamado `media.csv`, de acuerdo al esquema siguiente:

```csv
Comfortably Numb,Pink Floyd,The Wall,Rock progresivo,1979
Instant Crush,Daft Punk,Random Access Memories,Dance rock,2013
Profugos,Soda Stereo,Signos,New wave,1986
...
```

Si el usuario selecciona la opción `Filtrar canciones`, el comportamiento será similar a `Listar canciones` pero se le deberá preguntar previamente al usuario si se desea filtrar el listado por `Artista` o `Género` y el valor del filtro a aplicar.

Si el usuario selecciona la opción `Salir`, se terminará la ejecución.

## [Opcional] Tarea 1.5 - Reproducción local
Se debe incorporar una nueva opción al menú de usuario, la cual se llamará **`"Escuchar canción"`**.

Si el usuario selecciona la opción `Escuchar canción`, se le solicitará que elija una canción (mediante su número de orden), luego de lo cual la misma deberá reproducirse. Al terminar de reproducirse la canción, deberá volver a aparecer el menú de usuario.

**Nota:** Para los archivos de audio se recomienda utilizar el formato `.mp3` y para su reproducción, la biblioteca [libVLC](https://www.videolan.org/vlc/libvlc.html).
