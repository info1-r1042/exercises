# Trabajo Práctico Integrador - Sprint 2 - Aplicación de Escritorio

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
Se debe incorporar una nueva opción al menú de usuario, la cual se llamará **`"Ver imagen"`**.

Si el usuario selecciona la opción `Ver imagen`, el programa relevará de un directorio llamado `media` todos los archivos de imagen presentes y le mostrará al usuario un listado enumerado de los mismos (incluyendo su metadata), con la leyenda `Ingrese el número de imagen deseada`. Al elegir una imagen, la misma deberá mostrarse en pantalla.

Al oprimirse cualquier tecla, deberá cerrarse la imagen y deberá volver a aparecer el menú de usuario.

Los archivos (tanto de imagen como de metadata) deberán estar organizados de la siguiente manera:

```
media
├── ferrari_testarossa.jpg
├── ferrari_testarossa_metadata.json
├── bugatti_veyron.jpg
├── bugatti_veyron_metadata.json
:
├── chevrolet_camaro.jpg
└── chevrolet_camaro_metadata.json
```

Para la metadata se utilizarán archivos de texto en formato [JSON](https://es.wikipedia.org/wiki/JSON), de acuerdo al esquema siguiente:

```json
{"metadata": {"marca": "Ferrari", "modelo": "Testarossa", "anio": 1996, "cilindrada": 4.9, "color": "Rojo"}}
```

**Nota:** Para relevar todos los archivos presentes en un directorio se recomienda consultar la documentación en las páginas de man de las funciones `opendir` y `readdir`.

## Tarea 2.2 - Logs
Desarrollar un módulo de logging para poder depurar o "debuggear" el programa más fácilmente. Se deberán colocar
mensajes de log a lo largo del programa para facilitar su debug.
Se debe agregar un ﬂag de compilación condicional para decidir si incluir o no los logs en la compilación
del programa (https://es.cppreference.com/w/cpp/preprocessor/conditional). Debe loggear a un archivo de log en /tmp.

Se desea disponer de una función que permita depurar o “debuggear” un programa, volcando la
información sobre un archivo de texto histórico (log file), de acuerdo al siguiente prototipo:
void log msg(NivelLog nivel, const char* archivo, int linea, const char* mensaje)
Donde:
nivel: Tipo enumerativo que representa el nivel de debug al que pertenece el mensaje (DEBUG,
INFO, WARN, ERROR, FATAL).
archivo: Archivo donde se genera el log (siempre vale
linea: Linea donde se genera el log (siempre vale FILE ). LINE ).
mensaje: Mensaje de log.
Ayuda
La lı́nea de debug debe contener el timestamp (en formato Unix Epoch Timestamp), el nivel
de debug, el nombre del archivo, el número de lı́nea y el mensaje. Se debe abrir y cerrar el
archivo de log en la función. Por ejemplo, si se invoca la función de la siguiente manera:


```c
typedef enum LogSumidero
{ 
    LOG_STDERR,
    LOG_FILE
} LogSumidero;

typedef enum LogNivel
{ 
    LOG_DEBUG,
    LOG_INFO,
    LOG_WARN,
    LOG_ERROR,
    LOG_FATAL
} LogNivel;

typedef struct Logger
{
    LogNivel level;
    LogSumidero sink;
    FILE* archivo;
    Bool silenciado;
} Logger;

#define LOGGER_LOG(...) logger_log_interno(__FILE__, __LINE__, __VA_ARGS__)

Logger* logger_crear();
void logger_set_nivel(Logger* logger, LogNivel nivel);
void logger_set_archivo(Logger* logger, FILE* archivo);
void logger_set_sumidero(Logger* logger, LogSumidero sumidero);
void logger_silenciar(Logger* logger, Bool silenciado);
void logger_log_interno(const char* path_archivo, int linea, Logger* logger, LogNivel nivel, const char* mensaje);
void logger_destruir(Logger* logger);
```

LOGGER_LOG(LOG_INFO, “Registrando usuario...”);
Se deberı́a obtener la siguiente lı́nea de log:
“1565474700 INFO main.c:35: Registrando usuario...”

## Tarea 2.3 - Archivo de Configuración
Path del archivo de configuración se pasa como argumento del main. Formato INI.

## Tarea 2.4 - Logs
Elegir algun módulo de software de la aplicación y generar una biblioteca a partir del mismo. Dicha
biblioteca puede ser tanto estática como dinámica y la misma debe ser utilizada para la posterior
compilación y/o ejecución de la aplicación.
