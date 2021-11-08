# Trabajo Práctico Integrador - Sprint 3 - Aplicación Web

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

**Fecha de Entrega:** El código del presente sprint deberá estar subido al repositorio el Domingo 28 de Noviembre de 2021 a las 23:55hs.

<br>

## Tarea 3.1 - Arquitectura Cliente/Servidor
Dividir la funcionalidad implementada hasta el momento en dos aplicaciones diferentes, una que cumplirá la función de servidor y otra la de cliente. El servidor deberá ser capaz de aceptar conexiones entrantes de múltiples clientes en forma simultánea, y enviará los archivos de media que se vayan solicitando a través de un socket a la aplicación cliente. Además el servidor será quien tendrá acceso a la base de datos, con lo cual las operaciones de registro, inicio de sesión y cierra de sesión de usuarios se realizarán a través de él.

Tanto la aplicación servidor como la aplicación cliente deberán recibir el archivo de configuración en formato INI como argumento por línea de comandos.

El archivo de configuración del servidor deberá poseer el siguiente esquema:

```ini
[Usuarios]
PathBaseDeDatos: /home/johnconnor/base_de_datos.csv

[Media]
PathDirectorio: /home/johnconnor/media

[Logging]
Nivel: 2
Sumidero: 0

[Networking]
Puerto: 12345
```

El archivo de configuración del cliente deberá poseer el siguiente esquema:

```ini
[Media]
PathDirectorioTemporal: /tmp/media

[Logging]
Nivel: 2
Sumidero: 0

[Networking]
IpServidor: 127.0.0.1
PuertoServidor: 12345
```

## Tarea 3.2 - Presentación
Realizar una presentación sencilla (de no más de 15 diapositivas en total) la cual será utilizada durante la exposición y demostración del trabajo realizado. La misma debe incluir:
- Portada
- Información de los autores
- Temario
- Introducción y descripción de la aplicación
- Diagrama de arquitectura de software (módulos y funciones)
- Dificultades encontradas y cómo se resolvieron (lecciones aprendidas)
- Resultados y conclusiones
- Posibles mejoras futuras
