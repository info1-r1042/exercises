# Trabajo Práctico Integrador - Infotify - Sprint 2 - Aplicación Web

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

**Fecha de Entrega:** El código del presente sprint deberá estar subido al repositorio el Viernes 18 de Noviembre de 2022 a las 14:00hs.

## Tarea 2.1 - Arquitectura Cliente/Servidor
Dividir la funcionalidad implementada hasta el momento en dos aplicaciones diferentes, una que cumplirá la función de servidor y otra la de cliente. El servidor deberá ser capaz de aceptar una conexión entrante de un único cliente en forma simultánea, y enviará los archivos de media que se vayan solicitando a través de un socket a la aplicación cliente. Además el servidor será quien tendrá acceso a la base de datos de usuarios, con lo cual las operaciones de registro, inicio de sesión y cierra de sesión de usuarios se realizarán a través de él.

La aplicación servidor deberá recibir el número de puerto como argumento por línea de comandos. La aplicación cliente deberá recibir el número de IP y puerto del servidor como argumento por línea de comandos.

Tener en cuenta que la lógica de la aplicación pertenecerá a la aplicación cliente (menús, ingreso de datos por terminal, etc.), mientras que la aplicación servidor será quien tendrá acceso a los archivos de media y a la base de datos de usuarios y recibirá solicitudes de la aplicación cliente para operar sobre los mismos.

Para evitar problemas, se recomienda que el protocolo de la comunicación con la aplicación servidor sea [stateless](https://es.wikipedia.org/wiki/Protocolo_sin_estado) (sin estado), es decir, que el servidor recibirá una solicitud y responderá con una respuesta, por ejemplo:

**Ejemplo registro de usuario:**
```c
// La aplicación cliente envía la solicitud de registro de usuario al servidor.
send(/* ... */, "/registrar_usuario {johnconnor,576c941cdcedb2c6}", /* ... */);

// En caso de exito, el servidor responde con OK o código de exito.
send(/* ... */, "/registrar_usuario {OK}", /* ... */);

// En caso de error, el servidor responde con el mensaje o código de error.
send(/* ... */, "/registrar_usuario {ERROR_USUARIO_YA_REGISTRADO}", /* ... */);
```

**Ejemplo inicio de sesión de usuario:**
```c
// La aplicación cliente envía la solicitud de inicio de sesión de usuario al servidor.
send(/* ... */, "/iniciar_sesion {johnconnor,576c941cdcedb2c6}", /* ... */);

// En caso de exito, el servidor responde con OK o código de exito.
send(/* ... */, "/iniciar_sesion {OK}", /* ... */);

// En caso de error, el servidor responde con el mensaje o código de error.
send(/* ... */, "/iniciar_sesion {ERROR_DATOS_ERRONEOS}", /* ... */);
```

**Ejemplo listado de media:**
```c
// La aplicación cliente envía la solicitud de listado de media al servidor.
send(/* ... */, "/listado_media {}", /* ... */);

// En caso de exito, el servidor responde con el listado.
send(/* ... */, "/listado_media {1 - Comfortably Numb - Pink Floyd - The Wall - Rock progresivo - 1979\n2 - ...}", /* ... */);

// En caso de error, el servidor responde con el mensaje o código de error.
send(/* ... */, "/listado_media {ERROR_ARCHIVO_NO_ENCONTRADO}", /* ... */);
```

Lo importante a tener en cuenta en una comunicación mediante un protocolo sin estado, es que el servidor no almacenará el estado de la aplicación en ningún momento, sino que simplemente responderá a cada mensaje de solicitud con un mensaje de respuesta. De esta manera será mucho más sencillo evitar problemas de sincronización o bloqueos entre las aplicaciones cliente y servidor.

Utilizar el siguiente esquema de archivos para el repositorio:

```
repositorio
|-- cliente
|    |-- src
|    +-- Makefile
|-- servidor
|    |-- src
|    +-- Makefile
|-- README.md
+-- .gitignore
```

## Tarea 2.2 - Presentación
Realizar una presentación sencilla (de no más de 20 diapositivas en total) la cual será utilizada durante la exposición y demostración del trabajo realizado. La misma debe incluir:
- Portada
- Información de los autores
- Temario
- Introducción y descripción de la aplicación
- Diagrama de arquitectura de software (módulos y funciones)
- Dificultades encontradas y cómo se resolvieron (lecciones aprendidas)
- Resultados y conclusiones
- Posibles mejoras futuras

La exposición deberá tener una duración de aproximadamente **15 minutos** y se deberá hacer también una demostración en vivo del funcionamiento de la aplicación.
