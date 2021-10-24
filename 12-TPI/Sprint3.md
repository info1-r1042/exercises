6.
6.1.
UTN.BA
Sprint 4 - Arquitectura Cliente/Servidor
Tarea 1a (Sólo para quienes desarrollan Infotify)
Dividir la funcionalidad implementada hasta el momento en dos aplicaciones diferentes, una que
cumplirá la función de servidor y otra la de cliente. El servidor deberá ser capaz de aceptar conexiones
entrantes de múltiples clientes, y enviará las canciones que se vayan solicitando a través de un socket
a la aplicación cliente. Para implementar la concurrencia en el servidor, se pueden utilizar tanto la
función select, como múltiples procesos. Además el servidor será quien tendrá la base de datos, con lo
cual las operaciones de registro, login y logout se realizarán a través de él. Recordar que no se debe
hacer streaming del archivo de audio, sino que debe recibirse primero en cliente y luego comenzar a
reproducirse.
6.2.
Tarea 1b (Sólo para quienes desarrollan Infoﬂix)
Dividir la funcionalidad implementada hasta el momento en dos aplicaciones diferentes, una que
cumplirá la función de servidor y otra la de cliente. El servidor deberá ser capaz de aceptar conexiones
entrantes de múltiples clientes, y enviará los videos que se vayan solicitando a través de un socket
a la aplicación cliente. Para implementar la concurrencia en el servidor, se pueden utilizar tanto la
función select, como múltiples procesos. Además el servidor será quien tendrá la base de datos, con
lo cual las operaciones de registro, login y logout se realizarán a través de él. Recordar que se debe
hacer streaming del archivo de video, es decir, debe reproducirse a medida que se reciben cada uno
de los cuadros.
6.3.
Tarea 2

6.4.
Tarea 3 (Sólo para quienes desarrollan Infotify)
Realizar una interfaz gráﬁca de usuario (GUI) en la aplicación cliente, dónde al menos se pueda
reproducir, pausar y parar la reproducción en curso.

## Fecha de Entrega
El código del presente sprint deberá estar subido al repositorio para las 23:55hs del Domingo 28 de
Noviembre de 2021.
