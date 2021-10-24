# Trabajo Práctico Integrador - Sprint 2 - Ejecución Local

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

**Fecha de Entrega:** El código del presente sprint deberá estar subido al repositorio el Domingo 14 de Noviembre de 2021 a las 23:55hs.

<br>

## Tarea 2.1 - Reproducción local
### Tarea 2.1a (sólo para quienes desarrollan Infotify)
Se debe incorporar una nueva opción al menú de usuario, la cual se llamará **`"Escuchar canción"`**.

Si el usuario selecciona la opción `Escuchar canción`, el programa relevará de un directorio llamado `media` todos los archivos de audio presentes y le mostrará al usuario un listado enumerado de los mismos (incluyendo su metadata), con la leyenda `Ingrese el número de canción deseada`. Al elegir una canción, la misma deberá reproducirse.

Al terminar de reproducirse la canción, deberá volver a aparecer el menú de usuario.

Los archivos (tanto de audio como de metadata) deberán estar organizados de la siguiente manera:

```
media
├── pink_floyd_comfortably_numb.mp3
├── pink_floyd_comfortably_numb_metadata.json
├── daft_punk_instant_crush.mp3
├── daft_punk_instant_crush_metadata.json
:
├── soda_stereo_profugos.mp3
└── soda_stereo_profugos_metadata.json
```

Para la metadata se utilizarán archivos de texto en formato [JSON](https://es.wikipedia.org/wiki/JSON), de acuerdo al esquema siguiente:

```json
{"metadata": {"nombre": "Comfortably Numb", "artista": "Pink Floyd", "album": "The Wall", "genero": "Rock progresivo", "anio": 1979}}
```

**Nota:** Para relevar todos los archivos presentes en un directorio se recomienda consultar la documentación en las páginas de man de las funciones `opendir` y `readdir`.

### Tarea 2.1b (sólo para quienes desarrollan Infotitos)
Al menú que el usuario recibe una vez que ingresó al sistema, agregar una opción llamada “ver un
video”. Una vez elegida dicha opción, el programa debe relevar de un directorio llamado “media”,
todos los archivos de video presentes y entregarle al usuario un listado enumerado de los mismos,
con la leyenda “elija un video”. Al elegir un video, el mismo deberá reproducirse y al terminar debe
aparecer otro menú con las opciones “ver nuevamente”, “ver otro video” y “salir”.
Ayuda


## Tarea 2.2
Incorporar un módulo de log para poder depurar el programa más fácilmente. Se deberán colocar
mensajes de log a lo largo del programa para facilitar su debug.
Se debe agregar un ﬂag de compilación condicional para decidir si incluir o no los logs en la compilación
del programa (https://es.cppreference.com/w/cpp/preprocessor/conditional).

Path de la base de datos se pasa como argumento del main.

Elegir algun módulo de software de la aplicación y generar una biblioteca a partir del mismo. Dicha
biblioteca puede ser tanto estática como dinámica y la misma debe ser utilizada para la posterior
compilación y/o ejecución de la aplicación.
