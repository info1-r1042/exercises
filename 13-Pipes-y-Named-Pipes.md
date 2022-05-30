# Guía de Ejercicios 13 - Pipes y Named Pipes

```
Advertencia

La resolución conjunta o grupal de los ejercicios aquí presentes no está permitida, excepto en la medida en que puedas pedir ayuda a tus compañeros de clase y a otras personas, y siempre que esa ayuda no se reduzca a que otro haga el trabajo por vos.

El código fuente entregado por un estudiante debe ser escrito en su totalidad por dicha persona.
```

**Condiciones de entrega:**

| **¿Qué se entrega?**            | **¿Qué no se entrega?**                           |
| ----                            |   ----                                            |
| Archivos fuente/source (.c)     | Archivos objeto (.o)                              |
| Archivos encabezado/header (.h) | Archivos ejecutables (programa, app, a.out, etc.) |
| Bibliotecas específicas (.a)    |                                                   |

Se deben entregar los ejercicios en un archivo zip (usar template como ayuda para el formato).

## Ejercicio 13.1
Implementar un programa que genere dos procesos, uno padre y uno hijo. Dichos procesos deben comunicarse a través de dos pipes (debido a que son unidireccionales). El proceso padre debe enviarle al proceso hijo la leyenda `"Luke, yo soy tu padre"` a lo que el proceso hijo debe responder `"Noooooooooo!!!"`. Colocar los printf() que considere necesario para demostrar el correcto funcionamiento de la comunicación. 

**Ayuda:** Conviene declarar un string genérico para la comunicación para saber de antemano la cantidad de bytes a recibir (por ejemplo, `char mensaje[MSJ_MAX]`).

## Ejercicio 13.2
Implementar un programa que primeramente deberá crear un pipe y luego generar dos procesos hijo. El primer proceso hijo debe redirigir stdout al extremo de escritura del pipe y luego ejecuta con `execlp()` el comando **`ps -eo pid,command,%mem --sort -%mem`**. El segundo proceso hijo debe redirigir su entrada desde stdin al extremo de lectura del pipe, y luego ejecuta el comando **`head`**. Después de crear ambos procesos, el proceso padre simplemente debe esperar a que los procesos hijo finalicen su ejecución.

En definitiva, el proceso padre hace lo mismo que un shell que ejecuta el comando **`ps -eo pid,command,%mem --sort -%mem | head`**.

**Ayuda:** Revisar las funciones `dup2()` y `execlp()`.

## Ejercicio 13.3
Implementar dos programas que se comunicarán a través de un named pipe (FIFO). El primer programa deberá enviarle al segundo programa un comando (`"/refran"`, `"/cancion"` o `"/pelicula"`) a lo que el segundo programa deberá responder con un refrán, el nombre de una canción o el nombre de una película. Hacer que lo devuelto varíe aleatoriamente dentro de una lista de posibles valores. Luego ambos programas deben terminar. Colocar los printf() que considere necesario para demostrar el correcto funcionamiento de la comunicación. 

## Ejercicio 13.4
Implementar un chat simple entre dos programas. Dichos programas se comunicarán a través de un named pipe (FIFO). Tener en cuenta que la comunicación será por turnos (un mensaje de cada programa por vez), y la misma terminará cuando uno de los dos programas envíe el comando `"/exit"`.

## Ejercicio 13.5
Implementar un programa, llamado **servidor**, el cual recibirá el path de un archivo de audio como argumento. Luego, enviará dicho archivo de audio a un programa **cliente** a  través de un named pipe (FIFO). El programa cliente deberá recibir dicho archivo y reproducirlo. Al finalizar el envío, el programa servidor terminará su ejecución y lo mismo ocurrirá en el programa cliente al terminar la reproducción.

**Nota:** Para la reproducción de los archivos de audio se podrán usar tanto los ejemplos vistos en clase (para los formatos `.raw` y `.imf`) como la biblioteca [libVLC](https://www.videolan.org/vlc/libvlc.html) (para `.mp3` y otros formatos).

## Referencias
Algunos ejercicios fueron obtenidos y adaptados de:
- Guía de Trabajos Prácticos 2011 - Informática I - Departamento de Electrónica - UTN FRBA
