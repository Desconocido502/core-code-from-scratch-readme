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

# **Tuesday** 19-04-2022

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
  <li>Metodo split: Se usa para dividir cadenas de texto, basándose en un separador dado como argumento, y devuelve un Array con los elementos separados.</li>
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
<p align="justify">Haciendo una prueba se obtiene lo siguiente:</p>

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
  return String.fromCharCode(c);
}
```

<p align="justify">Haciendo una prueba se obtiene lo siguiente:</p>

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

<p align="justify">Haciendo una prueba se obtiene lo siguiente:</p>

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

Función a completar:

```javascript
function finalGrade (exam, projects) {
  return // final grade
}
```

<p align="justify">En base a los dos argumentos (exam, projects), que se le dan a la función, se nos solicita que devuelva un número (calificación final), en base a los cuatro tipos de calificaciones finales.</p>

En este método no fue necesario implementar métodos propios de JS.

Se tienen las cuatro opciones:

<ul>
  <li>Se da calificación de 100, si la calificación del examen es mayor a 90 <strong>o</strong> si la cantidad de proyectos terminados es mayor a 10.</li>
  <li>Se da calificación de 90, si la calificación del examen es mayor a 75 <strong>y</strong> si la cantidad de proyectos terminados es como mínimo 5.</li>
  <li>Se da calificación de 75, si la calificación del examen es mayor a 50 <strong>y</strong> si la cantidad de proyectos terminados es como mínimo 2.</li>
  <li>Se da calificación de 0, en cualquier otro caso.</li>
</ul>

Obteniendo así, la siguiente función.

```javascript
function finalGrade (exam, projects) {
  let calificacion_final = 0
  if (exam > 90 || projects > 10) {
      calificacion_final =  100
  }else if (exam > 75 && projects >= 5) {
      calificacion_final = 90
  }else if (exam > 50 && projects >= 2) {
      calificacion_final = 75
  }
  return calificacion_final// final grade
}
```

<p align="justify">Haciendo una prueba se obtiene lo siguiente:</p>

```javascript
finalGrade(85,5)
```

<p>Obteniendo como respuesta: <strong>90</strong></p>

# **Wednesday** 20-04-2022

## Holiday VIII - Duty Free exercise

<p align="justify">The purpose of this kata is to work out just how many bottles of duty free whiskey you would have to buy such that the saving over the normal high street price would effectively cover the cost of your holiday.</p>
<p align="justify">You will be given the high street price (normPrice), the duty free discount (discount) and the cost of the holiday.</p>
<p align="justify">For example, if a bottle cost £10 normally and the discount in duty free was 10%, you would save £1 per bottle. If your holiday cost £500, the answer you should return would be 500.</p>
<p align="justify">All inputs will be integers. Please return an integer. Round down.</p>

Función a completar

```javascript
function dutyFree(normPrice, discount, hol){

}
```

<p align="justify">Se nos solicita que a partir de tres valores (precio de venta, descuento sin impuestos, costo de vacaciones), obtengamos el calculo de cuántas botellas de whisky libre de impuesto se pueden comprar. Para ello evaluamos la situación.</p>

<p align="justify">Lo primero es entender que nos solicitan, y lo que se solicita es el calculo de ¿cuántas botellas de whisky se pueden compar?</p>
<p align="justify">¿Con que lo calculamos?, Se calcula con los datos ingresados, que son:</p>
<ul>
	<li>precio de venta</li>
	<li>descuento sin impuestos</li>
	<li>costo de vacaciones</li>
</ul>

<p>¿Cómo lo calculamos?</p> 
<ul>
	<li>Lo primero que se hace, es convertir el valor del impuesto en un porcentaje, se hace dividiendo el descuento sin impuestos dentro de 100.</li>
	<li>Luego se multiplica el porcentaje obtenido con el precio de venta  de la botella de whisky.</li>
	<li>Por último, el costo de las vacaciones se divide dentro de la multiplicación obtenida anteriormente. </li>
</ul>

<p align="justify">Así obteniendo, la siguiente función:</p>

```javascript
function dutyFree(normPrice, discount, hol){
  //hol/(normPrice*discount)
  return Math.floor(hol/(normPrice*(discount/100)));
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
dutyFree(24,35,3000)
```

<p>Obteniendo como respuesta: <strong>357</strong></p>

## Twice As Old exercise

Your function takes two arguments:

<ol>
	<li>current father's age (years)</li>
	<li>current age of his son (years)</li>
</ol>

<p align="justify">Сalculate how many years ago the father was twice as old as his son (or in how many years he will be twice as old).</p>

<p align="justify">Se nos solicita, a partir de dos argumentos (edad actual del padre, edad actual del hijo), obtener el valor de hace ¿cuántos años el padre tenía el doble de la edad del hijo?.</p>

Función a completar:

```javascript
function twiceAsOld(dadYearsOld, sonYearsOld) {
  // your code here
}
```

<p align="justify">¿Qué hay que calcular?, Hace cuantos años el padre tenia el doble de la edad que su hijo o dentro de cuantos años el padre tendrá el doble de la edad de su hijo.</p>

<ol>
	<li>Lo primero que se tiene que hacer es, multiplicar la edad del hijo por dos.</li>
	<li>Lo siguiente que se tendría que hacer es restar la edad del padre con el doble de la edad del hijo.</li>
</ol>

<p align="justify">Con esto, se obtiene la siguiente función:</p>

```javascript
function twiceAsOld(dadYearsOld, sonYearsOld) {
  return Math.abs(dadYearsOld-(sonYearsOld*2))
}
```

<p align="justify">Se hace uso del método abs, ya que, como lo indica el enunciado, hace cuantos años el padre tenia el doble de la edad que su hijo <strong>O</strong> dentro de cuantos años el padre tendrá el doble de la edad de su hijo.</p>

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
twiceAsOld(36,7)
```

<p>Obteniendo como respuesta: <strong>22</strong></p>

## Valid Spacing exercise

<p align="justify">Your task is to write a function called valid_spacing() or validSpacing() which checks if a string has valid spacing. The function should return either true or false (or the corresponding value in each language).</p>
<p align="justify">For this kata, the definition of valid spacing is one space between words, and no leading or trailing spaces. Words can be any consecutive sequence of non space characters. Below are some examples of what the function should return:</p>

Función a completar:

```javascript
function validSpacing(s) {
  // write your code here
}
```

<p align="justify">Se nos solicita, a partir de una cadena como argumento, que se verifique si una cadena tiene un espacio válido. La función debe devolver un true en caso de que la cadena sea válida con sus espaciados y false en caso de que la cadena no sea válida con sus espaciados. Para que la cadena sea válida, se tienen las siguientes validaciones:</p>

<ol>
	<li>No lleva espacios al inicio de la cadena</li>
	<li>No lleva espacios al final de la cadena</li>
	<li>Puede ser cualquier secuencia consecuiva de caracteres sin espacio</li>
	<li>No puede haber mas de un espacio por cada palabra en la cadena</li>
	<li>Si la cadena esta vacía es válida</li>
</ol>

<p align="justify">Tomando en consideración todo lo anterior, se realizan los pasos siguientesÑ</p>

<ul>
	<li>Si la cadena al inicio o al final tiene un espacio vacío retorna false</li>
	<li>Sino, se tendra que hacer un for que recorra la cadena</li>
	<li>Dentro del for verificar que no exista un espacio seguido de otro, si es así se retorna false</li>
	<li>En caso de que dentro del for no se encuentre un espacio seguido de otro, se retorna true</li>
</ul>

Obteniendo la siguiente función:

```javascript
function validSpacing(s) {
  if (s[0] === ' ' || s[s.length-1] === ' ') {
      return false;
  }else{
      for (var i = 0; i < s.length; i++) {
           if (s[i] === ' ' && s[i+1] === ' ') return false;
      }
      return true;
  }
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
validSpacing('Hello  world')
```

<p>Obteniendo como respuesta: <strong>false</strong></p>

## Fake Binary exercise

<p align="justify">Given a string of digits, you should replace any digit below 5 with '0' and any digit 5 and above with '1'. Return the resulting string.</p>
<p align="justify">Note: input will never be an empty string.</p>

Función a completar:

```javascript
function fakeBin(x){
}
```

<p align="justify">A partir de una cadena de digitos como argumento de la función, se nos pide retornar una cadena de 1´s y 0´s.</p>
<p align="justify">Cualquier digito que sea menor a 5 se le dará el valor de '0' en caso de que sea mayor o igual a 5 se le dará el valor de '1'.</p>

<p align="justify">Tomando en cuenta las validaciones anteriores, se obtiene la siguiente funcion:</p>

```javascript
function fakeBin(x){
    let falso_binario = ""
    for (var i = 0; i < x.length; i++) {
        if (x[i] < '5') {
            falso_binario += '0'
        }else{
            falso_binario += '1'
        }
    }
    return falso_binario
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(fakeBin('45385593107843568'))
```

<p>Obteniendo como respuesta: <strong>01011110001100111</strong></p>

# Thursday 21-04-2022

## Remove All Exclamation Marks From The End Of Sentence exercise

<p align="justify">Remove all exclamation marks from the end of sentence.</p>

Función a completar:

```javascript
function remove (string) {  
  return '';
}
```

<p align="justify">A partir de una cadena pasada como argumento, se tienen que eliminar los signos de exclamación</p>
<p align="justify">Para esto, se utilizará un método propio JS.</p>

<ul>
	<li>Método subString: Devuelve la parte de un string ente los índice inicial y final, o al final de la cadena.</li>
</ul>

<!-- ![pikachu triste](https://www.levelup.com/core/scripts/image_proxy.php?img=https://media.giphy.com/media/7SF5scGB2AFrgsXP63/giphy.gif) -->

<p align="justify">Para resolver el problema, se hace uso de una bandera, un while, un if y de un método propio de JS.</p>
<Ol>
	<li>Primero, se declara una bandera que es un booleano con un valor verdadero(true)</li>
	<li>Luego, se crea el while, dentro del while se trabaja se pregunta por lo que hay en la última posición</li>
	<li>Si el valor en la última posición es igual a un signo de admiración(!), entra al if.</li>
	<li>Dentro del if, a la misma cadena se le asigna una nueva cadena, osea una cadena que se le quita el signo de admiración del final de la cadena.</li>
	<li>En caso de que no exista un signo de admiración al final de la cadena se irá al else, donde se le asigna a bandera un valor false, esto sirve para salir del bucle while.</li>
</Ol>

<p align="justify">Obteniendo así, la función completada: </p>

```javascript
function remove (string) {
    bandera = true
    while (bandera){
        if (string[string.length -1] === "!"){
            string = string.substring(0,(string.length-1))
        }else{
            bandera = false
        }
    }
    return string
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(remove("!hi!!!"))
```

<p>Obteniendo como respuesta: <strong>"!Hi"</strong></p>

## Vowel Remover exercise

<p align="justify">Create a function called shortcut to remove the lowercase vowels (a, e, i, o, u ) in a given string.</p>

Función a completar:

```javascript
function shortcut (string) {
  return '';
}
```

<p align="justify">A partir de una cadena como argumento, se nos solicita eliminar todas las vocales minusculas de la cadena, y retornar la cadena.</p>

<ul>
	<li>Lo primero a entender es que se nos pide, Devolver una cadena sin vocales minúsculas</li>
	<li>¿Cómo lo hacemos?, Se hará con un if y un for</li>
	<li>¿Cómo lo haremos?, Bien para esto, se tiene que tomar la cadena, y recorrerla con el for.</li>
	<li>Dentro del for preguntar con un if, si la cadena en la i-ésima posición es diferente a la vocal "a", o si es diferente a la vocal "e", o si es diferente a la vocal "i", o si es diferente a la vocal "o", o si es diferente a la vocal "u"</li>
	<li>En caso de que sea cierto, se concatena el carácter en la i-ésima posicón a una nueva variable.</li>
	<li>Al final de todo se retorna el valor de la nueva variable.</li>
</ul>

<p align="justify">Obteniendo así, la función completa: </p>

```javascript
function shortcut (string) {
    let str = ""
    for (var i = 0; i < string.length; i++) {
        if (string[i] !== "a" && string[i] !== "e" && string[i] !== "i" && string[i] !== "o" && string[i] !== "u" ) {
            str += string[i]
        }
    }
    return str
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(shortcut("goodbye"))
```

<p>Obteniendo como respuesta: <strong>'gdby'</strong></p>


## Rock Paper Scissors! exercise

<p align="justify">Let's play! You have to return which player won! In case of a draw return Draw!.</p>
<p align="center">
	<img src="https://i.pinimg.com/originals/dd/a1/4c/dda14ccfabbff7efcded1b2ec971d863.gif" alt="piedra, papel o tijeras!!!" style="width:200px;"/>
</p>
<p align="justify">Se tiene que realizar el juego de piedra, papel y tijeras!!!, a partir de dos valores como argumentos.</p>
<p align="justify">Las reglas siguen siendo las mismas, las cuales son las siguientes.</p>

<ul>
	<li>Si un jugador saca tijeras y otro jugador saca piedra, la piedra le quita el filo a las tijeras, la piedra gana!</li>
	<li>Si un jugador saca tijeras y otro jugador saca papel, la tijera corta el papel, la tijera gana!</li>
	<li>Si un jugador saca papel y otro jugador saca piedra, el papel envuelve la piedra, el papel gana!</li>
	<li>Si ambos jugadores sacan el mismo objeto, hay un empate.</li>
</ul>

<p align="justify">Siguien las reglas anteriores, es como se programará la función, solo que con la diferencia de que cuando ambos jugadores, saquen el mismo objeto, se dira Draw!, se hará uso de la estructura de control if-else if-else.</p>

Función completada:

```javascript
const rps = (p1, p2) => {
    let response = ""
    if(p1 === "scissors" && p2 === "paper"){
        response = "Player 1 won!"
    }else if(p1 === "scissors" && p2 === "rock"){
        response = "Player 2 won!"
    }else if(p1 === "paper" && p2 === "rock"){
        response = "Player 1 won!"
    }else if(p1 === "paper" && p2 === "scissors"){
        response = "Player 2 won!"
    }else if(p1 === "rock" && p2 === "scissors"){
        response = "Player 1 won!"
    }else if(p1 === "rock" && p2 === "paper"){
        response = "Player 2 won!"
    }else{
        response = "Draw!"
    }
    return response
};
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(rps('scissors','paper'));
```

<p>Obteniendo como respuesta: <strong>'Player 1 won!'</strong></p>

## Persistent Bugger exercise

<p align="justify">Write a function, persistence, that takes in a positive parameter num and returns its multiplicative persistence, which is the number of times you must multiply the digits in num until you reach a single digit.</p>

<p align="justify">For example (Input --> Output):</p>

Función a completar:
```javascript
function persistence(num) {
   //code me
}
```

<p align="justify">Se nos dice que a partir de un parametro, se devuelva su persistencia multiplativa, osea la <strong>cantidad</strong> de veces que se debe de multiplicar los dígitos hasta que solo se llegue a un dígito.</p>

<p align="justify">Se tiene que tomar el número, transformarlo a un string, dentro de un while volverlo un arreglo de caracteres, y con un for multiplicar por cada posición que existe en el arreglo y almacenarlo en una variable, a la variable que almacenaba al numero inicialmente asignarle el valor de la nueva variable, a final, se aumenta el valor de un contador en 1. Al final del proceso retornar el valor del contador.</p>


Función completada:
```javascript
function persistence(num) {
   if (num < 0) num = Math.abs(num);
   let count = 0;
   num = ''+num;
   while(num.length !== 1){
       num = ''+num;
       num = num.split('');
       let num2 = 1;
       
       for (var i = 0; i < num.length; i++) {
           num2 = parseInt(num[i]) * num2;
       }
       num = ''+num2
       count +=1;
   }
   return count
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(persistence(999));
```

<p>Obteniendo como respuesta: <strong>4</strong></p>

# Monday 25-04-2022

## Who likes it? exercise

<p align="jsutify">You probably know the "like" system from Facebook and other pages. People can "like" blog posts, pictures or other items. We want to create the text that should be displayed next to such an item.</p>

<p align="jsutify">Implement the function which takes an array containing the names of people that like an item. It must return the display text as shown in the examples:</p>

<p align="justify">Se nos solicita que a partir de un argumento(en este caso un arreglo), Se debe devolver un texto a la pantalla.</p>
<p align="jsutify">Esto se realizará haciendo uso de las template Strings, estas son usadas para que la respuesta de un texto sea más dinámico.</p>
<p align="jsutify">Se poseen 4 casos, los cuales los abarcaremos con la estructura if-else.</p>

<ul>
	<li>El caso donde no venga nada en el arreglo, se retorna como respuesta: "no one likes this"</li>
	<li>El caso donde viene un elemento en el arreglo, se retorna como respuesta: El primer elemento + "likes this"</li>
	<li>El caso donde viene dos elementos en el arreglo, se retorna como respuesta:El primer elemento + "and" + segundo elemento + "like this"</li>
	<li>El caso donde viene tres elementos en el arreglo, se retorna como respuesta:El primer elemento + "," + segundo elemento + "and" Tercer elemento + "like this"</li>
	<li>El caso donde viene mas o igual a cuatro elementos en el arreglo, se retorna como respuesta: El primer elemento + "," + segundo elemento + "and" + el largo del arreglo menos dosd + "others likes this"</li>
</ul>

En la parte de arriba lo trabajamos con comillas dobles, pero en la siguiente función ya se hace uso de las plantillas literales:
```javascript
function likes(names) {
  
  if(names.length == 0){
      return "no one likes this"
  }
  else if(names.length == 1){
      return `${names[0]} likes this`
  }else if(names.length == 2){
      return `${names[0]} and ${names[1]} like this`
  }else if(names.length == 3){
      return `${names[0]}, ${names[1]} and ${names[2]} likes this`
  }else{
      return `${names[0]}, ${names[1]} and ${names.length-2} others likes this`
  }
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(likes(["Alex", "Jacob", "Mark", "Max"]));
```

<p>Obteniendo como respuesta: <strong>'Alex, Jacob and 2 others likes this'</strong></p>

## Bit Counting exercise

<p align="justify">Write a function that takes an integer as input, and returns the number of bits that are equal to one in the binary representation of that number. You can guarantee that input is non-negative.</p>


<p align="justify">Example: The binary representation of 1234 is 10011010010, so the function should return 5 in this case</p>


<p align="justify">Se nos solicita que a partir de un número entero como argumento, devuelva el número de bits del numero entero.</p>
<p align="justify">En otras palabras, al momento de ingresar el número, se necesita que se retorne la suma de los digitos del número, pero el número se tiene que convertir primero a binario, luego de esto ya se pueden sumar cada uno de los digitos, retornar la suma</p>

<p align="justify">Explicando paso a paso, se tiene:</p>
<ol>
	<li>Primero se convierte el número en binario usando toString, y luego se separa y se vuelve un arreglo de Strings, usando split.</li>
	<li>Luego, se hara uso del método reduce, la cual viene siendo una función reductora, sobre cada elemento de un arreglo. Devuelve un solo valor.</li>
	<li>Por último, retornamos el valor dado.</li>
</ol>

Obteniendo asi, la siguiente función:

```javascript
var countBits = function(n) {
    
    if(n < 0) n = Math.abs(n)
    
    n = n.toString(2).split("")
    return n.reduce((pv,cv) => parseInt(pv) + parseInt(cv),0);
};
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(countBits(1234))
```

<p>Obteniendo como respuesta: <strong>5</strong></p>

## Your Order, Please exercise

<p align="justify">Your task is to sort a given string. Each word in the string will contain a single number. This number is the position the word should have in the result.</p>
<p align="justify">Note: Numbers can be from 1 to 9. So 1 will be the first word (not 0).</p>
<p align="justify">If the input string is empty, return an empty string. The words in the input String will only contain valid consecutive numbers.</p>

Función a completar:

```javascript
function order(words){
  // ...
}
```

<p align="justify">A partir de una entrada (cadena), se solicita que se ordene la cadena, en la cadena vienen palabras con un numero entre las palabras, estos números van del 1 al 9, de manera consecutiva, si la cadena viene vacia, se retorna una cadena vacia, Los pasos para realizar el algoritmo es el siguiente:</p>

<ol>
	<li>Se separa la cadena usando split, el elemento separador es un espacio, se obtiene un arreglo de Strings.</li>
	<li>Se recorre el arreglo de Strings, por cada elemento del arreglo se busca un número.</li>
	<li>Si el numero existe dentro de la cadena, se extrae el número y se arregla en un arreglo de enteros.</li>
	<li>Al terminar de recorrer el arreglo de Strings, se procede a ordenar con el método sort.</li>
	<li>Luego, se debe de recorrer el arreglo de enteros junto con el arreglo de Strings.</li>
	<li>Revisando si el elemento entero aparece en el elemento del arreglo de Strings, en el caso de aparecer, se almacena en otro arreglo.</li>
	<li>Al final, el arreglo nuevo, contiene las cadenas de Strings ordenadas, como último paso, se usa el método join para unir las cadenas.</li>
</ol>

Obteniendo así la siguiente función:
```javascript
function order(words){
  
  if(words == "") return ""
  
  enteros = []
  words = words.split(" ")
  for (let i = 0; i < words.length; i++) {
      cadena = words[i]
      for (let j = 0; j < cadena.length; j++) {
          switch (cadena[j]) {
              case '1':
                  enteros.push(Number(cadena[j]));
                  break;
              case '2':
                 enteros.push(Number(cadena[j]));
                  break;
              case '3':
                  enteros.push(Number(cadena[j]));
                  break;
              case '4':
                  enteros.push(Number(cadena[j]));
                  break;
              case '5':
                  enteros.push(Number(cadena[j]));
                  break;
              case '6':
                  enteros.push(Number(cadena[j]));
                  break;
              case '7':
                  enteros.push(Number(cadena[j]));
                  break;
              case '8':
                  enteros.push(Number(cadena[j]));
                  break;
              case '9':
                  enteros.push(Number(cadena[j]));
                  break;
          }
      }
  }
  enteros.sort();
  words2 = []
  for (let i = 0; i < enteros.length; i++) {
      entero_str = ""+enteros[i]
      for (var j = 0; j < words.length; j++) {
          if(words[j].includes(entero_str)){
              words2.push(words[j])
          }
      }
  }
  words2 = words2.join(" ")
  return words2
  
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(order("4of Fo1r pe6ople g3ood th5e the2"));
```

<p>Obteniendo como respuesta: <strong>'Fo1r the2 g3ood 4of th5e pe6ople'</strong></p>

	
<p align="justify"></p>
<p align="justify"></p>
<p align="justify"></p>
<p align="justify"></p>













