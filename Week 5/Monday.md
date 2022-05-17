# Monday 09-05-2022

<ul>
    <li><a href='#find'><strong>Find The Missing Letter exercise</strong></a></li>
    <li><a href='#reverse'><strong>Reverse Or Rotate? exercise</strong></a></li>
</ul>

<a name="find"></a>

## Find The Missing Letter exercise

<p align="justify">
Write a method that takes an array of consecutive (increasing) letters as input and that returns the missing letter in the array.
</p>
<p align="justify">
You will always get an valid array. And it will be always exactly one letter be missing. The length of the array will always be at least 2.
The array will always contain letters in only one case.</p>

Example:

['a','b','c','d','f'] -> 'e' ['O','Q','R','S'] -> 'P'

<p align="justify">Se nos solicita que a partir de un arreglo como parámetro, se retorne la letra faltante, para dicho ejercicio se toma en cuenta que una de las restricciones es que son letras consecutivas, esto facilita el problema, y no se vuelve tan complejo.</p>

<p align="justify">Usando el método map, se mapea cada elemento del arreglo de entrada, y retornando el valor a un nuevo arreglo en código ascii o utf-8.</p>
<p align="justify">A partir de esto, declaramos una variable auxiliar y le asignamos el primer valor del arreglo nuevo. Después utilizando un for-of, empezamos a recorrer el arreglo nuevo, y preguntamos si el elemento de arreglo nuevo es es diferente a la variable auxiliar, en caso de que se cumpla la condición se retorna el valor de la variable aux, pero parseando su valor de un entero a un char, en caso de que no se cumpla la condición solo aumentamos el valor de aux en uno.</p>

Completando la función, queda lo siguiente:

```javascript
function findMissingLetter(array) {
  let results = array.map((e) => e.charCodeAt(0)),
    aux = results[0];
  for (const result of results) {
    if (aux !== result) return String.fromCharCode(aux);
    aux += 1;
  }
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(findMissingLetter(["O", "Q", "R", "S"]));
```

<p>Obteniendo como respuesta: <strong>'P'</strong></p>

<a name="reverse"></a>

## Reverse Or Rotate? exercise

<p align="justify">The input is a string str of digits. Cut the string into chunks (a chunk here is a substring of the initial string) of size sz (ignore the last chunk if its size is less than sz).</p>

<p align="justify">If a chunk represents an integer such as the sum of the cubes of its digits is divisible by 2, reverse that chunk; otherwise rotate it to the left by one position. Put together these modified chunks and return the result as a string.</p>

If

<ul>
	<li>sz is <= 0 or if str is empty return ""</li>
	<li>sz is greater (>) than the length of str it is impossible to take a chunk of size sz hence return "".</li>
</ul>

<p align="justify">Se nos solicita a partir de dos parámetros, una cadena de números y un número entero, que se parta la cadena en varias partes, según la cantidad que indique el número entero, además de esto hay reglas que cumplir, si sz es menor o igual a 0 se retorna una cadena vacía o si la cadena de números viene vacía res retorna una cadena vacía, o si sz es mayor a la longitud de números se retorna cadena vacía, dicho esto, pasamos a resolver el problema.</p>


<ul>
	<li>Primero que nada, se toma en cuenta las reglas anteriormente mencionadas.</li>
	<li>Lo siguiente es cortar la cadena según el tamaño indicado en sz (size=Tamaño), y lo que alcance de la cadena se ignora.</li>
	<li>Los cadenas que si cumplen, se almacenan en un nuevo arreglo.</li>
	<li>Después, con un for-of, recorremos dicha arreglo de cadenas de números, dentro de recorrido usamos una variable auxiliar, esto para realizar el resto de pasos necesarios, bien asignamos por valor el contenido de number(elemento actual) y lo almacenamos en la variable auxiliar.</li>
	<li>El siguiente paso es, aplicar un split, que nos devuelve un arreglo de numeros en string, luego se aplica un map, en dicho map, devolvemos los números pero convirvirtiendolos en enteros, y por último aplicamos un reduce, al que su valor actual se le saca la potencia elevada a la 3 y se devuelve un único valor.</li>
	<li>Ya que tenemos un único número, preguntamos si es divisible por dos, si es divisible por dos se debe invertir la cadena de números, recordar que esta queda intacta ya que la variable auxiliar contiene una copia del mismo por valor, entonces, el numero se vuelve un arreglo con split, luego se aplica un reverse y por último se une el arreglo con un join.</li>
	<li>En caso de que no sea divisible por dos, simplemente corremos el primer digito del número al final de la cadena de ese mismo número.</li>
	<li>Luego de todo esto, se almacenan las cadenas de números en un nuevo arreglo.</li>
	<li>Por último, se retorna el arreglo, pero antes se convierte en una cadena usando el método join.</li>
</ul>

Completando la función, queda lo siguiente:

```javascript
function revrot(str, sz) {
  if (sz <= 0 || str === "" || sz > str.length) return "";
  let str2 = [],aux = "",number2 = [],aux2 = 0,cadena = [];
  for (let i = 0; i <= str.length; i++) {
    if (aux.length === sz) {
      str2.push(aux);
      aux = "";
    }
    aux += str[i];
  }
  for (let number of str2) {
    aux2 = number;
    aux2 = number
      .split("")
      .map((e) => Number(e))
      .reduce((pv, pc) => pv + Math.pow(pc, 3), 0);
    if (aux2 % 2 == 0) {
      number = number.split("").reverse().join("");
    } else {
      x = number[0];
      number = number.slice(1) + x;
    }
    cadena.push(number);
  }
  return cadena.join("");
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(revrot("563000655734469485", 4));
```

<p>Obteniendo como respuesta: <strong>'0365065073456944'</strong></p>
<a href="../README.md">Inicio</a>