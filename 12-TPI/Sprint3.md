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

Dividir la funcionalidad implementada hasta el momento en dos aplicaciones diferentes, una que cumplirá la función de servidor y otra la de cliente. El servidor deberá ser capaz de aceptar conexiones entrantes de múltiples clientes, y enviará las canciones que se vayan solicitando a través de un socket a la aplicación cliente. Para implementar la concurrencia en el servidor, se pueden utilizar tanto la función select, como múltiples procesos. Además el servidor será quien tendrá la base de datos, con lo cual las operaciones de registro, login y logout se realizarán a través de él. Recordar que no se debe hacer streaming del archivo de audio, sino que debe recibirse primero en cliente y luego comenzar a reproducirse.

## Tarea 2.4 - Logs
Elegir algun módulo de software de la aplicación y generar una biblioteca a partir del mismo. Dicha
biblioteca puede ser tanto estática como dinámica y la misma debe ser utilizada para la posterior
compilación y/o ejecución de la aplicación.
