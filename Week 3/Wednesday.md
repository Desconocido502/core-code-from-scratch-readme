# Wednesday 27-04-2022

<a name='valid-pa'></a>

## Valid Parentheses exercise

<p align="justify">Write a function that takes a string of parentheses, and determines if the order of the parentheses is valid. The function should return true if the string is valid, and false if it's invalid.</p>

<p align="justify">Se nos solicita validar el orden de los parentesis en una cadena de texto, como argumento, osea que esten ordenados de forma correcta, o que esten escritos bien de manera sintáctica.</p>

<p align="justify">Se hará una implementación de una 'pila', aprovechando el poder que nos brindan los métodos de los arreglos en javascript.</p>

<ol>
	<li>Se declara un arreglo que nos servirá para actuar emmular la pila, y un indice, para llevar el control de las posiciones en la cadena de texto.</li>
	<li>Se crea un while, validando que mientra el indice sea menor al largo de la cadena de texto, realice todo lo que se le solicita.</li>
	<li>Dentro del while, si viene un parentésis de apertura se agrega a la pila. Sino, existen dos opciones:
		<ol>
			<li>Que el tamaño de la pila sea cero.</li>
			<li>Que el tamaño de la pila no sea cero.</li>
		</ol>
	</li>	
	<li>En caso de que el tamaño de la pila sea cero, se retorna falso, ya que se esperaría que la pila no este vacía.</li>
	<li>En caso de que el tamaño de la pila <strong>NO</strong> sea cero, es por que dentro de la pila se encuentran los parentésis de apertura, y se deben de quitar, con el método pop.</li>
	<li>Al terminar de recorrer la cadena, se pregunta nuevamente por el tamaño de la pila, si es cero, es por que sintácticamente, los parentésis venian orenados de forma correcta, por tanto retornando un true.</li>
	<li>En caso de que la pila no se encuentre vacía, quiere decir que no venían sintácticamente bien ordenados, así retornando un false.</li>
</ol>

Funcíon completada:

```javascript
function validParentheses(parens) {
  let pila = [], i = 0;
  while (i < parens.length) {
    if (parens[i] == "(") {
      pila.push(parens[i]);
    } else {
      if (pila.length === 0) {
        return false;
      } else {
        pila.pop();
      }
    }
    i++;
  }
  if (pila.length === 0) return true;
  return false;
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(validParentheses("())("));
```

<p>Obteniendo como respuesta: <strong>false</strong></p>

<a name='convert-str'></a>

## Convert String To Camel Case exercise

<p align="justify">Complete the method/function so that it converts dash/underscore delimited words into camel casing. The first word within the output should be capitalized only if the original word was capitalized (known as Upper Camel Case, also often referred to as Pascal case).</p>

<p align="justify">Se nos solicita que a partir de una cadena pasada como argumento, se pase dicha cadena a camelCase, esto quiere decir la notación del camello. Esto quiere decir que luego de la primera palabra escrita las primeras letras del resto del identificador deben ir en mayúsuculas, Ejemplo: miVarible. Esto es una buena práctica en programación0.</p>

<ul>
	<li>Se necesita saber con que tipo de signo se separan el identficador, en este caso, solo son dos signos: guión('-'), guión bajo('_').</li>
	<li>Esto se realiza con el método includes, si el identificador incluye guión se le asigna un split con guión sino se le aplica un guión bajo al split como argumento de separación. </li>
	<li>A partir de aqui se usa el método map que nos devuelve un nuevo arreglo, dentro del mismo, se verificará la primera letra de cada palabra, almacenada en el arreglo se Strings que se realizó al aplicar el método split.</li>
	<li>La primera palabra dentro de la salida debe estar en mayúsculas solo si la palabra original estaba en mayúsculas, es por esto que dentro de map, se válida que si el indice del elemento es cero no se toque, ya que asi validamos que la primer letra de la primera palabra sea minúscula, o que si ya venía en mayúscula, no tenga cambios. En caso contrario, solamente se quita dicha letra y se reemplaza con la misma letra en mayúsculas.</li>
	<li>al terminar con map. se retorna el arreglo de strings, pero no sin antes unirlo y volver en una cadena por medio del método join.</li>
</ul>

Funcíon completada:

```javascript
function toCamelCase(str){
    if(str.includes('_')) str = str.split('_')
    else str = str.split('-')
    const camelCase = str.map((element, index) => {
        if(index != 0){
            if(element.charAt(0) !== element.charAt(0).toUpperCase()){
                return element[0].toUpperCase() + element.slice(1)
            }
        }
        return element
    });
    return camelCase.join('');
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(toCamelCase("the-stealth-warrior"));
```

<p>Obteniendo como respuesta: <strong>'theStealthWarrior'</strong></p>

<a name='unique'></a>

## Unique In Order exercise

<p align="justify">Implement the function unique_in_order which takes as argument a sequence and returns a list of items without any elements with the same value next to each other and preserving the original order of elements.</p>

<p align="justify">A partir de un parametro, que puede ser una cadena de texto o un arreglo de números, se nos solicita que se devuelva una lista de elementos sin ningún elemento con el mismo valor uno al lado del otro y conservando el orden original de los elementos.</p>

<ul>
	<li>En caso de que ingrese un arreglo vacío, se retorna un arreglo vacío.</li>
	<li>Debemos de preguntar si es un arreglo el que se ingreso por medio del iterable, en caso de que lo sea lo convertimos en una cadena de texto.</li>
	<li>Se declara un indice dandole como valor inicial 0, una variable aux que almacena la primera posición de la cadena de texto.</li>
	<li>Se almacena el valor de la variable aux en en el arreglo de result, Comenzamos un bucle while, donde se validaran el resto de instrucciones.</li>
	<li>Si el aux es diferente de lo que se esta recorriendo en la i-ésima posición, se reasigna a aux el valor de la cadena de texto en la i-ésima posición.</li>
	<li>El valor que posee aux, se almacenará en el arreglo de result, que es el contendrá los nuevos datos limpios.</li>
	<li>Después, preguntamos si el primer valor de la cadena no es un número, en caso de que se cumpla, se pasan todos los valores de caracteres a números, ya que solo serán números los que se encuentran en dicho arreglo, y retornamos el arreglo.</li>
	<li>En caso de que no se cumpla, simplemente retornamos el arreglo result.</li>
</ul>

Función completada:

```javascript
var uniqueInOrder = function (iterable) {
  let result = [];
  if(iterable.length === 0) return []
  if (Array.isArray(iterable)) iterable = iterable.join("");

  let i = 0, aux = iterable[0];
  result.push(aux);
  while (i < iterable.length) {
    if(aux != iterable[i]){
      aux = iterable[i];
      result.push(aux)
    }
    i++
  }
  if (!isNaN(result[0])){
    let = re = []
    for (let i = 0; i < result.length; i++) re.push(parseInt(result[i]))
    return re
  }
  return result;
};
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(uniqueInOrder("AAAABBBCCccceeeDAABBB"));
```

<p>Obteniendo como respuesta: <strong>[ 'A', 'B', 'C', 'c', 'e', 'D', 'A', 'B' ]</strong></p>

<a href="../README.md">Inicio</a>