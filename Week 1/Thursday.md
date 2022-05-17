# **Thursday** 14-05-22 :star:

<ul>
  <li><a href='#special-numbers'><strong>Print special numbers exercise</strong></a></li>
  <li><a href='#badcode-1'><strong>Bad Code exercise</strong></a></li>
  <li><a href='#badcode-2'><strong>Bad Code 2 exercise</strong></a></li>
  <li><strong>Follow Git Course - 75% completed</strong>
</ul>

<a name='special-numbers'></a> 

##Print special numbers :dolphin:

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

<a name='badcode-1'></a>

### Bad Code exercise :tiger2:

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

<a name='badcode-2'></a>

## Bad Code 2 exercise :snowman:

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
<a href="../README.md">Inicio</a>