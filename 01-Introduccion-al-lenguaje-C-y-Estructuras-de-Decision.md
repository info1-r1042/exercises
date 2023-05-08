# Guía de Ejercicios 1 - Introducción al lenguaje C y Estructuras de Decisión

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

## Ejercicio 1.1
Escribir un programa donde se ingresa por teclado una temperatura expresada en grados Celsius. Calcular su valor en grados Kelvin, y mostrar por pantalla el valor en °C y su equivalente en °K. Recordar que `°C = °K - 273`.

**Nota:** La temperatura es una magnitud referida a la noción de calor medible mediante un termómetro. La temperatura se mide con termómetros, los cuales pueden ser calibrados de acuerdo a una multitud de escalas que dan lugar a unidades de medición de la temperatura. En el Sistema Internacional de Unidades, la unidad de temperatura es el kelvin (K), y la escala correspondiente es la escala Kelvin o escala absoluta, que asocia el valor «cero kelvin» (0 K) al «cero absoluto», y se gradúa con un tamaño de grado igual al del grado Celsius. Sin embargo, fuera del ámbito científico el uso de otras escalas de temperatura es común. La escala más extendida es la escala Celsius, llamada «centígrada», y, en mucha menor medida, y prácticamente solo en los Estados Unidos, la escala Fahrenheit.

## Ejercicio 1.2
Escribir un programa donde se ingresa por teclado una temperatura expresada en grados Celsius. Calcular su valor en grados Fahrenheit, y mostrar por pantalla el valor en °C y su equivalente en °F. Recordar que `°C = 5/9 * (°F - 32)`.

**Nota:** La temperatura es una magnitud referida a la noción de calor medible mediante un termómetro. La temperatura se mide con termómetros, los cuales pueden ser calibrados de acuerdo a una multitud de escalas que dan lugar a unidades de medición de la temperatura. En el Sistema Internacional de Unidades, la unidad de temperatura es el kelvin (K), y la escala correspondiente es la escala Kelvin o escala absoluta, que asocia el valor «cero kelvin» (0 K) al «cero absoluto», y se gradúa con un tamaño de grado igual al del grado Celsius. Sin embargo, fuera del ámbito científico el uso de otras escalas de temperatura es común. La escala más extendida es la escala Celsius, llamada «centígrada», y, en mucha menor medida, y prácticamente solo en los Estados Unidos, la escala Fahrenheit.

## Ejercicio 1.3
Escribir un programa que dado un tiempo en horas, minutos y segundos compute el tiempo en segundos. Luego deberá mostrar el resultado obtenido por pantalla.

## Ejercicio 1.4
Escribir un programa que dadas las coordenadas de un vector en R2 `(x,y)`, compute la norma del mismo. Recordar que:

<div align="center">
  <img src="https://latex.codecogs.com/svg.latex?\left&space;\|&space;v&space;\right&space;\|=\sqrt{x^{2}&plus;y^{2}}" title="\left \| v \right \|=\sqrt{x^{2}+y^{2}}"/>
</div>

Luego deberá mostrar el resultado obtenido por pantalla.

**Nota:** Dado un vector de un espacio vectorial euclídeo, la norma de un vector es definida como la distancia (en línea recta) entre dos puntos A y B que delimitan al vector. Coincidiendo en un espacio euclídeo la norma de un vector con el módulo del vector AB.

## Ejercicio 1.5
Escribir un programa que dado el radio de un círculo compute:
- Su diámetro.
- Su perímetro.
- Su área.

Luego deberá mostrar los resultados obtenidos por pantalla.

## Ejercicio 1.6
Escribir un programa que dado el radio de una esfera compute:
- Su diámetro.
- Su volumen.
- Su área.

Luego deberá mostrar los resultados obtenidos por pantalla.

## Ejercicio 1.7
Escribir un programa que dados el radio de un cilindro y su altura compute:
- El diámetro de la base.
- El perímetro de la base.
- El área de la base.
- El volumen del cilindro.
- El área del cilindro.

Luego deberá mostrar los resultados obtenidos por pantalla.

## Ejercicio 1.8
Escribir un programa que reciba dos valores reales que correspondan a los extremos izquierdo y derecho de un intervalo. Luego, se debe dividir dicho intervalo en 4 subintervalos iguales. Se deberá mostrar por pantalla el rango ingresado y cada uno de los subrangos.

## Ejercicio 1.9
Escribir un programa que dado un número entero informe si el mismo es par o impar.

## Ejercicio 1.10
Escribir un programa que dado un número entero informe si el mismo es positivo, negativo o igual a cero.

## Ejercicio 1.11
Escribir un programa que dados dos números enteros informe si el primero es divisible por el segundo.

## Ejercicio 1.12
Escribir un programa que dado un número entero imprima el primer número múltiplo de 10 inferior a él. Por ejemplo, para 153 debe imprimir 150. Si el número ingresado es múltiplo de 10, se debe imprimir el mismo número.

## Ejercicio 1.13
Escribir un programa que dados 2 números enteros `a` y `b` los compare. La función debe informar si `a` es menor, igual, o mayor a `b`.

## Ejercicio 1.14
Escribir un programa que calcule la diferencia de dos números enteros e informe si la misma es positiva, negativa o cero.

## Ejercicio 1.15
Escribir un programa que reciba tres valores reales, correspondientes a las longitudes de los lados de un triángulo, y luego informe si los números ingresados conforman realmente un triángulo y si el triángulo ingresado es equilátero, isósceles o escaleno.

## Ejercicio 1.16
Escribir un programa que reciba tres valores reales, correspondientes a las longitudes de los lados de un triángulo, y luego informe si los números ingresados conforman realmente un triángulo y si el triángulo ingresado es rectángulo e indique cual de los valores es la hipotenusa.

## Ejercicio 1.17
Escribir un programa (utilizando la estructura **switch**) que permita realizar operaciones matemáticas entre dos operandos. Para ello se ingresan dos valores reales y el símbolo de la operación (`+`,`-`,`/`,`*`). Se deberán presentar en pantalla los datos, la operación y el resultado con el siguiente formato:

```
(Operando 1) (Operación) (Operando 2) = (Resultado)
```

Si la operación no es válida, se deberá presentar el mensaje **“Operación inválida”**. A su vez, si la operación es de división y el divisor es igual a 0, se deberá presentar el mensaje **“Operación inválida: División por Cero”**.

## Ejercicio 1.18
Escribir un programa que solicite al usuario un par de valores reales `(x,y)`, las cuales representarán las coordenadas cartesianas de un punto en el plano `R2`. Se pide determinar e informar por pantalla:
- Si el punto se encuentra en el origen (ambos valores iguales a 0).
- Si el punto se encuentra sobre un eje (sólo si **no** está ubicado en el origen), y si el mismo es el eje `x` o `y`.
- Si el punto se encuentra en un cuadrante (sólo si **no** está ubicado sobre **ninguno** de los ejes **ni** sobre el origen), y si el mismo es el cuadrante `I`, `II`, `III` o `IV`.
- La distancia del punto al origen de coordenadas. Recordar que:

<div align="center">
  <img src="https://latex.codecogs.com/svg.latex?d^{2}=x^{2}&plus;y^{2}" title="d^{2}=x^{2}+y^{2}"/>
</div>

## Ejercicio 1.19
Escribir un programa tal que ingresando los coeficientes `a`, `b` y `c` de una ecuación cuadrática <img src="https://latex.codecogs.com/svg.latex?a^{2}x&plus;bx&plus;c=0" title="a^{2}x+bx+c=0"/>, informe sus raíces, a partir de la ecuación resolvente:

<div align="center">
  <img src="https://latex.codecogs.com/svg.latex?x=\frac{-b\pm&space;\sqrt{b^{2}-4ac}}{2a}" title="x=\frac{-b\pm \sqrt{b^{2}-4ac}}{2a}"/>
</div>

Luego se debe mostrar el resultado por pantalla, por ejemplo:  

| a | b | c  | Salida por stdout                   |
|---|---|----|-------------------------------------|
| 0 | 0 | 0  | No es una ecuación de segundo grado |
| 0 | 1 | 1  | No es una ecuación de segundo grado |
| 1 | 2 | -8 | r0 = 2.00 ; r1 = -4.00              |
| 1 | 2 | 1  | r0 = -1.00 ; r1 = -1.00             |
| 1 | 1 | 1  | No tiene solución en el campo real  |
| 1 | 0 | 4  | No tiene solución en el campo real  |

## Ejercicio 1.20
Escribir un programa que dado un número real devuelva su valor absoluto.

## Ejercicio 1.21
Escribir un programa que dadas dos rectas definidas por su pendiente y su ordenada al origen devuelva el punto de intersección. Validar lo que considere necesario.

## Ejercicio 1.22
Escribir un programa que dado un mes y un año, devuelva la cantidad de días correspondientes a dicho mes. Tenga en cuenta años bisiestos (según calendario gregoriano, ver https://es.wikipedia.org/wiki/A%C3%B1o_bisiesto#Raz%C3%B3n_y_definici%C3%B3n_del_a%C3%B1o_bisiesto).

## Ejercicio 1.23
Escribir un programa que dada una fecha (día, mes, año), indique si es válida o no. Tenga en cuenta años bisiestos (según calendario gregoriano, ver https://es.wikipedia.org/wiki/A%C3%B1o_bisiesto#Raz%C3%B3n_y_definici%C3%B3n_del_a%C3%B1o_bisiesto).

## Ejercicio 1.24
Escribir un programa que dada una fecha (día, mes, año), indique los días que faltan hasta fin de mes. Tenga en cuenta años bisiestos (según calendario gregoriano, ver https://es.wikipedia.org/wiki/A%C3%B1o_bisiesto#Raz%C3%B3n_y_definici%C3%B3n_del_a%C3%B1o_bisiesto).

## Ejercicio 1.25
Escribir un programa que dada una fecha (día, mes, año), indique los días que faltan hasta fin de año. Tenga en cuenta años bisiestos (según calendario gregoriano, ver https://es.wikipedia.org/wiki/A%C3%B1o_bisiesto#Raz%C3%B3n_y_definici%C3%B3n_del_a%C3%B1o_bisiesto).

## Ejercicio 1.26
Escribir un programa que dada una fecha, indique la cantidad de días transcurridos en ese año hasta esa fecha. Tenga en cuenta años bisiestos (según calendario gregoriano, ver https://es.wikipedia.org/wiki/A%C3%B1o_bisiesto#Raz%C3%B3n_y_definici%C3%B3n_del_a%C3%B1o_bisiesto).

## Ejercicio 1.27
Escribir un programa que dado un monto de dinero (moneda peso argentino), calcule la mínima cantidad de billetes con los que se puede obtener dicho valor. Por ejemplo, `2320 ARS = 2*1000 ARS + 3*100 ARS + 1*20 ARS`.

## Ejercicio 1.28
Escribir un programa que dado un caracter, indique la familia noble correspondiente:

```
si el caracter es 'A':
    "House Arryn"
si el caracter es 'B':
    "House Baratheon"
si el caracter es 'F':
    "House Frey"
si el caracter es 'G':
    "House Greyjoy"
si el caracter es 'L':
    "House Lannister"
si el caracter es 'M':
    "House Martell"
si el caracter es 'S':
    "House Stark"
si el caracter es 'T':
    "House Targaryen"
si es otro caracter:
    "No lo conozco"
```

## Referencias
Algunos ejercicios fueron obtenidos y adaptados de:
- Guía de Trabajos Prácticos 2011 - Informática I - Departamento de Electrónica - UTN FRBA
- Guía de Ejercicios - Algoritmos y Programación I - UBA FIUBA
