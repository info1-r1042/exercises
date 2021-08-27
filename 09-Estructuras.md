# Guía de Ejercicios 9 - Estructuras

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

**Importante:** Recordá también que se evaluarán las buenas prácticas de programación con respecto al pedido de memoria. Por lo tanto, ¡no te olvides de **liberar** la memoria pedida! (podés ayudarte del programa `valgrind` para veriﬁcarlo).

<br>

## Ejercicio 9.1
Desde la Subsecretaría de Tecnologías de la Información y Comunicación de la facultad nos solicitan implementar un módulo para el SIU Guaraní que permita almacenar y operar sobre las calificaciones finales obtenidas por los estudiantes. Para ello utilizaremos una estructura con los siguientes campos:
- Nombre (hasta 25 caracteres).
- Apellido (hasta 25 caracteres).
- Legajo.
- Carrera.
- Código de la materia (valor entero).
- Nombre de la materia (hasta 25 caracteres).
- Calificación final (valor entero).
- Fecha de aprobación (en formato Unix epoch).
- Libro (hasta 10 caracteres).
- Folio (valor entero).

Se nos pide implementar un módulo capaz de agregar, eliminar (por legajo y código de la materia), ordenar (por calificación o por apellido de forma lexicográfica), e imprimir calificaciones. Las calificaciones deberán ser almacenados en un arreglo dinámico. Para ello se deberán implementar las siguientes funciones:

```c
typedef struct Calificacion
{
    /*Definir*/
} Calificacion;

// @brief Agrega una calificacion al vector de calificaciones. Retorna EXITO o ERROR.
int calificaciones_agregar(/*Definir*/ calificaciones, /*Definir*/ cantidad_calificaciones, /*Definir*/ calificacion);

// @brief Elimina una calificacion del vector de calificaciones (por legajo y código de la materia). Retorna EXITO o ERROR.
int calificaciones_eliminar(/*Definir*/ calificaciones, /*Definir*/ cantidad_calificaciones, /*Definir*/ usuario, /*Definir*/ timestamp);

// @brief Imprime el contenido de una calificacion en pantalla con el siguiente formato ejemplo:
//
// Marty McFly - 2014321 - Ing. Electrónica - 950452 - Informática I - R0042 - 101 - 8 (ocho) - 11/02/2013
void calificacion_imprimir(/*Definir*/ calificacion);

// @brief Imprime el contenido del vector de calificaciones (reutilizar función anterior).
void calificaciones_imprimir(/*Definir*/ calificaciones, /*Definir*/ cantidad_calificaciones);

// @brief Ordena las calificaciones del vector por calificación o por apellido de forma lexicográfica.
void calificaciones_ordenar(/*Definir*/ calificaciones, /*Definir*/ cantidad_calificaciones, /*Definir*/ criterio_ordenamiento);
```

Se pide también implementar un main que demuestre el correcto funcionamiento del módulo.

## Ejercicio 9.2
Estamos armando nuestra propia versión de Twitter, y para ello debemos ser capaces de almacenar los Tweets que cada uno de los usuario desee postear. Para ello utilizaremos una estructura con los siguientes campos:
- Nombre (hasta 25 caracteres).
- Usuario (hasta 25 caracteres).
- Fecha de creación (en formato Unix epoch).
- Mensaje (hasta 140 caracteres).
- Cantidad de likes.
- Cantidad de retweets.

Se nos pide implementar un módulo capaz de agregar, eliminar (por usuario y fecha de creación), ordenar (por cantidad de likes o retweets), e imprimir Tweets. Los Tweets deberán ser almacenados en un arreglo dinámico. Para ello se deberán implementar las siguientes funciones:

```c
typedef struct Tweet
{
    /*Definir*/
} Tweet;

// @brief Agrega un Tweet al vector de Tweets. Retorna EXITO o ERROR.
int tweets_agregar(/*Definir*/ tweets, /*Definir*/ cantidad_tweets, /*Definir*/ tweet);

// @brief Elimina un Tweet del vector de Tweets (por usuario y fecha de creación). Retorna EXITO o ERROR.
int tweets_eliminar(/*Definir*/ tweets, /*Definir*/ cantidad_tweets, /*Definir*/ usuario, /*Definir*/ timestamp);

// @brief Imprime el contenido de un Tweet en pantalla con el siguiente formato ejemplo:
//
// 5:33 a.m. - 19 jul. 2021
// Terminator @terminatorok
// ---
// Volveré!
// ---
// Likes: 109
// Retweets: 24
void tweet_imprimir(/*Definir*/ tweet);

// @brief Imprime el contenido del vector de Tweets (reutilizar función anterior).
void tweets_imprimir(/*Definir*/ tweets, /*Definir*/ cantidad_tweets);

// @brief Ordena los Tweets del vector por cantidad de likes o de retweets.
void tweets_ordenar(/*Definir*/ tweets, /*Definir*/ cantidad_tweets, /*Definir*/ criterio_ordenamiento);
```

Se pide también implementar un main que demuestre el correcto funcionamiento del módulo.

## Ejercicio 9.3
Para un proyecto de un grupo de investigación de robótica de la facultad se nos pide implementar un módulo que permita almacenar y operar sobre las poses obtenidas de un robot. La pose de un robot nos dice su ubicación, tanto en dos o tres dimensiones y también su orientación. Los mensajes de pose recibidos poseen el siguiente formato:

```c
typedef struct Header
{
    char robot[25];
    time_t timestamp;
} Header;

typedef struct Posicion {
    double x, y, z;
} Posicion;

typedef struct Orientacion {
    double yaw, pitch, roll;
} Orientacion;

typedef struct Pose {
    Posicion posicion;
    Orientacion orientacion;
} Pose;

typedef struct RobotPose {
    Header header;
    Pose pose;
} RobotPose
```

Se nos pide implementar un módulo capaz de agregar, eliminar (por robot y timestamp), ordenar (por distancia al origen de coordenadas), e imprimir las poses del robot. Las poses deberán ser almacenadas en un arreglo dinámico. Para ello se deberán implementar las siguientes funciones:

```c
// @brief Agrega una pose al vector de poses. Retorna EXITO o ERROR.
int poses_agregar(/*Definir*/ poses, /*Definir*/ cantidad_poses, /*Definir*/ pose);

// @brief Elimina un pose del vector de poses (por usuario y timestamp). Retorna EXITO o ERROR.
int poses_eliminar(/*Definir*/ poses, /*Definir*/ cantidad_poses, /*Definir*/ usuario, /*Definir*/ timestamp);

// @brief Imprime la pose del robot en pantalla con el siguiente formato ejemplo:
//
// Robot: WALL-E
// Timestamp: 1630032476
// Posicion:
//   x: 1.5
//   y: 0.2
//   z: 0.9
// Orientacion:
//   yaw: 75
//   pitch: 32
//   roll: 63
void pose_imprimir(/*Definir*/ pose);

// @brief Imprime el contenido del vector de poses (reutilizar función anterior).
void poses_imprimir(/*Definir*/ poses, /*Definir*/ cantidad_poses);

// @brief Ordena las poses del vector por distancia al origen de coordenadas.
void poses_ordenar(/*Definir*/ poses, /*Definir*/ cantidad_poses);
```

## Ejercicio 9.4
Un familiar que posee una inmobiliaria nos pide implementar un módulo que permita almacenar y operar sobre las distintas publicaciones de alquiler y venta de inmuebles. Para ello utilizaremos una estructura con los siguientes campos:
- Operación (Alquiler o Venta).
- Tipo (Casa, Departamento, PH).
- Metros cuadrados (valor entero).
- Cantidad de ambientes.
- Precio (valor entero)
- Dirección (hasta 25 caracteres).
- Barrio (hasta 25 caracteres).
- Ciudad (hasta 25 caracteres).
- Anunciante (hasta 25 caracteres).
- Fecha de publicación (en formato Unix epoch).

Se nos pide implementar un módulo capaz de agregar, eliminar (por anunciante y fecha de publicación), ordenar (por precio o metros cuadrados), e imprimir publicaciones. Las publicaciones deberán ser almacenadas en un arreglo dinámico. Para ello se deberán implementar las siguientes funciones:

```c
typedef struct Publicacion
{
    /*Definir*/
} Publicacion;

// @brief Agrega una publicacion al vector de publicaciones. Retorna EXITO o ERROR.
int publicaciones_agregar(/*Definir*/ publicaciones, /*Definir*/ cantidad_publicaciones, /*Definir*/ publicacion);

// @brief Elimina una publicacion del vector de publicaciones (por anunciante y fecha de publicación). Retorna EXITO o ERROR.
int publicaciones_eliminar(/*Definir*/ publicaciones, /*Definir*/ cantidad_publicaciones, /*Definir*/ anunciante, /*Definir*/ timestamp);

// @brief Imprime el contenido de una publicacion en pantalla con el siguiente formato ejemplo:
//
// Departamento - 64m2 - 4 ambientes
// Venta - USD 155000
// Maza al 100, Almagro, Capital Federal
// ---
// Lepore Propiedades - Publicado hace 259 días.
void publicacion_imprimir(/*Definir*/ publicacion);

// @brief Imprime el contenido del vector de publicaciones (reutilizar función anterior).
void publicaciones_imprimir(/*Definir*/ publicaciones, /*Definir*/ cantidad_publicaciones);

// @brief Ordena las publicaciones del vector por precio o metros cuadrados.
void publicaciones_ordenar(/*Definir*/ publicaciones, /*Definir*/ cantidad_publicaciones, /*Definir*/ criterio_ordenamiento);
```

Se pide también implementar un main que demuestre el correcto funcionamiento del módulo.

## Ejercicio 9.5
Para un banco se nos pide implementar un módulo que permita almacenar y operar sobre las distintas cuentas bancarias de un grupo de clientes. Para ello utilizaremos una estructura con los siguientes campos:
- Nombre (hasta 25 caracteres).
- Usuario (hasta 25 caracteres).
- Contraseña (hasta 25 caracteres).
- DNI.
- Fecha de última actividad (en formato Unix epoch).
- Dinero en cuenta.

Se nos pide implementar un módulo capaz de agregar, eliminar (por usuario), realizar depósitos o extracciones de dinero, y mostrar el estado de cuenta. Las cuentas deberán ser almacenadas en un arreglo dinámico. Para ello se deberán implementar las siguientes funciones:

```c
typedef struct Cuenta
{
    /*Definir*/
} Cuenta;

// @brief Agrega una cuenta al vector de cuentas. Retorna EXITO o ERROR.
int cuentas_agregar(/*Definir*/ cuentas, /*Definir*/ cantidad_cuentas, /*Definir*/ cuenta);

// @brief Elimina una cuenta del vector de cuentas (por usuario). Retorna EXITO o ERROR.
int cuentas_eliminar(/*Definir*/ cuentas, /*Definir*/ cantidad_cuentas, /*Definir*/ usuario);

// @brief Realiza un depósito a una cuenta del vector de cuentas (por usuario). Retorna EXITO o ERROR.
int cuentas_deposito(/*Definir*/ cuentas, /*Definir*/ cantidad_cuentas, /*Definir*/ usuario, /*Definir*/ monto);

// @brief Realiza una extracción de una cuenta del vector de cuentas (por usuario). Retorna EXITO o ERROR.
// Nota: No se admiten valores negativos en las cuentas.
int cuentas_extraccion(/*Definir*/ cuentas, /*Definir*/ cantidad_cuentas, /*Definir*/ usuario, /*Definir*/ monto);

// @brief Imprime el estado de una cuenta en pantalla con el siguiente formato ejemplo:
//
// Banco Gringotts
// Nymphadora Tonks - @tonks
// DNI: 123456789
// 
// Saldo: 654321
// Última actividad: 14:12 - 10/04/98
void cuentas_imprimir(/*Definir*/ cuenta);

// @brief Imprime el contenido del vector de cuentas (reutilizar función anterior).
void cuentas_imprimir(/*Definir*/ cuentas, /*Definir*/ cantidad_cuentas);
```

Se pide también implementar un main que demuestre el correcto funcionamiento del módulo.


6. Automoviles - concesionaria

## Ejercicio 9.4
Definí una estructura de datos que permita representar a un automóvil. Un automóvil posee las siguientes características:
- numero_dominio: el número de patente.
- numero_motor: el número que trae grabado el motor.
- marca: la marca del automóvil.
- modelo: el modelo del automóvil.
- tamaño_motor: el número que indica la cilindrada del motor.
- color: el color de la carrocería.

Luego implementá las siguientes funciones para manipular dicha estructura:

```c
// @brief Genera una instancia de tipo Automóvil con valores de inicialización adecuados para cada uno de sus atributos.
Automovil automovil_crear();

// @brief Imprime los atributos del automóvil en pantalla.
void automovil_mostrar(Automovil automovil);

// @brief Cambia el color del automovil.
void automovil_cambiar_color(Automovil* automovil, /*Definir*/ color);
```

## Ejercicio 9.5
Escribir un programa que permita al usuario generar un vector de automóviles, los muestre ordenados según el número de dominio, permita modificar cualquiera de los atributos de un automóvil, ofrezca la posibilidad de agregar un
nuevo automóvil a la lista, de eliminar un automóvil a la lista, permita determinar cuál es el automóvil de mayor potencia presente en la lista.



























## Ejercicio 9.1
Implementá una función que reciba un ángulo expresado en radianes y lo devuelva en formato sexagesimal. Utilizá el siguiente prototipo:

```c
typedef struct AnguloSexagesimal
{
    int grados;
    int minutos;
    int segundos;
} AnguloSexagesimal;

AnguloSexagesimal a_sexagesimal(float angulo_en_radianes);
```

## Ejercicio 9.2
Definí una estructura de datos que permita representar el tiempo, es decir, horas, minutos y segundos.

Luego implementá las siguientes funciones para manipular dicha estructura:

```c
// @brief Genera un estructura del tipo Tiempo inicializado en 0 horas, 0 minutos y 0 segundos.
Tiempo tiempo_crear();

// @brief Imprime la hora en el formato "hh:mm:ss" en pantalla.
void tiempo_mostrar(Tiempo tiempo);

// @brief Recibe las horas minutos y segundos como argumentos y setea los valores en los campos de la estructura.
void tiempo_set(Tiempo* tiempo, int horas, int minutos, int segundos);
```

## Ejercicio 9.3
Definí una estructura de datos que permita representar una fecha, es decir, día, mes y año.

Luego implementá las siguientes funciones para manipular dicha estructura:

```c
// @brief Genera un estructura del tipo Fecha a partir de la fecha indicada.
Fecha fecha_crear(int dia, int mes, int año);

// @brief Imprime la fecha en pantalla.
void fecha_mostrar(Fecha fecha);

// @brief Aumenta la fecha en un día.
void fecha_incrementar_dia(Fecha* fecha);

// @brief Disminuye la fecha en un día.
void fecha_decrementar_dia(Fecha* fecha);
```






Ejercicio 7.21.
Implementar un Tipo de Dato “Vector” que incorpore en forma segura y
conveniente las funcionalidades de un arreglo estático estándar de punteros a
datos, utilizando memoria dinámica.

Ejercicio 7.22.
Se tienen la siguiente estructura:
struct datos {
long cod_art;
int cantidad;
char[26] descripción;
};
Escriba un programa que realice lo siguiente:
 Cargue datos en memoria, correspondientes a dicha estructura (fin de
datos: cod_art = 0)
 Ordene en forma creciente por cantidad, usando vector de punteros











Una estructura para manejar inventarios que contenga un campo para la descripción del producto (máximo 30 caracteres), un número para el número de parte en el inventario, un punto flotante para el precio, un entero para la cantidad que hay en el almacén y un entero para el lugar donde se almacena.

Una para manejar una dirección física que contiene arreglos para el país (máximo 40 caracteres), la provincia (máximo 30 caracteres), la ciudad (máx. 20), la dirección (máx. 30) y el código postal (10).

Una persona, con un arreglo para el nombre, otro para el apellido y una estructura como la del inciso anterior.

Una estructura, registro, que nos sirva para mantener un registro de los consumos de un vehículo, como en el último ejercicio de la guía 1. Para ello, debe contener un número para almacenar una cantidad de kilómetros, un número real para almacenar el costo del combustible, un número real para almacenar el dinero utilizado en una recarga, un time_t para almacenar la fecha, un booleano para indicar si se llenó el tanque y un arreglo para almacenar algún comentario.

Definí una estructura punto que contenga las coordenadas de un punto en .

Definí un nuevo tipo utilizando la definición de la estructura punto.

Implementá una función que reciba dos estructuras punto y calcule la distancia euclídea entre ambos puntos. Recuerde que la distancia euclídea es

donde  para .

Implementá la función del inciso c ¡pero validá!







9.3. Ejercicio 3
Nos piden desarrollar el m ́odulo de login de una aplicaci ́on de streaming. Dicho m ́odulo consiste en el
desarrollo de un arreglo est ́atico de estructuras para manejar la informaci ́on de los clientes. Cada cliente
tendr ́a su informaci ́on contenida en una estructura, la cual consistir ́a en “usuario”, “contrase ̃na”, y
“fecha de  ́ultimo login”. El m ́odulo debe ser capaz de agregar, eliminar, ordenar (por hora de  ́ultimo
login), e imprimir usuarios. El arreglo tendr ́a un m ́aximo de 10 clientes, luego de alcanzada dicha
cantidad, no se podr ́a agregar ning ́un nuevo cliente, debiendo imprimirse un mensaje de error por
pantalla.








## Referencias
Algunos ejercicios fueron obtenidos y adaptados de:
- Guía de Trabajos Prácticos 2011 - Informática I - Departamento de Electrónica - UTN FRBA
- Guía de Ejercicios - Algoritmos y Programación I - UBA FIUBA
