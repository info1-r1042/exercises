# Guía de Ejercicios 8 - Argumentos en Línea de Comandos

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












Trabajo Práctico 7 - Strings y Argumentos de main()
Enunciado 1:
Realizar un programa que reciba por argumento de main un número entre el 30 y el 99 y presente por
pantalla el <número>: <número en letras>.
Ej: 47: Cuarenta y siete
Deberá validar que el número se encuentre en ese rango.
Enunciado 2:

Implemente un programa que, al recibir por línea de comandos la cadena IP:PUERTO, imprima cada
cadena (IP y PUERTO) en diferentes líneas como se indica en el siguiente ejemplo:
Comando ejecutado Salida por pantalla
./ej_2 172.16.4.205:1234 La IP es: 172.16.4.205
El puerto es: 1234

Enunciado 3:
Implemente un programa que reciba por línea de comandos una cadena de caracteres (nombre) e
imprima por pantalla el la cadena cifrada utilizando el algoritmo rot13 que se detalla a continuación.

ROT13 es un sencillo cifrado utilizado para
ocultar un texto sustituyendo cada letra por la
letra que está trece posiciones antes o
después en el alfabeto (ver imagen). A se
convierte en N, B se convierte en O y así
sucesivamente hasta la letra M que la
convierte en la Z. Luego la secuencia se
invierte, la N se convierte en A, O se convierte
en B y así hasta la letra Z, que se convierte en
M.














Argumentos en línea de comandos
Describa qué son, qué tipos las definen y qué contienen las variables argc y argv en la ejecución de un programa.

Dada la siguiente ejecución de un programa:

$ ./programa -s "Hola Mundo!"
¿cuánto vale argc?

Haga un diagrama que muestre el contenido de argv.

Argumentos posicionales
En los próximos ejercicios, la función de cada argumento estará dada por su ubicación en la invocación al programa.

Escriba un programa que imprima por pantalla todos los argumentos recibidos, uno por línea.

Escriba un programa que reciba una cadena de caracteres e imprima su longitud, à la strlen().

Escriba un programa que reciba dos cadenas de caracteres e imprima el resultado de su comparación lexicográfica, como lo haría la función strcmp() o strcasecmp().

Escriba un programa que reciba como argumentos dos números e imprima el resultado de la operación módulo entre ambos.

Escriba un programa que imprima de manera ordenada los argumentos recibidos:

$ ./g07e07 Ser o "no ser," "esa es" "la cuestión"
Ser
esa es
la cuestión
no ser,
o
Si el primer parámetro del programa es -r, entonces los ordena al revés:

$ ./g07e07 Ser o "no ser," "esa es" "la cuestión"
o
no ser,
la cuestión
esa es
Ser
El siguiente programa reemplazará caracteres, recibidos como argumentos, en líneas leídas por stdin. Se debe ejecutar del siguiente modo:

$ cat archivo.txt | ./reemplazar viejo nuevo
donde viejo y nuevo son los caracteres a reemplazar. ¿Cómo modificaría el programa para que pueda reemplazar más que un carácter, por ejemplo, reemplazar x por equis, o "American National Standards Institute" por "ANSI", o "ISO" por "International Organization for Standardization", etc.

El siguiente programa generará muestras aleatorias en un intervalo dado por el usuario. El programa debe recibir como argumentos el inicio del intervalo, , el fin del intervalo, , y la cantidad de muestras a generar, , de forma tal que se ejecute de la siguiente manera:

./random x_i x_f n

$ ./g07e09 -3 2.65 10
2.0284
1.5767
0.4812
-1.1543
-0.7098
-0.1651
2.0144
0.2328
0.2302
1.3886
El siguiente programa procesará las líneas por stdin e imprimirá datos de las mismas. Escriba un programa que reciba como parámetros una posición y un ancho e imprima, de cada línea, los datos que comienzan en la posición posición y se componen de ancho caracteres. La ejecución del mismo es:

$ cat archivo.txt | ./extraer posición ancho
Este programa es de utilidad cuando se trabaja con datos almacenados en archivos formados por registros con campos de ancho fijo. El utilizar este tipo de formato permite un procesamiento muy veloz de los datos, y archivos más pequeños que la gran mayoría de los formatos (sin compresión). Un ejemplo de un archivo de este estilo:

Lista 4 bibliografia.txt
KernighanRitchieThe C Programming LanguagePrentice-Hall19889780131103702
KernighanRitchieEl lenguaje de programacioPearson Educa19919789688802052
Aguilar  ZahonerProgramacion en C: metodolMcGraw-Hill  20059788448198442
Deitel   Deitel C: How to Program         Pearson      20129780132990448
Bowman          Algorithms and Data StructOxford Univer20049780195174809
Bowman   HernándAlgoritmos y estructuras dOxford Univer19999789706134592
Kruse    Tondo  Data Structures and PrograPearson Educa20079788177584233
Los campos del documento son:

Autor 1: posición: 1, ancho: 9

Autor 2: posición: 10, ancho: 7

Título: posición: 17, ancho: 26

Editorial: posición: 43, ancho: 13

Año: posición: 56, ancho: 4

ISBN: posición: 60, ancho: 13

Ejemplo de ejecución:

$ cat bibliografia.txt | ./g07e10 60 13
9780131103702
9789688802052
9788448198442
9780132990448
9780195174809
9789706134592
9788177584233
El siguiente programa trabajará con archivos con campos separados por delimitadores (DSV) 1. El más común de ellos es el que utiliza comas (,) como separadores, el CSV 2. El archivo anterior podría escribirse como:

Lista 5 bibliografia.csv
Kernighan,Ritchie,The C Programming Language,Prentice Hall,1988,9780131103702
Kernighan,Ritchie,El lenguaje de programación C,Pearson Educación,1991,9789688802052
Aguilar,Zahonero,Programación en C: metodología, algoritmos y estructuras de datos,McGraw-Hill,2005,9788448198442
Deitel,Deitel.C: How to Program,Pearson,2012,9780132990448.
Bowman,,Algorithms and Data Structures: An Approach in C,Oxford University Press,2004,9780195174809
Bowman,Hernández,Algoritmos y estructuras de datos: aproximación en C,Oxford University Press,1999,9789706134592
Kruse,Tondo,Data Structures and Program Design in C,Pearson Education,2007,9788177584233
En este caso, implemente un programa que reciba como argumento el número de campo e imprima el campo correspondiente. Los números de campo comienzan en 1, mientras que el 0 corresponde a la línea completa.

Escriba un programa expr que evalúa expresiones en notación Polaca inversa 3 recibidas como argumento. Por ejemplo:

$ ./expr 2 222 111 + "*"
666
evalúa la operación: .

Argumentos no-posicionales
En los próximos ejercicios, la función de cada argumento estará dada por las banderas, flags, en la línea de comandos.

Modifique el programa del ejercicio 09 para que reciba los argumentos utilizando las siguientes banderas:

-a comienzo del intervalo

-b fin del intervalo

-n cantidad de muestras

-h muestra un mensaje de ayuda, sin realizar ninguna otra función

Las banderas deben poder aparecer en cualquier orden, por lo que las siguientes invocaciones del programa son equivalentes:

$ ./g07e13 -a -3 -b 2.65 -n 10
$ ./g07e13 -b 2.65 -a -3 -n 10
$ ./g07e13 -n 10 -b 2.65 -a -3
2.0422
1.6900
-1.0428
-0.3802
-1.7582
-1.3972
-1.5386
-0.0568
-2.3125
-2.6120
$ ./g07e13 -h
NOMBRE
       g07e13, sampler - genera lotes de números pseudo-aleatorios

SINOPSIS
       g07e13 [-a A] [-b B] [-n N] [-h]

DESCRIPCIÓN
       Generar un lote de N números pseudo-aleatorios en el intervalo
       [A,B). La distribución muestreada es U[A,B).

OPCIONES
       h
              muestra esta ayuda.
       a A
              comienzo del intervalo. Valor por omisión: 0.0.
       b B
              fin del intervalo. Valor por omisión: 1.0.
       n N
              cantidad de muestras a tomar. Valor por omisión: 100.

AUTORES
       Ada Lovelace, Alan Turing

LICENCIA
       GNU General Public License v3.0
Modifique el programa extractor de campos de ancho fijo (ver aquí) de forma tal que los argumentos del mismo se puedan recibir en cualquier orden. Para ello, agregue las siguientes banderas:

-p posición del campo

-a ancho del campo

-h muestra un mensaje de ayuda, sin realizar ninguna otra función

Ejemplo de ejecución:

$ cat bibliografia.txt | ./g07e14 -p 60 -a 13
$ cat bibliografia.txt | ./g07e14 -a 13 -p 60
9780131103702
9789688802052
9788448198442
9780132990448
9780195174809
9789706134592
9788177584233
$ ./g07e14 -h
NOMBRE
       g07e14, extractor - extrae campos de ancho fijo

SINOPSIS
       g07e14 -p POSICIÓN -a ANCHO [-h]

DESCRIPCIÓN
       Lee líneas de stdin y extrae porciones de texto de cada
       una de estas.

OPCIONES
       h
              muestra esta ayuda.
       p POSICIÓN
              posición en la que comienza un campo
       a ANCHO
              ancho del campo a extraer

AUTORES
       Steve Jobs, nah, mentira, "nunca" escribió código en su
       vida.

LICENCIA
       GNU General Public License v3.0
Sea la siguiente forma de onda

Escribir un programa con comandos en línea de órdenes que permita tabular la función dentro del intervalo [T1,T2) utilizando N puntos, aceptando la siguiente invocación:

sampler –alfa <a> -amp <A> -frec <f> -start <T1> -end <T2> -points <N>
Realizar las validaciones pertinentes.

Ejemplo de ejecución:

$ ./g07e15 -amp 3 -frec .6 -end 6 -start 0 -alfa 0.5 -points 10
0       3
0.6     -1.41665
1.2     -0.308511
1.8     1.06884
2.4     -0.84013
3       0.206853
3.6     0.265715
4.2     -0.364472
4.8     0.198392
5.4     0.0126596

$ ./g07e15 -h
NOMBRE
       g07e15, sampler - muestrea una senoidal con decaimiento
       exponencial

SINOPSIS
       g07e15 –alfa a -amp A -frec f -start T1 -end T2 -points N

DESCRIPCIÓN
       Dada la función:
                       -at
               f(t) = e    A cos(2 pi f t)
       toma N muestras a intervalos de tiempo regulares entre T1
       y T2. El span del intervalo entre muestras es (T2 - T1)/N

OPCIONES
       h
              muestra esta ayuda.
       alfa a
              tasa de dacaimiento
       amp A
              amplitud de la función en tiempo 0
       frec f
              frecuencia del oscilador
       start T1
              valor inicial del intervalo
       end T2
              valor final del intervalo
       points N
              cantidad de puntos a imprimir

AUTORES
       Bill Gatos, nah, mentira, en un mundo sin fronteras ¿para
       qué queremos puertas (Gates) y ventanas (Windows)?.

LICENCIA
       GNU General Public License v3.0
1
Campos separados por delimitadores, artículo de wikipedia [en]

2
Campos separados por comas, artículo de wikipedia [es] [en]

3
Notación Polaca Inversa, artículo de wikipedia [es] [en]










## Referencias
Algunos ejercicios fueron obtenidos y adaptados de:
- Guía de Trabajos Prácticos 2011 - Informática I - Departamento de Electrónica - UTN FRBA
- Guía de Ejercicios - Algoritmos y Programación I - UBA FIUBA
