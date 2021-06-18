# Guía de Ejercicios 7 - Memoria Dinámica

```
Advertencia

La resolución conjunta o grupal de los ejercicios aquí presentes no está permitida, excepto en la medida en que puedas pedir ayuda a tus compañeros de clase y a otras personas, y siempre que esa ayuda no se reduzca a que otro haga el trabajo por vos.

El código fuente entregado por un estudiante debe ser escrito en su totalidad por dicha persona.
```

***<u>Condiciones de entrega:</u>***

| <b>¿Qué se entrega?</b>         | <b>¿Qué no se entrega?</b>                        |
| ----                            |   ----                                            |
| Archivos fuente/source (.c)     | Archivos objeto (.o)                              |
| Archivos encabezado/header (.h) | Archivos ejecutables (programa, app, a.out, etc.) |
| Bibliotecas específicas (.a)    |   |

Se deben entregar los tres ejercicios en un zip (usar template como ayuda para el formato).

**Importante:** Recordá validar **siempre** que no se reciben punteros **`NULL`**. En dicho caso, la función deberá retornar sin efectuar operación alguna y en caso de tener que retornar algún valor devolverá el valor **`-1`**.

Recordá también que se evaluarán las buenas prácticas de programación con respecto al pedido de memoria. Por lo tanto, ¡no te olvides de **liberar** la memoria pedida! (podés ayudarte del programa `valgrind` para veriﬁcarlo).

<br>

## Ejercicio 7.1
Utilizando las funciones `malloc`, `realloc` y `free`, desarrollar un programa en el que se ingrese cı́clicamente por teclado la cantidad en bytes de memoria que se desea reservar o liberar. El programa deberá reservar o liberar de un solo bloque de memoria y preguntar por un nuevo valor. Si el valor
es positivo, se reserva ese valor en bytes **más** de memoria para ese mismo bloque. Si es negativo, se **libera** ese valor en bytes de memoria. El programa debe ﬁnalizar (indicando lo sucedido) cuando:
- El valor ingresado es **`cero`**, indicando **cuánta** memoria había quedado reservada antes de ﬁnalizar el programa. No te olvides de liberar dicha memoria antes de ﬁnalizar.
- El resultado de reservar y liberar memoria equivale o es menor a **cero**.
- No hay **suﬁciente** espacio de memoria disponible para reservar. Al ﬁnalizar el programa, no te olvides de liberar cualquier espacio de memoria que haya quedado reservado.

## Ejercicio 7.2
Realizar un programa donde el usuario ingrese letras mayúsculas y minúsculas de a una a la vez. El ingreso ﬁnaliza cuando el usuario ingresa **`FFF`** (tres ’F’ seguidas). Tené en cuenta que no se conoce la cantidad de caracteres a ingresar y se deben validar que los caracteres ingresados correspondan solamente a letras mayúsculas y minúsculas, caso contrario son descartados y no por lo tanto no se almacenan. Al ﬁnalizar, se deben imprimir por pantalla los caracteres ingresados.

## Ejercicio 7.3
Realizar un programa donde el usuario ingrese letras mayúsculas y minúsculas de a una a la vez. El ingreso ﬁnaliza cuando el usuario ingresa **`.`** (un punto). Tené en cuenta que no se conoce la cantidad de caracteres a ingresar y se deben validar que los caracteres ingresados correspondan solamente a letras mayúsculas y minúsculas, caso contrario son descartados y no por lo tanto no se almacenan. Luego, se deberá implementar una función que ordene los caracteres ingresados por el usuario en orden alfabético. Se deben ordenar los caracteres sin importar si los mismos son letras mayúsculas o minúsculas.

**Ayuda:**

Suponiendo los siguientes caracteres ingresados:
```
“PvpxixCDvgnkLHQLlBvsJzgQLDmBxUeIhyUMvDiVpjCYvOshnaEvupb”
```
Se deberı́a obtener la siguiente salida:
```
“aBBbCCDDDEeggHhhIiiJjkLLLlMmnnOPpppQQssUUuVvvvvvvxxxYyz”
```

## Ejercicio 7.4
Desarrollá un programa que solicite el ingreso de las calificaciones (como número enteros) del primer parcial de los estudiantes de Informática 1. El ingreso de calificaciones finalizará cuando se ingrese un once (11). Tené en cuenta que las calificaciones deberán ser números comprendidos entre 0 y 10 (0 significa ausente), por lo que se debe validar la carga de datos. Una vez finalizada la carga de datos, se pide computar e imprimir en pantalla la cantidad de aprobados, desaprobados y ausentes. Utilizá los siguientes prototipos:

```c
void agregar_calificacion(int** calificaciones, int* cantidad, int calificacion);
void clasificar_calificaciones(const int* calificaciones, int cantidad, int* aprobados, int* desaprobados, int* ausentes);
```

## Ejercicio 7.5
Implementá una función que reciba un string y retorne una copia del mismo, utilizando memoria dinámica, por valor. Si por algún motivo no se puede, se deberá retornar **`NULL`**. Utilizá el siguiente prototipo:

```c
char* copiar_string(const char* string);
```

## Ejercicio 7.6
Implementá una función que reciba un string y retorne una copia del mismo, utilizando memoria dinámica, por referencia. La función deberá retornar `ERROR` (-1) si ocurrió algún error, y `EXITO` (0) en caso contrario. Utilizá el siguiente prototipo:

```c
int copiar_string(const char* string_original, char** string_copia);
```

## Ejercicio 7.7
Implementá una función que reciba un arreglo numérico y retorne una copia del mismo, utilizando memoria dinámica, por valor. Si por algún motivo no se puede, se deberá retornar **`NULL`**. Utilizá el siguiente prototipo:

```c
int* copiar_arreglo(const int* arreglo, int largo);
```

## Ejercicio 7.8
Implementá una función que reciba un arreglo numérico y retorne una copia del mismo, utilizando memoria dinámica, por referencia. La función deberá retornar `ERROR` (-1) si ocurrió algún error, y `EXITO` (0) en caso contrario. Utilizá el siguiente prototipo:

```c
int copiar_arreglo(const int* arreglo_original, int largo, int** arreglo_copia);
```

## Ejercicio 7.9
Implementá una función que reciba un string y un caracter. La función retorna una copia del string, pero elimina todo lo que esté después del caracter recibido. Utilizá memoria dinámica. La función deberá retornar `ERROR` (-1) si ocurrió algún error, y `EXITO` (0) en caso contrario. Utilizá el siguiente prototipo:

```c
int strip(const char* string_in, char caracter, char** string_out);
```

**Ejemplo:**
```
                                  _______________
                                 |               |
("Esto va ; esto no va", ';') -->|     strip     |--> "Esto va "
                                 |_______________|
```

## Ejercicio 7.10
Implementá una función que reciba un string y que retorne una copia del string eliminando los espacios al comienzo (si es que hay alguno). Utilizá memoria dinámica. La función deberá retornar `ERROR` (-1) si ocurrió algún error, y `EXITO` (0) en caso contrario. Utilizá el siguiente prototipo:

```c
int left_trim(const char* string_in, char** string_out);
```

**Ejemplo:**
```
                          ___________
                         |           |
"     la izquierda  " -->| left_trim |--> "la izquierda  "
                         |___________|
```

## Ejercicio 7.11
Implementá una función que reciba un string y que retorne una copia del string eliminando los espacios al final (si es que hay alguno). Utilizá memoria dinámica. La función deberá retornar `ERROR` (-1) si ocurrió algún error, y `EXITO` (0) en caso contrario. Utilizá el siguiente prototipo:

```c
int right_trim(const char* string_in, char** string_out);
```

**Ejemplo:**
```
                          ____________
                         |            |
"  la derecha       " -->| right_trim |--> "  la derecha"
                         |____________|
```

## Ejercicio 7.12
Implementá una función que reciba un string y que retorne una copia del string eliminando los espacios al comienzo y al final (si es que hay alguno). Utilizá memoria dinámica. La función deberá retornar `ERROR` (-1) si ocurrió algún error, y `EXITO` (0) en caso contrario. Utilizá el siguiente prototipo:

```c
int full_trim(const char* string_in, char** string_out);
```

**Ejemplo:**
```
                          ___________
                         |           |
"     el centro     " -->| full_trim |--> "el centro"
                         |___________|
```

## Ejercicio 7.13
Implementá una función que reciba un string, un caracter y una longitud. La función deberá retornar una copia del string original, centrado en la longitud especificada y rellenando los espacios restantes con el caracter pedido. Utilizá el siguiente prototipo:

```c
int centrar(const char* string_in, char** string_out);
```

**Ejemplo:**
```
                          _________
                         |         |
(" cadena ", '*', 12) -->| centrar |--> "** cadena **"
                         |_________|
```

## Ejercicio 7.14
Implementá una función que reciba un número entero y retorne un string que lo represente. Utilizá el siguiente prototipo:

```c
int itostr(int numero, char** string);
```

**Ejemplo:**
```
         ________
        |        |
9511 -->| itostr |--> "9511"
        |________|
```

## Ejercicio 7.15
Implementá una función que reciba un string que contenga varios campos, en formato de campos de ancho fijo, y un arreglo con los anchos de cada campo. La función debe retornar un vector de strings con cada campo extraído (copiado). Utilizá el siguiente prototipo:

```c
char** split(const char* string_in, const int* anchos, int cantidad_campos);
```

**Ejemplo:**
```
                           _______
                          |       |
("unodostres",{3,3,4}) -->| split |-->{"uno", "dos", "tres"}
                          |_______|
```

## Ejercicio 7.16
Implementá una función que reciba un string que contenga varios campos, en formato de campos de ancho fijo, y un arreglo con los anchos de cada campo. La función debe retornar un vector de strings con cada campo extraído (copiado). Utilizá el siguiente prototipo:

```c
void split(const char* string_in, const int* anchos, int cantidad_campos, char*** campos);
```

**Ejemplo:**
```
                           _______
                          |       |
("unodostres",{3,3,4}) -->| split |-->{"uno", "dos", "tres"}
                          |_______|
```

## Ejercicio 7.17
Implementá una función que reciba un string que contenga varios campos, en formato CSV (ver https://es.wikipedia.org/wiki/Valores_separados_por_comas). La función debe retornar un arreglo de strings con cada campo extraído y la cantidad de campos. Utilizá el siguiente prototipo:

```c
char** split_csv(const char* string_in, int* cantidad_campos);
```

**Ejemplo:**
```
                     ___________
                    |           |
("uno,dos,tres") -->| split_csv |-->({"uno", "dos", "tres"}, 3)
                    |___________|
```

## Ejercicio 7.18
Implementá una función que reciba un string que contenga varios campos, en formato CSV (ver https://es.wikipedia.org/wiki/Valores_separados_por_comas). La función debe retornar un arreglo de strings con cada campo extraído y la cantidad de campos. Utilizá el siguiente prototipo:

```c
void split_csv(const char* string_in, char*** campos, int* cantidad_campos);
```

**Ejemplo:**
```
                     ___________
                    |           |
("uno,dos,tres") -->| split_csv |-->({"uno", "dos", "tres"}, 3)
                    |___________|
```

## Ejercicio 7.19
Implementá una función que reciba un arreglo de strings y su longitud y retorne un string en formato CSV (ver https://es.wikipedia.org/wiki/Valores_separados_por_comas) uniendo todas los strings del vector, agregando el caracter delimitador entre ellos. Utilizá el siguiente prototipo:

```c
void join_csv(const char** string_in, char*** campos, int* cantidad_campos);
```

**Ejemplo:**
```
                            __________
                           |          |
({"uno", "dos", "tres"})-->| join_csv |-->"uno,dos,tres"
                           |__________|
```

## Ejercicio 7.20
Implementá una función que lea, de stdin, una cadena de caracteres de largo indefinido y la retorne por el nombre. Implementar otra función que realice lo mismo, pero retornando la cadena leída por la interfaz. Prototipos:

char * readline(void);

## Ejercicio 7.21
Implementá una función que lea, de stdin, una cadena de caracteres de largo indefinido y la retorne por el nombre. Implementar otra función que realice lo mismo, pero retornando la cadena leída por la interfaz. Prototipos:

bool readline(char **);
La función se puede implementar tanto con fgetc() como con fgets(). Hacerlo de ambas maneras.

## Ejercicio 7.22
Implementá una función que reciba el inicio de un intervalo, el final y la cantidad de puntos y retorne un arreglo de números linealmente espaciados entre el inicio y el final.

double * linspace(double inicio, double fin, size_t nelems);

## Ejercicio 7.23
Implementá una función que reciba el inicio de un intervalo, el final y la cantidad de puntos y retorne un arreglo de números linealmente espaciados entre el inicio y el final.

bool linspace(double inicio, double fin, size_t nelemes, double ** valores);

## Ejercicio 7.24
Implementá una función que reciba dos vectores de números y retorne un nuevo vector con los números de ambos vectores concatenados.

## Ejercicio 7.25
Implementá una función similar a la del ejercicio anterior, pero en lugar de retornar un nuevo vector, modifica el primero pegándole el segundo.

## Ejercicio 7.26
Implementá una función que retorne una matriz dinámica, de un tamaño pasado como argumento, siendo la misma inicializada con:

ceros,

## Ejercicio 7.27
unos,

## Ejercicio 7.28
la identidad,


## Referencias
Algunos ejercicios fueron obtenidos y adaptados de:
- Guía de Trabajos Prácticos 2011 - Informática I - Departamento de Electrónica - UTN FRBA
- Guía de Ejercicios - Algoritmos y Programación I - UBA FIUBA
