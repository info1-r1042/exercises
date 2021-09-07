# Guía de Ejercicios #10 - Estructuras avanzadas

```
Advertencia

La resolución conjunta o grupal de los ejercicios aquí presentes no está permitida, excepto en la medida en que puedas pedir ayuda a tus compañeros de clase y a otras personas, y siempre que esa ayuda no se reduzca a que otro haga el trabajo por vos.

El código fuente entregado por un estudiante debe ser escrito en su totalidad por dicha persona.
```
<br><br>

## Ejercicio 1.1
Se desea implementar un módulo de manejo de pilas. Para ello, dicho módulo debe poseer las siguientes funciones:
|   |    |
|:----:|:----:|
|int push(Nodo** pila, int* largo, Nodo nodo)|Inserta un nodo en la pila.|
|int pop(Nodo** pila, int* largo, Nodo* nodo)|Quita un nodo de la pila. |
|int espiar(Nodo* pila, int largo, Nodo* nodo)|Devuelve el valor del próx. nodo a quitar de la pila.|
|int mostrar(Nodo* pila, int largo)|Imprime el contenido de la pila.|
||| 

## Ejercicio 1.2
Se desea implementar un módulo de manejo de colas. Para ello, dicho módulo debe poseer las siguientes funciones:
| | |
|:----:|:----:|
|int encolar(Nodo** cola, int* largo, Nodo nodo)|Inserta un nodo en la cola.|
|int desencolar(Nodo** cola, int* largo, Nodo* nodo) |Quita un nodo de la cola.|
|int espiar(Nodo* cola, int largo, Nodo* nodo)|Devuelve el valor del nodo a quitar de la cola.|
|int mostrar(Nodo* cola, int largo) |Imprime el contenido de la cola.|
| | |
<br><br><br><br><br>

## Ejercicio 1.3
Implemente un programa que permita manejar la lista de espera de un servicio telefonico:<br> 
Al ingresar por consola la letra C, se podrá ingresar un nuevo cliente que poseerá: un nombre, apellido, edad y, el sistema le entregará un <i>número de atención</i>.<br>
Al ingresar por consola la letra A, el sistema permite 'atender' a los clientes, con lo cual al ingresar algún numero de atención el sistema muestra los datos de dicho cliente, si existe, y da la opcion de retirarlo de la lista.
<br><br>

## Ejercicio 1.4
Utilizando la siguiente estructura:<br>
>typedef struct Nodo {<br>
> char usuario [ 30 ] ;<br>
> int clave ;<br>
} Nodo ;<br><br>

Se desea implementar un módulo de manejo de arreglos dinámicos (vectores). Para ello, dicho módulo debe poseer las siguientes funciones:<br>
- int insertar(Nodo** vector, int* largo, Nodo nodo, int posicion); <br>
>Inserta un nodo en la posición indicada.<br>
- int eliminar(Nodo** vector, int* largo, Nodo* nodo, int posicion); <br> 
>Elimina el nodo presente en la posición indicada.<br>
- int obtener(Nodo* vector, int largo, Nodo* nodo, int posicion); <br> 
>Devuelve el valor del nodo presente en la posición indicada.<br>
- int buscar(Nodo* vector, int largo, Nodo nodo, int* posicion);<br>
>Devuelve la posición del nodo con un valor coincidente al indicado.<br>
- int mostrar(Nodo* vector, int largo);<br>
>Imprime el contenido del vector.   


<br><br><br><br><br><br><br><br>

## Ejercicio 1.5
Impremente un código que resuelva el juego de las Torres de Hanoi para 3 discos utilizando <b>pilas</b>.
Para esto, es necesario tener tres pilas: una origen, en la cual se encuentran los 3 discos al inicio; una auxiliar y; una pila de destino que, es en la que deberán encontrarse los discos al finalizar el programa.<br><br>
![Procedimiento para resolver las torres de hanoi de tres discos](/home/milagros/Documents/info1/imagenes/Hanoi.jpg)
<br>
<u>Reglas del juego:</u><br>
- Sólo se puede mover un disco a la vez, cada disco se moverá cuando se oprima la tecla 's'.
- Un disco de mayor tamaño no puede quedar arriba de uno más chico
- Solo se puede desplazar el disco que se encuentre arriba de los otros en una pila


## Ejercicio 1.6

## Ejercicio 1.7


## Ejercicio 1.8


## Ejercicio 1.9

## Ejercicio 1.10



## Referencias 
Algunos ejercicios fueron obtenidos y adaptados de:
- Guía de Trabajos Prácticos 2011 - Informática I - Departamento de Electrónica - UTN FRBA
