# Guía de Ejercicios #2 - Estructuras de Iteración

```
Advertencia

La resolución conjunta o grupal de los ejercicios aquí presentes no está permitida, excepto en la medida en que puedas pedir ayuda a tus compañeros de clase y a otras personas, y siempre que esa ayuda no se reduzca a que otro haga el trabajo por vos.

El código fuente entregado por un estudiante debe ser escrito en su totalidad por dicha persona.
```


## Ejercicio 1.1
Realizar un programa que imprima los números enteros PARES entre el 0 y el 100 por la pantalla.

**Nota:** Recuerde que el 0 es considerado par.

## Ejercicio 1.2
Escribir un programa que realice la sumatoria de los números del 1 al 100. Y luego imprima el resultado por pantalla.

## Ejercicio 1.3
Escribir un programa que calcule el promedio de 10 valores numéricos reales ingresados por teclado y lo imprima por pantalla.

## Ejercicio 1.4
Ingresar un número entero por teclado y determinar si es primo. Se debe informar el resultado por pantalla.

## Ejercicio 1.5
Escribir un programa que realice la sumatoria del rango de números enteros entre dos valores ingresados por teclado 
 <br><br><br><br><br><br><br><br><br><br>

## Ejercicio 1.6
Realizar un programa que imprima los números enteros del 1 al 100 por pantalla. Pero para los números múltiplos de 3, debe imprimir la palabra “Fizz” en vez del número, para los números múltiplos de 5, debe imprimir la palabra “Buzz” en vez del número, y para aquel los números que son múltiplos tanto de 3 como de 5, debe imprimir la palabra “FizzBuzz” en vez del número.

***Ayuda:*** Para los números del 1 al 15 se debería obtener la siguiente salida:

|Salida por stdout|
|:---------------:|
| 	     1	      |
|	     2	      |
|     Fizz	      |
|	     4	      |
|     Buzz	      |
|     Fizz	      |
|      	 7	      |
| 	     8	      |
|     Fizz	      |
|     Buzz	      |
|       11	      |
|     Fizz	      |
|       13	      |
|       14	      |
|   FizzBuzz	  |

## Ejercicio 1.7
Escribir un programa que reciba un numero entero del 1 al 10 y luego imprima la tabla de multiplicar del mismo.

***Ayuda:*** En caso de recibir el 2, se deberan mostrar por pantalla el: 2, 4, 6, 8, 10, 12, 14, 16, 18 y, el 20.

## Ejercicio 1.8
Escriba un programa donde ingresa una serie de números reales. Cuando encuentra que la suma de los números ingresados tiene un valor mayor que '300', deja de leer e informa cuantos elementos tiene la serie.

**Nota:** Se deben admitir tanto números enteros como decimales que, a su vez, podran ser positivos o negativos según como desee el usuario que ingresara los mismos.

## Ejercicio 1.9
Escribir un programa donde ingresa una serie de valores enteros y luego informe la cantidad de valores pares e impares ingresados. El programa finaliza cuando se ingresa '0'.

**Nota:** El cero es la condición de finalización con lo cual no debe ser tomado en cuanta para el informe final del programa.

## Ejercicio 1.10
Implementar un programa que acumule números ingresados por teclado hasta que dicha acumulación supere el valor '100' o el valor ingresado sea 0. Informe el número acumulado en pantalla al finalizar el programa. Luego calcule el promedio e informe por pantalla.

**Nota:** Tener en cuenta que 0(cero) es la condición de fin, por lo cual no debe ser tenido en cuenta para el cálculo del promedio.

## Ejercicio 1.11 
Realizar un programa que reciba dos numeros enteros positivos. Si el primer número es par debera calcular el factorial del mismo pero, si es impar debera calcula la potencia del primero elevado por el segundo.

## Ejercicio 1.12 
Escribir un programa que imprima por pantalla todas las fichas del dominó, sin repetir.

## Ejercicio 1.13
Realizar un programa que recibe la magnitud de un número binario de 4 bits y luego imprime su representación en base 10. Resolver aplicando una estructura de iteración.

**Nota:**  El primer número ingresado debe considerarse como el más significativo (MSB)

***Ayuda:*** 
	
| 1° | 2° | 3° | 4° | Salida por stdout                    |
|:---|:---|:---|---:|  ---:                                |
| 1  | 0  | 0  | 0  | 	  El número ingresado es 8	       |
| 1  | 0  | 1  | 1  |    El número ingresado es 11	       |
<br><br><br><br><br><br><br><br><br><br>

## Ejercicio 1.14
Un tirador realiza 10 disparos a un blanco cuyo centro coincide con el origen decoordenadas. Leyendo la abscisa y la ordenada de cada impacto, deberá calcularse el puntaje obtenido. 
El blanco tiene cuatro zonas que, de acuerdo a la distancia del impacto al origen (R), son:

| ZONA      | DENOMINACIÓN | PUNTAJE |   |   |
|:--------: |:--------------:|:---------:|---|---|
|0<= R <=1  |    centro    |    10   |   |   |
|1 < R <= 5 |     medio    |     5   |   |   |
|5 < R <= 10|    externo   |     1   |   |
|    R > 10 |     falla    |     0   |

**Nota:** Realizar el ingreso de coordenadas por consola.

## Ejercicio 1.15
Un programa recibe por teclado pares de valores no nulos X e Y, que representan las coordenadas rectangulares de distintos puntos en el plano. El fin de datos se indica con X e Y iguales a cero. Se pide determinar e informar por pantalla:<br>
- a) Cantidad de puntos que pertenecen a cada cuadrante. 
- b) Sumatoria de las distancias al origen de los puntos pertenecientes al primer cuadrante.

## Ejercicio 1.16
El valor aproximado del número de Euler, e , se puede obtener con la siguiente fórmula:
 
<code> e = 1 + 1/1! + 1/2! + 1/3! + 1/4! + 1/5! + ... </code>
 		
Escribir un programa que calcule el valor aproximado de  e  mediante un ciclo repetitivo que termine cuando la diferencia entre dos aproximaciones sucesivas difiera en menos de 10 elevado a la -9. 

## Ejercicio 1.17
Realizar un programa que obtenga los factores positivos de un numero positivo.<br>

***Ayuda:*** Los <i>factores</i> pueden dividir exactamente a un número <u>sin un residuo o decimal</u>. Por ejemplo, 30 dividido entre 10 es 3, y 30 dividido entre 15 es 2, así que 2, 3, 10 y 15 son todos factores de 30.
<br><br><br><br><br><br><br><br><br><br>

## Ejercicio 1.18
Realizar un programa que calcule los puntos de 5 tiradas de 4 dados y las imprima.   
Ej,
| dado | tirada 1 | tirada 2 |etc|
|------|:--------:|:--------:|---|
| 1    | 2        | 5        |   |
| 2    | 5        | 2        |   |
| 3    | 4        | 5        |   |
| 4    | 2        | 1        |   |

- En caso de realizar 'Generala' (4 dados iguales) el programa debera interrumpir las tiradas para imprimir por pantalla una felicitacion al jugador y luego terminar. De no obtener generala, se debera imprimir el puntaje del jugador al finalizar las tiradas.

**Nota:** Las reglas de esta generala no son como la convencional, por ello se debe aclarar que los puntajes son los siguientes:

|     CONDICIÓN   | DENOMINACIÓN | PUNTAJE |
|:----------------|:------------:|:-------:|
| 4 dados iguales |   Generala   |    50   |
| 3 dados iguales |    Póker     |    40   |
| 2 dados iguales |    Full      |    35   |
| ningúno igual   |    Agua      |     0   |

***Ayuda:*** Si realizan 'man rand' en su consola van a encontrar una herramienta muy útil para generar números aleatorios, si deciden ir por dicha alternativa, deberan ajustar el rango de 'aleatoriedad' para lo cual deberan colocar '%6+1' luego de invocar a la funcion. ¿Qué sucede con la variable si en lugar de '6+1' ponen otros números?

## Ejercicio 1.19
Escribir un programa que tome un número entero en base 10 (decimal) y lo muestre en base 2 (binario) por pantalla.

## Ejercicio 1.20
Escribir un programa que tome un número entero en base 10 (decimal) y lo muestre por pantalla en entero en base 16 (hexadecimal).

**Nota:** Realizar el ejercicio sin usar "%x". Unicamente pueden usarlo para <i>comprobar</i> sus resultados.
<br><br><br><br><br>

## Ejercicio 1.21
Se tienen 5 sensores de temperatura, que registran 15 temperaturas distintas cada uno. Esas temperaturas se ingresan de a una por vez, primero las 15 del 1er sensor, luego las 15 del segundo, y así sucesivamente.<br>
Mostrar por pantalla:<br>
- a) Temperatura promedio detectada por cada sensor.
- b) Máxima temperatura registrada por cada sensor.
- c) Número de sensor que registró la temperatura máxima.

## Ejercicio 1.22
Escribir un programa que permita determinar el máximo y el mínimo de un conjunto de valores numericos reales ingresados por stdin (sin almacenar la totalidad de los valores leídos). A tal efecto debe ingresarse primero la cantidad esperada de elementos a procesar, y luego el lote de datos de a uno por vez. Finalizado el ingreso de datos, mostrar el resultado por stdout con 3 decimales. Realizar todas las validaciones que considere necesarias.

## Ejercicio 1.23
Escribir un programa que pida el número de legajo (entero de 8 cifras) y la nota de un examen de los alumnos de un curso. El fin de ingreso se indica con legajo igual a cero. El programa debe informar:<br>
- a) Cantidad de alumnos del curso
- b) Promedio de las notas 
- c) Cantidad de alumnos aprobados (aprueban con promedio igual o mayor que 6)
- d) Mayor nota.
- e) La cantidad de alumnos con cada calificación conceptual, por cada asignatura,
según la siguiente tabla:
	
| Calificación Conceptual | Nota numérica |
|:-----------------------:|:-------------:|
|     Sobresaliente       |       10      |
|      Muy bueno          |      8 ó 9    |
|       Bueno             |      6 ó 7    |
|      Regular            |      4 ó 5    |
|     Insuficiente        |      1 a 3    |
		
<br><br><br><br><br><br><br><br>

## Ejercicio 1.24
En el comienzo del nivel 1-1 en Super Mario Bros de Nintendo, Mario debe saltar sobre pirámides de bloques adyacentes, como se indica a continuación.

![Mario Bross saltando, juego de Nintendo Super Mario Bross](/home/milagros/Documents/info1/imagenes/MarioBross.png)

Codifiquemos dichas pirámides en C, aunque en texto, usando numerales (#) para los ladrillos, como se muestra a continuación (cada numeral es un poco más alto que ancho, por lo que las pirámides en sí también son más altas que anchas):<br><br>
\#<br>
\##<br>
\###<br>
\####<br><br>
Dejaremos que el usuario decida qué tan altas deben ser las pirámides solicitando primero un número entero positivo entre 1 y 8, inclusive.

**Nota:** Si el usuario no ingresa un número entero positivo dentro del rango indicado, el programa deberá volver a solicitar un número al usuario: <br>
<html>
$ ./mario<br>
Ingrese el alto: -1<br>
Ingrese el alto: 0<br>
Ingrese el alto: 42<br>
Ingrese el alto: 50<br>
Ingrese el alto: 5<br>
#<br>
##<br>
###<br>
####<br>
#####<br>
</html>

## Referencias 
Algunos ejercicios fueron obtenidos y adaptados de:
- Guía de Trabajos Prácticos 2011 - Informática I - Departamento de Electrónica - UTN FRBA
- Guía de Ejercicios - Algoritmos y Programación I - UBA FIUBA
- Set de Problemas - CS50 - Harvard University
