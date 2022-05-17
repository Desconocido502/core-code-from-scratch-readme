# Tuesday 26-04-22

<a name='simple-pig'></a>

## Simple Pig Latin exercise

<p align="justify">Move the first letter of each word to the end of it, then add "ay" to the end of the word. Leave punctuation marks untouched.</p>

<p align="justify"> A partir de una cadena como argumento, se solicita tomar la primera letra de cada palabra y moverla al final de la misma, y agregarle un 'ay' a cada palabra, en caso de que venga un signo de puntuación, se deja en el mismo lugar y no se hace nada.</p>
	
Los signos de puntuación son los siguientes: '.',',',';','(',')','[',']','{','}','¿','?','!','¡'

<ul>
	<li>Primero, se separa la cadena en palabras, haciendo uso del meotodo split.</li>
	<li>Se crea un arreglo de signos de puntuacion, y se declaran variables, extras a usar(cadena, aux).</li>
	<li>Se recorre el arreglo de Strings, y preguntamos si la palabra no se incluye en el arreglo de signos de puntuacion.</li>
	<li>Si no se incluye, entonces, tomamos el primer valor de la palabra osea la primera letra, y la almacenamos en aux.</li>
	<li>Luego de esto, en cadena se almacena la palabra pero, recortada, osea se le quita la primera letra.</li>
	<li>Despues, a la cadena de Strings en la i-ésima posición se le almacena, la cadena, el aux y el 'ay'.</li>
	<li>Al terminar de recorrer el arreglo, se une con el metodo join, propio de js, y se retorna como una cadena.</li>
</ul>

Obteniendo así la siguiente función:

```javascript
function pigIt(str){
    str = str.split(' ');
    let signos = ['.',',',';','(',')','[',']','{','}','¿','?','!','¡'];
    let cadena ='', aux = '';
    for (let i = 0; i < str.length; i++) {
        if(!signos.includes(str[i])){
            aux = str[i][0];
            cadena = str[i].slice(1);
            str[i] = cadena + aux + 'ay';
        }
    }
    str = str.join(' ')
    return str
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(pigIt('Hello world !'));
```

<p>Obteniendo como respuesta: <strong>'igPay atinlay siay oolcay'</strong></p>

<a name='counting-duplicates'></a>

## Counting Duplicates exercise

<p align="justify">Write a function that will return the count of distinct case-insensitive alphabetic characters and numeric digits that occur more than once in the input string. The input string can be assumed to contain only alphabets (both uppercase and lowercase) and numeric digits.</p>

Función a completar:

```javascript
function duplicateCount(text){
  //...
}
```

<p align="justify">Bien, para solucionar el problema se nos indica que a partir de una cadena como argumento, se devuelva la cantidad de caracteres que aparecen más de una vez en la cadena de entrada.</p>

<ul>
	<li>Se vuelven todos los caracteres en minusculas, se separan por medio de split, se ordenan, y se vuelven a juntar con el método join.</li>
	<li>Lugo de esto, filtramos las palabras que esten repetidas, quedandonos con un nuevo arreglo sin caracteres repetidos.</li>
	<li>Se empueza a recorrer este nuevo arreglo sin caracteres repetidos, y se manda a llamar a una función extra.</li>
	<li>La función extra se encarga de contar cuantas veces aparece un caracter dentro de una cadena, y devolver el contador</li>
	<li>tras esto, vamos a preguntar si el contador posee una cantidad mayor a 1, en caso de que sea verdad, el contador global crecerá.</li>
	<li>Al terminar de recorrer el arreglo de caracteres que no se repiten, se retorna el contador global.</li>
</ul>

Función complementaria

```javascript
function cuantasVecesAparece(cadena, caracter){
  var indices = [];
  for(var i = 0; i < cadena.length; i++) {
    if (cadena[i] === caracter) indices.push(i);
  }
  return indices.length;
}
```

Función completa:

```javascript
function duplicateCount(text) {
  text = text.toLowerCase().split('').sort().join('')
  let contador = 0, cont_aux = 0;
  
  let result = text.split('').filter((item,index)=>{
    return text.indexOf(item) === index;
  });
  console.log(text)
  for (let i = 0; i < result.length; i++) {
    cont_aux = cuantasVecesAparece(text, result[i])
    //console.log(cont_aux)
    if(cont_aux > 1){
      contador += 1
    }
  }
  return contador
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(duplicateCount("Indivisibilities"));
```

<p>Obteniendo como respuesta: <strong>2</strong></p>

<a name='decode'></a>

## Decode The Morse Code exercise

<p align="justify">In this kata you have to write a simple Morse code decoder. While the Morse code is now mostly superseded by voice and digital data communication channels, it still has its use in some applications around the world.</p>

<p align="justify">The Morse code encodes every character as a sequence of "dots" and "dashes". For example, the letter A is coded as ·−, letter Q is coded as −−·−, and digit 1 is coded as ·−−−−. The Morse code is case-insensitive, traditionally capital letters are used. When the message is written in Morse code, a single space is used to separate the character codes and 3 spaces are used to separate words. For example, the message HEY JUDE in Morse code is ···· · −·−−   ·−−− ··− −·· ·.</p>

<p align="justify">Se nos solicita, que a partir de una cadena como argumento, se pase de código en morse, a los caracteres que una persona normal pueda leer.</p>

<ul>
	<li>Lo primero que haremos es limpiar la cadena de espacios vacios, al final y al inicio de la cadena con código morse.</li>
	<li>Al terminar de limpiar con el método trim, le añademos un espacio al final de la cadena, esto servíra para el proceso de separar los caracteres.</li>
	<li>Con un while, vamos a recorrer desde 0 hasta el largo de la cadena, para hacer la respectiva separación de los códigos morse.</li>
	<li>Dentro del while, preguntamos, si el caracter en la i-ésima es igual a un punto o igual a un guion. En caso de ser asi se concatena a una cadena de texto, previamente declarada.</li>
	<li>Después de preguntar esto, preguntamos si el caracter en la i-ésima posición es igual a un espacio, en caso de serlo, se agrega el contenido de la cadena de texto, a un arreglo, y se limpia la cadena de texto.</li>
	<li>Luego, pregunta nuevamente si si el caracter en la i-ésima posición +1 y si el caracter en la i-ésima posición +2 es igual a un espacio, en caso de que sea verdad, almacenamos un espacio, dentro del arreglo anterior, y aumentamos en dos el contador del while.</li>
	<li>Al terminar este proceso, se hace uso del método map, para recorrer los elementos del arreglo anterior, que vendria siendo el arreglo con los códigos morse.</li>
	<li>dentro del mao, hacemos una validación si el elemento es diferente de un espacio, que retorne el valor del elemento como un caracter legible.</li>
	<li>En caso de que el elemento sea un espacio, solo se retorna el elemento.</li>
	<li>Por último, fuera del map, retornamos la cadena descifrada, y lo hacemos por medio del método join.</li>
</ul>


Función completa:
```javascript
decodeMorse = function(morseCode){
  
  let morse = [],aux = "";
  let i = 0;
  morseCode = morseCode.trim() + ' '
  while (i < morseCode.length) {
    if (morseCode[i] === "." || morseCode[i] === "-") aux += morseCode[i];

    if (morseCode[i] === " ") {
      morse.push(aux);
      aux = "";
      if (morseCode[i + 1] === " " && morseCode[i + 2] === " ") {
        morse.push(" ");
        i += 2;
      }
    }
    i++;
  }
  const message = morse.map(element => {
    if(element !== ' '){
      return MORSE_CODE[element]
    }else{
      return element
    }
  });
  return message.join('');
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(decodeMorse(".... . -.--   .--- ..- -.. ."));
```

<p>Obteniendo como respuesta: <strong>'HEY JUDE'</strong></p>

<a href="../README.md">Inicio</a>