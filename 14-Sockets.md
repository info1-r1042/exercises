# Ejercicios adicionales 14 - Sockets

## Ejercicio 14.1
Implemente una aplicación con arquitectura Cliente-Servidor que cumpla con los siguientes requisitos:

**Servidor:**
- Espera la conexión de un (1) cliente en el puerto TCP pasado como argumento del main.
- Aceptada la conexión enviará al cliente el mensaje `"Bienvenido! Conexión aceptada"` e imprimirá en pantalla la leyenda `"Nueva conexión desde la IP <IP>"`.
- Cada mensaje recibido desde el cliente, lo imprimirá en pantalla con el siguiente formato: `"Cliente[<IP>]: <mensaje>"`.
- En caso de que se reciba el comando `"/imagen"`, el servidor imprimirá la leyenda `"Cliente[<IP>]: Imagen solicitada"`, y le enviará una imagen al cliente a través del socket.
- La conexión con el cliente termina al recibir el comando `"/exit"`.
- La ejecución termina cuando el usuario oprime CTRL-C.

**Cliente:**
- Conecta con el servidor en la dirección IP y puerto TCP pasados como argumentos del main.
- Al recibir el mensaje `"Bienvenido! Conexión aceptada"` lo presenta en pantalla.
- El cliente enviará continuamente todos los mensajes que se ingresen por teclado.
- En el caso en que se envíe el comando `"/imagen"`, el cliente imprimirá la leyenda `"Imagen solicitada"`, tras lo cual esperará hasta recibir la imagen completamente y la mostrará al usuario. Luego, al pulsar cualquier tecla, se cerrará la imagen y el usuario  podrá continuar enviando mensajes al servidor.
- La conexión y ejecución terminan cuando el usuario envía el comando `"/exit"`.

## Ejercicio 14.2
Modificar el ejercicio 14.1 para que el servidor sea capaz de dar servicio a varios clientes, manejando cada instancia de conexión mediante un nuevo proceso hijo, mientras que el proceso padre se encargará de aceptar las conexiones entrantes.

**Ayuda:** El proceso padre deberá atender las defunciones de los procesos hijo sin bloquear su ejecución (ver ejercicio 12.5).    

## Ejercicio 14.3
Modificar el ejercicio 14.1 para que el servidor sea capaz de dar servicio a varios clientes, manejando cada instancia de conexión en el mismo proceso y evitando bloquear su ejecución mediante el uso de la función `select()`.

## Referencias
Algunos ejercicios fueron obtenidos y adaptados de:
- Guía de Trabajos Prácticos 2011 - Informática I - Departamento de Electrónica - UTN FRBA
