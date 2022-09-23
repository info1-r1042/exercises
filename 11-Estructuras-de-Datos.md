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

## Ejercicio 11.7
Desarrollá un módulo para el manejo de pilas de números enteros. Dicho módulo deberá utilizar internamente estructuras autorreferenciadas para almacenar la información. Utilizá los siguientes prototipos:

```c
typedef struct Nodo {
    int valor;
    struct Nodo* siguiente;
} Nodo;

typedef enum Status {
    EXITO = 0,
    ERROR_FALLA_DE_MEMORIA,
    ERROR_PILA_VACIA
} Status;

// @brief Inserta un elemento en la pila.
Status push(Nodo** pila, int elemento);

// @brief Quita un elemento de la pila.
Status pop(Nodo** pila, int* elemento);

// @brief Devuelve el valor del próximo elemento a quitar de la pila (sin quitarlo).
Status espiar(Nodo* pila, int* elemento);

// @brief Imprime el contenido de la pila.
void imprimir(Nodo* pila);
```

## Ejercicio 11.8
Desarrollá un módulo para el manejo de colas de números enteros. Dicho módulo deberá utilizar internamente estructuras autorreferenciadas para almacenar la información. Utilizá los siguientes prototipos:

```c
typedef struct Nodo {
    int valor;
    struct Nodo* siguiente;
} Nodo;

typedef enum Status {
    EXITO = 0,
    ERROR_FALLA_DE_MEMORIA,
    ERROR_COLA_VACIA
} Status;

// @brief Inserta un elemento en la cola.
Status encolar(Nodo** cola, int elemento);

// @brief Quita un elemento de la cola.
Status desencolar(Nodo** cola, int* elemento);

// @brief Devuelve el valor del próximo elemento a quitar de la cola (sin quitarlo).
Status espiar(Nodo* cola, int* elemento);

// @brief Imprime el contenido de la cola.
void imprimir(Nodo* cola);
```

## Referencias 
Algunos ejercicios fueron obtenidos y adaptados de:
- Guía de Trabajos Prácticos 2011 - Informática I - Departamento de Electrónica - UTN FRBA
