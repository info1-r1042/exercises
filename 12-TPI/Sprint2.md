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

Si el usuario selecciona la opción `Escuchar canción`, el programa relevará de un directorio llamado `media` todos los archivos de audio presentes y le mostrará al usuario un listado enumerado de los mismos (incluyendo su metadata), con la leyenda `Ingrese el número de canción deseada`, por ejemplo:

```
No - Tema - Artista - Album - Genero - Año
1 - Comfortably Numb - Pink Floyd - The Wall - Rock progresivo - 1979
2 - ...
```

Al elegir una canción (mediante su número de orden), la misma deberá reproducirse.

Al terminar de reproducirse la canción, deberá volver a aparecer el menú de usuario.

Los archivos (tanto de audio como de metadata) deberán estar organizados de la siguiente manera:

```
media
├── pink_floyd_comfortably_numb.mp3
├── pink_floyd_comfortably_numb_metadata.json
├── daft_punk_instant_crush.imf
├── daft_punk_instant_crush_metadata.json
:
├── soda_stereo_profugos.raw
└── soda_stereo_profugos_metadata.json
```

Para la metadata se utilizarán archivos de texto en formato [JSON](https://es.wikipedia.org/wiki/JSON), de acuerdo al esquema siguiente:

```json
{"metadata": {"nombre": "Comfortably Numb", "artista": "Pink Floyd", "album": "The Wall", "genero": "Rock progresivo", "anio": 1979}}
```

**Nota:** Para la reproducción de los archivos de audio se podrán usar tanto los ejemplos vistos en clase (para los formatos `.raw` y `.imf`) como la biblioteca [libVLC](https://www.videolan.org/vlc/libvlc.html) (para `.mp3` y otros formatos).

**Ayuda:** Para relevar todos los archivos presentes en un directorio se recomienda consultar la documentación en las páginas de man de las funciones `opendir` y `readdir`.

### Tarea 2.1b (sólo para quienes desarrollan Infotitos)
Se debe incorporar una nueva opción al menú de usuario, la cual se llamará **`"Ver imagen"`**.

Si el usuario selecciona la opción `Ver imagen`, el programa relevará de un directorio llamado `media` todos los archivos de imagen presentes y le mostrará al usuario un listado enumerado de los mismos (incluyendo su metadata), con la leyenda `Ingrese el número de imagen deseada`, por ejemplo:

```
No - Marca - Modelo - Año - Cilindrada - Color
1 - Ferrari - Testarossa - 1996 - 4.9 - Rojo
2 - ...
```

Al elegir una imagen (mediante su número de orden), la misma deberá mostrarse en pantalla.

Al oprimirse cualquier tecla, deberá cerrarse la imagen y deberá volver a aparecer el menú de usuario.

Los archivos (tanto de imagen como de metadata) deberán estar organizados de la siguiente manera:

```
media
├── ferrari_testarossa.png
├── ferrari_testarossa_metadata.json
├── bugatti_veyron.jpg
├── bugatti_veyron_metadata.json
:
├── chevrolet_camaro.bmp
└── chevrolet_camaro_metadata.json
```

Para la metadata se utilizarán archivos de texto en formato [JSON](https://es.wikipedia.org/wiki/JSON), de acuerdo al esquema siguiente (que podrá variar de acuerdo a la aplicación):

```json
{"metadata": {"marca": "Ferrari", "modelo": "Testarossa", "anio": 1996, "cilindrada": 4.9, "color": "Rojo"}}
```

**Nota:** Para la apertura de los archivos de imagen se podrá usar la biblioteca [OpenCV](https://opencv.org/).

**Ayuda:** Para relevar todos los archivos presentes en un directorio se recomienda consultar la documentación en las páginas de man de las funciones `opendir` y `readdir`.

## Tarea 2.2 - Logs
En informática, se usa el término [registro, log o historial de log](https://es.wikipedia.org/wiki/Log_(inform%C3%A1tica)) para referirse a la grabación secuencial en un archivo o en una base de datos de todos los acontecimientos (eventos o acciones) que afectan a un proceso particular (aplicación, actividad de una red informática, etc.). De esta forma constituye una evidencia del comportamiento del sistema.

Desarrollar un módulo de logging para poder depurar o "debuggear" el programa más fácilmente. La lı́nea de debug debe contener la fecha, el nivel de log, el nombre del archivo, el número de lı́nea y el mensaje. También se deberán colocar mensajes de log a lo largo del programa para facilitar su debug. Por ejemplo:

```
23-10-2021 08:03:32 DEBUG src/main.c:63: Inicializando...
23-10-2021 08:03:32 INFO  src/config/config.c:31: Configuracion cargada con exito
23-10-2021 08:03:40 INFO  src/menu_usuario.c:26: Inicio de sesion de usuario: johnconnor
23-10-2021 08:05:06 WARN  src/media.c:19: El directorio media se encuentra vacio
```

El módulo de logging deberá poseer las siguientes configuraciones:
- Se podrá configurar al flujo de salida de error estándar (`stderr`) o a un archivo en el directorio temporal del sistema (`/tmp/infotify.log` o `/tmp/infotitos.log`) como el sumidero destino de los logs generados.
- Se podrá configurar el nivel mínimo de logs a escribir. Esto quiere decir que si por ejemplo se elige `LOG_WARN`, solo se escribirán los logs con nivel `LOG_WARN`, `LOG_ERROR` o `LOG_FATAL`.
- Se podrá habilitado y deshabilitar al módulo para que no se escriban logs.

Se deberán utilizar los siguientes tipos, macros y prototipos:

```c

/*!
 * @typedef Sumidero de logs.
 */
typedef enum LogSumidero
{ 
    LOG_ARCHIVO,
    LOG_STDERR
} LogSumidero;

/*!
 * @typedef Nivel de prioridad de logs.
 */
typedef enum LogNivel
{ 
    LOG_DEBUG,
    LOG_INFO,
    LOG_WARN,
    LOG_ERROR,
    LOG_FATAL
} LogNivel;

/*!
 * @typedef Logger.
 */
typedef struct Logger
{
    LogNivel nivel;
    LogSumidero sumidero;
    Bool habilitado;
} Logger;

/*!
 * @brief Macro para simplificar el uso de logger_log (evita que el usuario
 *   tenga que colocar el archivo y la linea donde se generó el log).
 */
#define LOGGER_LOG(...) logger_log_interno(__FILE__, __LINE__, __VA_ARGS__)

/*!
 * @brief Crea un logger.
 *
 * @details Crear el logger consiste en reservar memoria para el mismo y crear
 *   el archivo de log (en /tmp).
 *
 * @param[in] nivel Nivel de prioridad mínimo.
 * @param[in] sumidero Sumidero destino.
 * @return	  Logger creado.
 */
Logger* logger_crear(LogNivel nivel, LogSumidero sumidero);

/*!
 * @brief Habilita y deshabilita al logger.
 *
 * @param[in/out] logger Logger.
 * @param[in]     habilitado Variable booleana que define el estado deseado del logger.
 */
void logger_habilitar(Logger* logger, Bool habilitado);

/*!
 * @brief Escribe una entrada de log.
 *
 * @param[in] path_archivo Path del archivo donde se generó el log.
 * @param[in] linea Número de línea donde se generó el log.
 * @param[in] logger Logger.
 * @param[in] nivel Nivel de prioridad del log.
 * @param[in] mensaje Mensaje del log.
 */
void logger_log_interno(const char* path_archivo, int linea, const Logger* logger, LogNivel nivel, const char* mensaje);

/*!
 * @brief Destruye el logger.
 *
 * @details Destruir el logger consiste en liberar la memoria reservada para
 *   el mismo y cerrar el archivo de log (en /tmp).
 *
 * @param[in/out] logger Logger.
 */
void logger_destruir(Logger* logger);
```

## Tarea 2.3 - Configuración
Con el objetivo de desarrollar una aplicación más flexible, en lugar de tener algunos valores directamente escritos en el código fuente (["hard-codeados"](https://es.wikipedia.org/wiki/Hard_code)), se utilizará un archivo de configuración. El mismo deberá ser un archivo de texto en formato [INI](https://es.wikipedia.org/wiki/INI_(extensi%C3%B3n_de_archivo)).

Desarrollar un módulo de configuración para cargar dicha configuración al comienzo de la aplicación. El path del archivo de configuración se deberá pasar a la aplicación como argumento en línea de comandos, por ejemplo:

```bash
./app /home/johnconnor/config.ini
```

El archivo de configuración deberá poseer el siguiente esquema:

```ini
[Usuarios]
PathBaseDeDatos: /home/johnconnor/base_de_datos.csv

[Media]
PathDirectorio: /home/johnconnor/media

[Logging]
Nivel: 2
Sumidero: 0
```

Y se deberá utilizar de la siguiente manera:

```c
// ...
Config config;
config_cargar("path_archivo_de_config", &config);
// ...
```
