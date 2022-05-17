# **Tuesday** 19-04-2022

<ul>
  <li><a href='#multiply'><strong>Multiply exercise</strong></a></li>
  <li><a href='#ascii'><strong>ASCII Total exercise</strong></a></li>
  <li><a href='#char-ascii'><strong>Char From ASCII Value exercise</strong></a></li>
  <li><a href='#binary'><strong>Binary Addition exercise</strong></a></li>
  <li><a href='#final-grade'><strong>Student's Final Grade exercise</strong></a></li>
</ul>


<a name='multiply'></a>

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

<a name='ascii'></a>

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

<a name='char-ascii'></a>

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

<a name='binary'></a>

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

<a name='final-grade'></a>

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
<a href="../README.md">Inicio</a>