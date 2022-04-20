# core-code-from-scratch-readme

# **Tuesday**

## Interpreted And Compiled Programming Languages

<p align='justify'>Los lenguajes interpretados y compilados sirven para procesar código de alto nivel y pasarlo a bajo nivel para que lo procese la computadora, que entiende 1´s y 0´s.</p>

### Lenguajes Compilados:
<p align='justify'>Los lenguajes compilados analiza un programa y lo traduce al lenguaje máquina, esto como ejemplo es decir tener un traductor humano, que toma nota de lo que está escuchando y reproduce por escrito en otra lengua, el ejemplo que habla en la lectura es de una receta escrita en griego, un "traductor", lee o escucha la lengua griega y lo puede empezar a escribir en inglés o cualquier otro idioma que le interese, esto cumple con lo mencionado antes, que el "traductor" toma nota y lo pasa a otro idioma.</p>

### Lenguajes Interpretados:
<p align="justify">Los lenguajes interpretados analizan un programa linea a linea y se corre directamente, si se sigue con el ejemplo del "traductor humano" el traductor como tal escucha lo que se esta hablando en griego y en ese mismo tiempo el puede ir traduciendo en la marcha, sin necesidad de tomar nota. En el ejemplo de la receta griega, el podría escuchar a la persona hablar en griego y traducir al idioma que se necesite en este caso como ejemplo "ingles".</p>

<p align="justify">Algunas ventajas y desventajas que se tienen, y siguiendo con el ejemplo de la receta griega es:</p>

### Compilado: 
<p align="justify">El traductor toma nota y esa información se coloca en un libro, pero si el creador de la receta decide cambiar algún ingrediente, el traductor tendría, que volver a tomar nota y colocar la información en un libro nuevo. Esto significa que tendriamos que "reconstruir" el programa cada vez que exista un cambio.</p>

<p align="center"> <img src="https://cdn.pixabay.com/photo/2021/09/17/01/07/man-6631394__340.png" alt="traductor tomando nota" width="240" height="180" /> </p>

### Interpretado:
<p align="justify">El traductor no toma nota, ya que va traduciendo en la marcha y si el creador de la receta decide cambiar algún ingrediente, el traductor cambia en ese momento al nuevo ingrediente que agrego el creador de la receta, y no tendría que reconstruir todo lo que se habia traducido anteriormente mas que el nuevo ingrediente.</p>

<p align="center"> <img src="https://cdn.pixabay.com/photo/2018/04/16/10/13/translate-3324171__340.jpg" width="240" height="180"/></p>

<p align="justify">Una ventaja para los lenguajes compilados y desventaja para los lenguajes interpretados es su tiempo de ejecución. En primera instancia uno pensaría que un lenguaje compilado tendria que ser más lento ya que es más robusto comparado con un lenguje interpretado que es más liviano, pero no es así, esto se debe a la carga de datos que tiene que analizar el interprete en tiempo de ejecución  y ralentiza el programa, y esto se debe a que el análisis que realiza, lo hace línea por línea, y cada línea (que es una instrucción) se puede llegar a analizar muchas veces.</p>

<p align="justify">Existen un tipo más de traducir un lenguaje de alto nivel a bajo nivel y este se le denomina lenguaje intermedio, lo que hace es tomar un poco de compilador y otro poco de interprete, los une, y esto lo hace hasta donde llega el código máquina sin dejar de ser portátil (para llevarlo a otras plataformas). Este archivo en ese punto se puede mandar a otras personas para que realicen el último paso de ejecución para que puedan ver el programa en sus computadoras.</p>

## Ejemplos de lenguajes compilados, interpretados e Hibridos:

|Compilados|Interpretados|Híbridos|
|----------|-------------|--------|
|    C     | JavaScript  |  Java  |
|    C++   |    PHP      | Python |
|    Go    | ----------- |   C#   |

## Is Java compiled or interpreted, or both?

<p align="justify">Java es tanto lenguaje compilado como lenguaje interpretado ya que Java cuenta con un entorno de ejecución que lee el lenguaje compilado (ByteCode) y que luego es interpretado por la Java Virtual Machine(JVM). El interprete con que cuenta Java es diferente a cualquier otro, ya que lo que interpreta es el código de bytes, y no un código de lenguaje máquina. Tambíen según el entorno el código de bytes, puede ser compilado con anticipación, compilado justo a tiempo, interpretado o ser ejecutado directamente por un procesador compatible.</p>

## Pseudocode Currency Converter exercise
```
Inicio
  variables: valorEntrada, valorSalida Entero;
  Mostrar: "Conversor de dólares(USD) a bitcoin(BTC)";
  Mostrar: "Ingrese la cantidad de dólares a convertir:";
  Leer: valorEntrada;
  Ejecutar: valorSalida = (valorEntrada) * (0.000022);
  Imprimir: "Los"+valorEntrada+"dólares en Bitcoin son: "+valorSalida+" BTC"
Fin
```
## Learn about High and Low level languajes

<p align="justify">Los lenguajes de alto nivel, permiten que una persona pueda programar con una sintaxis parecida a la de los humanos, osea que abstrae todo el proceso de traducir el programa y deja que la persona escriba su programa con una sintaxis parecida a la de los humanos.</p>

<p align="justify">Los lenguajes de bajo nivel, son los que contienen menos abstracción, y que son más cercanos al lenguaje máquina.</p>

# **Wednesday**

## Your date of birth in the matrix? exercise

<p align="justify">
    Mi fecha y año de nacimiento -> 2000, 08-06-2000
    <br/>Año -->2000
</p>

<p align="justify">Metodo 1: Se calculan las potencias de base 2 hasta que uno de los valores de la lista de potencias de base 2 sea mayor al numero que deseamos encontrar el numero binario.</p>

<p align="justify">Paso 1: Se calcula la potencia de base 2 mientras sean menores al numero que se desea calcular su valor binario (2000 > 1024 ✔)</p>

|2^11|2^10|2^9|2^8|2^7|2^6|2^5|2^4|2^3|2^2|2^1|2^0|
|----|----|---|---|---|---|---|---|---|---|---|---|
|2048|1024|512|256|128|64 |32 | 16| 8 | 4 | 2 | 1 |

<p align="justify">Paso 2: Se resta el numero a pasar a binario, con el ultimo valor de la potencia de base 2 calculado.</p>

2000 - 1024 = 976.
<p align="justify">Paso 3: El resultado obtenido de la resta, se compara con cada uno de los valores de la lista de potencia de base 2, y cuando se encuentre el numero mas alto que este por debajo del resultado, se le vuelve a restar. y asi sucesivamente.</p>

<p align="justify">2000 -> 1024 + 512 + 256 + 128 + 64 + 8 + 4 + 2 + 1 + 1 = 2000</p>

<p align="justify">2000 - 1024 = 976, resultado = 976, 976 >= 1024 X, 976 >= 512 ✔  
976 - 512 = 464, resultado = 464, 464 >= 512 X, 464 >= 256 ✔<br/>   
464 - 256 = 208, resultado = 208, 208 >= 256 X, 208 >= 128 ✔<br/>  
208 - 128 = 80, resultado = 80, 80 >= 128 X, 80 >= 64 ✔<br/>         
80 - 64 = 16, resultado = 16, 16 >= 64 X, 16 >= 32 X, 16 >= 16 ✔<br/>
16 - 16 = 0, resultado = 0 ✔<br/>
Fin</p>

<p align="justify">Paso 4: A los numeros binarios que si se usaron, se les da el valor de 1, y a los que no el valor de 0. Quedando asi en la lista:</p>

| 2040| 1024 | 512 | 256 | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
|-----|------|-----|-----|-----|----|----|----|---|---|---|---|
|-----|  1   |  1  |  1  |  1  |  1 | 0  |  1 | 0 | 0 | 0 | 0 |

<p align="justify">Obteniendo asi el numero binario de mi fecha de cumpleaños (2000) en binario: <strong>11111010000</strong>.</p>

## MIPS
### 1.Create a program that adds any two given numbers provided by the user.

<p align="justify">Crearemos el programa en MIPS, que lee dos numeros ingresados por el usuario, y nos devolvera la suma de ambos valores.</p>

```MIPS
.data   # ->Aqui se almacenan los valores adicionales, se almacenan tres cadenas que nos serviran para la lectura del user.
	      val1: .asciiz "\nIngrese el primer valor: "
	      val2: .asciiz "\nIngrese el segundo valor: "
	      result_m: .asciiz "\n El resultado de la suma es: "
.text  # -> Aqui se coloca toda la parte del codigo a procesar
    main: # -> Aqui es el punto de inicio del programa
        li $v0, 4       # -> Se le dice a la computadora que estamos a punto de imprimir un valor
        la $a0, val1    # -> Se esta cargando la mezcla deseada para imprimir, siempre va despues de decirle a la computadora que vamos a imprimir
        syscall         # -> Se llama al sistema para que imprime la cadena seleccionada en este caso la cadena val1

        li $v0, 5       # -> Se prepara para recibir una entrada.
        syscall         # -> El sistema procesa la entrada (Lee la entrada del usuario)

        move $t0, $v0   # -> Se mueve el valor de entrada del registro general a un registro "seguro" que es para almacenamiento de valores
        
        # -> Se realiza lo mismo que en los pasos anteriores.
        li $v0, 4
        la $a0, val2
        syscall

        li $v0, 5
        syscall

        move $t1, $v0   # -> Se mueve el valor de entrada del registro general a un registro nuevo, en este caso a $t1, ya que $t0. se encuentra ocupado

        add $t2, $t0, $t1  # -> Se suman los valores almacenados en $t0 y $t1, y se almacenan en $t2
        
        li $v0, 4          # -> Estamos a punto de imprimir un valor (de la cadena resul_m)
        la $a0, result_m   #Cargando la mezcla deseada a imprimir
        syscall            # -> Se llama al sistema para que muestre la impresión de la cadena
        
        li $v0, 1         # -> Se le dice a la computadora que se imprimirá un número
        move $a0, $t2     # -> Se le indica a la computadora donde esta el resultado de la suma, que se va a imprimir
        syscall           # -> Se llama al sistema para que imprima dicho valor
```

<p align="justify">Fin del programa que suma dos numeros dados por el usuario en MIPS, <br/>(Lenguaje de bajo nivel - Assembler)</p>

### 2.Create a program that displays your name.
<p align="justify">Crearemos el programa que imprime tu nombre en MIPS.</p>

```MIPS
.data	      # ->Aqui se almacenan los valores adicionales, se almacenan una cadena que nos servira para imprimir un nombre.
	      mi_nombre: .asciiz "\nHello!, my name is CARLOS, and I am learning MIPS!!!"
	      
.text       # -> Aqui se coloca toda la parte del codigo a procesar
        main:  # -> Aqui es el punto de inicio del programa
            li $v0, 4             # -> Se le dice a la computadora que estamos a punto de imprimir un valor
            la $a0, mi_nombre     # -> Se esta cargando la mezcla deseada para imprimir, siempre va despues de decirle a la computadora que vamos a imprimir
            syscall               # -> Se llama al sistema para que imprime la cadena seleccionada en este caso la cadena mi_nombre
```
<p align="justify">Fin del programa un nombre en una cadena en MIPS, <br/>(Lenguaje de bajo nivel - Assembler)</p><br/>

# **Thursday**

<p align="justify">1. In this exercise you must use an iterative flow control to be able to print all the even numbers in the range of numbers from 0 to 100. Remember that you should not print each number, you should use a flow control structure to perform the exercise.</p>

### Solución:
<p align="justify">Existe tres formas de realizar el ejercicio con un control de flujo iterativo, los cuales son for, while, do-while:</p>

## Con for
```javascript
for (let i = 1; i <= 100; i++) {
  if (i % 2 == 0) {
    console.log(i);
  }
}
```
## Con while
```javascript
let i = 1;
while (i <= 100){
  if((i % 2) == 0){
    console.log(i);
  }
  i +=1;
}
```

## Con do-while
```javascript
let i = 1;
do {
  if (i % 2 == 0) {
    console.log(i);
  }
  i += 1;
} while (i <= 100);
```
### 2, 4, 6, 8, 10, 12, 14, 16, 18, 20 ... ... ..., 80, 82, 84, 86, 88, 90, 92 ,94 ,96,98,100
<p align="justify"> 
Asi obteniendo el mismo resultado para las tres formas de obtener los numeros pares entre 0 y 100.
</p>

<p align="justify">2. The code shown below is not working in the right way, as a task you must find the error made by the developer who programmed this code and correct it, for this exercise you must explain what the error is and place the correct code.</p>

### Código con error
```javascript
var cond = false;

if ((cond = true)) {
  console.log('The cond variable is true');
} else {
  console.log('The cond variable is false');
}
```
<p align="justify">El error que contiene el código anterior es que esta asignando un valor verdadero en la condición de la sentencia if, esto se debería realizar antes de la sentencia if, ya que en la condicion de la sentencia if se debe de comparar valores, más no asignar, ya que al asignar en la condicional, se le dice a la variable cond que tome el valor de true(verdadero).</p>

<p align="justify">Para terminar de arreglar el problema que causó el programador, solo se tiene que colocar la variable cond en el condición de la sentencia if, quedando como lo siguiente:</p>

### Código sin error
```javascript
var cond = false;

if ((cond)) {
  console.log('The cond variable is true');
} else {
  console.log('The cond variable is false');
}
```
<p align="justify">3. You must create the code that follows the following logic, if the given number is 100, take this number as special and show the following message: "This is a special number!", but if the number is less than 1000, multiple of 10 and different from 100, you must show the following message: "This number is almost special". if none of the given conditions are met show the following message: "Just a regular number". Another developer was trying to program the logic, but apparently couldn't, you need to fix the code to work properly.</p>

## Código incompleto
```javascript
var n = 100;

if (n == 100) {
  console.log('This is a special number!');
}
if (n < 1000) {
  console.log('');
} else {
  console.log('Just a regular number');
}
if (n % 10 == 0) {
  console.log('This number is multiple of 10');
}
```
<p align="justify">Para resolver el problema de lógica, se tiene que entender que es lo que se solicita, para esto iremos paso a paso a lo solicitado.</p>
<ol>
    <li>Si el número es 100, se toma el número como especial, mostrando el mensaje: "Este es un número especial".</li>
    <li>Si el número es menor a 1000, y es múltiplo de 10 y diferente de 100, se muestra el mensaje: "Este número es casi especial".</li>
    <li>Sino cumplió con ninguna de las condiciones anteriores, simplemente muestra el mensaje: "Sólo un número regular".</li>
</ol>

<p align="justify">El error del desarrollador que estaba intentando desarrollar el código, fue no entender de manera correcta el uso de la sentencia if-else, ya que estaba tomando el 2do caso en 2 partes separadas y le falto agregar una condición más. En tal caso, al llevar la lectura correcta, se puede observar que en el segundo caso se encuentra un operador booleano '&&' de forma ímplicita en la oración, y agregando la última condición faltante, se obtuvo lo siguiente:</p>

```javascript
var n = 100;

if (n == 100) {
  console.log("This is a special number!");
} else if (n < 1000 && n % 10 == 0 && n != 100) {
  console.log("This number is almost special");
} else {
  console.log("Just a regular number");
}
```
<p align="justify">Así obteniendo la forma correcta de resolver el programa.</p>

# **Tuesday**

## Multiply
This code does not execute properly. Try to figure out why.
Función con error:
```javascript
function multiply(a, b){
  a * b
}
```
<p align="justify">Se nos dice que el código no se ejecuta correctamente, esto se debe a que, los valores si se multiplican, pero no se retorna el resultado de la multiplicación, para completar la funcion de forma correcta, se debe de colocar el return antes de la multiplicación asi el resultado de esa multiplicación, es la que se devolverá obteniendo el siguiente resultado:</p>

```javascript
function multiply(a, b){
  return a * b
}
```
## ASCII Total
<p align="justify">You'll be given a string, and have to return the sum of all characters as an int. The function should be able to handle all ASCII characters.</p>
Función a completar:

```javascript
function uniTotal (string) {
// total up dem unicodes!
}
```

<p align="justify">Se nos pide que retornemos la suma de todos los caracteres ASCII de una cadena como un valor entero, para esto haremos uso de varios metodos que nos provee JS.</p>

<ul>
  <li>Metodo split: Se usa para dividir cadenas de texto, basándose en un separador dado como argumento, y devolver un Array con los elementos separados.</li>
  <li>Metodo parseInt: Convierte (parsea) un argumento de tipo cadena y devuelve un entero en una especificada.</li>
  <li>charCodeAt: Devuelve el valor Unicode, osea código UTF-16.</li>
</ul>
<p align="justify">Asi, completanto la función se tiene: </p>

```javascript
function uniTotal (string) {
// total up dem unicodes!
  string = string.split('');
  let totalAscii = 0;
  for(var i = 0; i < string.length; i++){
      totalAscii += parseInt(string[i].charCodeAt(0));
  }
  return totalAscii;
}
```
<p align="justify">Haciendo una prueba se obtiene lo siguiente</p>

```javascript
uniTotal("Mary Had A Little Lamb")
```

<p>Obteniendo como respuesta: <strong>1873</strong></p>

## Char From ASCII Value

<p align="justify">Write a function get_char() / getChar() which takes a number and returns the corresponding ASCII char for that value.</p>
Función base:

```javascript
function getChar(c){
  // ...
}
```

<p align="justify">A partir de un número de entrada como argumento se nos pide que la función devuelva el carácter ASCII correspondiente al número de entrada. Para ello, se hace uso de un método que posee JS.</p>

<ul>
  <li>Metodo String.fromCharCode: Es un método estático, que nos devuelve una cadena a partir de una secuencia especificada de unidades de código UTF-8.</li>
</ul>

Así, completando la función se tiene:

```javascript
function getChar(c){
  // ...
  c = String.fromCharCode(c);
  return c
}
```

<p align="justify">Haciendo una prueba se obtiene lo siguiente</p>

```javascript
getChar(65)
```

<p>Obteniendo como respuesta: <strong>'A'</strong></p>


## Binary Addition

<p align="justify">Implement a function that adds two numbers together and returns their sum in binary. The conversion can be done before, or after the addition.</p>

```javascript
function addBinary(a,b) {
  ....
}
```

<p align="justify">Se nos pide que ingresados dos números se devuelva la suma de ambos en binario. Para tal caso, usaremos nuevamente un método provisto por JS.</p>

<ul>
  <li>Metodo toString: Devuelve una cadena que representa al objeto Number especificado, el objeto Number es un valor entero comprendido entre 2 y 36, que es la base  la que se esta buscando pasar el valor. </li>
</ul>

Así, completando la función se tiene:

```javascript
function addBinary(a,b) {
  return (a + b).toString(2)
}
```

<p align="justify">Haciendo una prueba se obtiene lo siguiente</p>

```javascript
addBinary(5,9)
```

<p>Obteniendo como respuesta: <strong>'1110'</strong></p>

## Student's Final Grade

<p align="justify">This function should take two arguments: exam - grade for exam (from 0 to 100); projects - number of completed projects (from 0 and above);</p>

<p align="justify">This function should return a number (final grade). There are four types of final grades:</p>

<ul>
  <li>100, if a grade for the exam is more than 90 or if a number of completed projects more than 10.</li>
  <li>90, if a grade for the exam is more than 75 and if a number of completed projects is minimum 5.</li>
  <li>75, if a grade for the exam is more than 50 and if a number of completed projects is minimum 2.</li>
  <li>0, in other cases</li>
</ul>









