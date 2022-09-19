# Guía de Ejercicios 11 - Estructuras de Datos

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

**Importante:** Recordá que se evaluarán las buenas prácticas de programación con respecto al pedido de memoria. Por lo tanto, ¡no te olvides de **liberar** la memoria pedida! (podés ayudarte del programa `valgrind` para veriﬁcarlo).

Tené en cuenta también que para **todos** los ejercicios, se pide también implementar (y entregar) una función main que demuestre el correcto funcionamiento del módulo.

## Ejercicio 11.1
Desarrollá un módulo para el manejo de arreglos dinámicos (vectores). Utilizá los siguientes prototipos:

```c
typedef struct Nodo {
    char usuario[30];
    int edad;
} Nodo;

typedef enum Status {
    EXITO = 0,
    ERROR_FALLA_DE_MEMORIA,
    ERROR_POSICION_INVALIDA,
    ERROR_VECTOR_VACIO
} Status;

// @brief Agrega un elemento en el vector.
Status agregar(Nodo** vector, int* largo, Nodo nodo);

// @brief Quita el elemento presente en la posición indicada.
Status eliminar(Nodo** vector, int* largo, int posicion);

// @brief Devuelve el valor del elemento presente en la posición indicada.
Status obtener(Nodo* vector, int largo, int posicion, Nodo* nodo);

// @brief Imprime el contenido del vector.
Status imprimir(Nodo* vector, int largo);
```

## Ejercicio 11.2
Desarrollá un módulo para el manejo de pilas. Dicho módulo deberá utilizar un arreglo dinámico (vector) para almacenar la información. Utilizá los siguientes prototipos:

```c
typedef struct Nodo {
    char usuario[30];
    int edad;
} Nodo;

typedef enum Status {
    EXITO = 0,
    ERROR_FALLA_DE_MEMORIA,
    ERROR_PILA_VACIA
} Status;

// @brief Inserta un elemento en la pila.
Status push(Nodo** pila, int* largo, Nodo nodo);

// @brief Quita un elemento de la pila.
Status pop(Nodo** pila, int* largo, Nodo* nodo);

// @brief Devuelve el valor del próximo elemento a quitar de la pila (sin quitarlo).
Status espiar(Nodo* pila, int largo, Nodo* nodo);

// @brief Imprime el contenido de la pila.
void imprimir(Nodo* pila, int largo);
```

## Ejercicio 11.3
Desarrollá un módulo para el manejo de colas. Dicho módulo deberá utilizar un arreglo dinámico (vector) para almacenar la información. Utilizá los siguientes prototipos:

```c
typedef struct Nodo {
    char usuario[30];
    int edad;
} Nodo;

typedef enum Status {
    EXITO = 0,
    ERROR_FALLA_DE_MEMORIA,
    ERROR_COLA_VACIA
} Status;

// @brief Inserta un elemento en la cola.
Status encolar(Nodo** cola, int* largo, Nodo nodo);

// @brief Quita un elemento de la cola.
Status desencolar(Nodo** cola, int* largo, Nodo* nodo);

// @brief Devuelve el valor del próximo elemento a quitar de la cola (sin quitarlo).
Status espiar(Nodo* cola, int largo, Nodo* nodo);

// @brief Imprime el contenido de la cola.
void imprimir(Nodo* cola, int largo);
```

## Ejercicio 11.4
Desarrollá un módulo para el manejo de arreglos dinámicos (vectores) de números enteros. Para mejorar la abstracción y el encapsulamiento del módulo, la información correspondiente al vector deberá estar contenida en una estructura creada para tal fin. Utilizá los siguientes prototipos:

```c
typedef struct Vector {
    int* elementos;
    int largo;
} Vector;

typedef enum Status {
    EXITO = 0,
    ERROR_FALLA_DE_MEMORIA,
    ERROR_POSICION_INVALIDA,
    ERROR_VECTOR_VACIO
} Status;

// @brief Crea un vector.
Vector* crear();

// @brief Agrega un elemento en el vector.
Status agregar(Vector* vector, int elemento);

// @brief Quita el elemento presente en la posición indicada.
Status eliminar(Vector* vector, int posicion);

// @brief Devuelve el valor del elemento presente en la posición indicada.
Status obtener(Vector* vector, int* elemento, int posicion);

// @brief Imprime el contenido del vector.
void imprimir(Vector* vector);

// @brief Destruye el vector.
void destruir(Vector* vector);
```

## Ejercicio 11.5
Desarrollá un módulo para el manejo de pilas de números enteros. Dicho módulo deberá utilizar internamente un arreglo dinámico (vector) para almacenar la información. Para mejorar la abstracción y el encapsulamiento del módulo, la información correspondiente a la pila deberá estar contenida en una estructura creada para tal fin. Utilizá los siguientes prototipos:

```c
typedef struct Pila {
    int* elementos;
    int largo;
} Pila;

typedef enum Status {
    EXITO = 0,
    ERROR_FALLA_DE_MEMORIA,
    ERROR_PILA_VACIA
} Status;

// @brief Crea una pila.
Pila* crear();

// @brief Inserta un elemento en la pila.
Status push(Pila* pila, int elemento);

// @brief Quita un elemento de la pila.
Status pop(Pila* pila, int* elemento);

// @brief Devuelve el valor del próximo elemento a quitar de la pila (sin quitarlo).
Status espiar(Pila* pila, int* elemento);

// @brief Imprime el contenido de la pila.
void imprimir(Pila* pila);

// @brief Destruye la pila.
void destruir(Pila* pila);
```

## Ejercicio 11.6
Desarrollá un módulo para el manejo de colas de números enteros. Dicho módulo deberá utilizar internamente un arreglo dinámico (vector) para almacenar la información. Para mejorar la abstracción y el encapsulamiento del módulo, la información correspondiente a la cola deberá estar contenida en una estructura creada para tal fin. Utilizá los siguientes prototipos:

```c
typedef struct Cola {
    int* elementos;
    int largo;
} Cola;

typedef enum Status {
    EXITO = 0,
    ERROR_FALLA_DE_MEMORIA,
    ERROR_COLA_VACIA
} Status;

// @brief Crea una cola.
Cola* crear();

// @brief Inserta un elemento en la cola.
Status encolar(Cola* cola, int elemento);

// @brief Quita un elemento de la cola.
Status desencolar(Cola* cola, int* elemento);

// @brief Devuelve el valor del próximo elemento a quitar de la cola (sin quitarlo).
Status espiar(Cola* cola, int* elemento);

// @brief Imprime el contenido de la cola.
void imprimir(Cola* cola);

// @brief Destruye la cola.
void destruir(Cola* cola);
```

## Ejercicio 11.3
Implemente un programa que permita manejar la lista de espera de un servicio telefonico:<br> 
Al ingresar por consola la letra C, se podrá ingresar un nuevo cliente que poseerá: un nombre, apellido, edad y, el sistema le entregará un <i>número de atención</i>.<br>
Al ingresar por consola la letra A, el sistema permite 'atender' a los clientes, con lo cual al ingresar algún numero de atención el sistema muestra los datos de dicho cliente, si existe, y da la opcion de retirarlo de la lista.

## Ejercicio 11.5
Impremente un código que resuelva el juego de las Torres de Hanoi para 3 discos utilizando <b>pilas</b>.
Para esto, es necesario tener tres pilas: una origen, en la cual se encuentran los 3 discos al inicio; una auxiliar y; una pila de destino que, es en la que deberán encontrarse los discos al finalizar el programa.<br><br>
![Procedimiento para resolver las torres de hanoi de tres discos](/home/milagros/Documents/info1/imagenes/Hanoi.jpg)
<br>
<u>Reglas del juego:</u><br>
- Sólo se puede mover un disco a la vez, cada disco se moverá cuando se oprima la tecla 's'.
- Un disco de mayor tamaño no puede quedar arriba de uno más chico
- Solo se puede desplazar el disco que se encuentre arriba de los otros en una pila
<br>

## Ejercicio 11.6
Para este ejercicio deberá desarrollar un programa que simule un colectivo, donde entran y salen pasajeros del mismo, como si fuera una cola. Para dicho programa usted tendrá un menú en el cual tendrá dos opciones para el chofer: abrir la puerta delantera y, abrir la puerta trasera.<br>
Al abrir la puerta delantera los pasajeros ingresan a la cola mientras que al abrir la puerta trasera los pasajeros salen. En este caso el tiempo de ingreso y egreso será de un segundo, por ejemplo: luego de que ingrese un pasajero, pasará un segundo antes de que ingrese otro a no ser que se salga del menu de ingreso(se cierre la primer puerta).<br>
Considere a cada pasajero como una estructura de datos que contiene un nombre y un número de ticket. El nombre deberá generarse aleatoriamente mientras que el ticket es un contador que se reinicia con el inicio del programa.

**Nota:** Solo es posible abrir una puerta por vez y el colectivo tiene un límite de 30 pasajeros. <br><br>
![imagen de colectivo](/home/milagros/Documents/info1/imagenes/bondi.jpeg)

## Ejercicio 11.7
Escribir una programa que simule el trabajo de una torre de control de un aeropuerto con una sola pista de aterrizaje. El avión debe considerarse como una estructura que contenga el nombre del avión(por ejemplo 'AR156') y su condicion de espera.<br>
Deberá generar 4 funciones: <br>
-  Para avisar que un avión quiere aterrizar en la pista: nuevo_arribo('AR156');//recibe el nombre del avion
-  Para avisar que un avión quiere despegar de la pista: nueva_partida('AR156');//recibe el nombre del avion
-  Para mostrar el estado actual de espera (los que esperan para aterrizar y los que esperan para despegar): ver_estado();
-  Para asignar la pista a un avión: asignar_pista();//quita un avión de la cola

**Nota:** Los aviones que están esperando para aterrizar tienen prioridad sobre los que están esperando para despegar. 

![imagen de torre de control](/home/milagros/Documents/info1/imagenes/torre_control.jpeg)

## Referencias 
Algunos ejercicios fueron obtenidos y adaptados de:
- Guía de Trabajos Prácticos 2011 - Informática I - Departamento de Electrónica - UTN FRBA
- Guía de Trabajos Prácticos 2019 - Informática I - Departamento de Electrónica - UTN FRBA
- Guía de Ejercicios - Algoritmos y Programación I - UBA FIUBA
