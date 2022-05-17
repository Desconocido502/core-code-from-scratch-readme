# Thursday 28-04-22

<a name='fold'></a>

## Fold An Array exercise

<p align="justify">In this kata you have to write a method that folds a given array of integers by the middle x-times.</p>

<p align="justify">Se nos solicita a partir de dos parámetros, uno que es un arreglo de números y otro que es un valor entero, el cual, indica la cantidad de ejecuciones de plegado tendrá que hacer el método.</p>

<p align="justify">Se nos dice que el arreglo inicial no puede cambiar, y que en caso se mande un arreglo con un solo elemento, que se retorne dicho arreglo.</p>

<ul>
	<li>Lo primero que hacemos es uso de map, para crear dos nuevos arreglos a partir del arreglo de entrada. uno normal, y otro reverso.</li>
	<li>Dentro de un while, que es el encargado de verificar si un contador es diferente a la cantidad de vueltas que se pide, trabaje.</li>
	<li>Se preguntara por el largo del arreglo, en caso de que sea impar, se suman sus valores, exceptuando el valor de enmedio del arreglo.</li>
	<li>En caso de que si sea impar, se tiene que hacer un nuevo arreglo reverse, que almacenará los mismos datos, solo que al revés del orden que se encontraban originalmente.</li>
	<li>Lo mismo pasa en caso de que sea par, con la diferencia de que este tipo de arreglos, se tiene que sumar todos los elementos en orden inverso.</li>
	<li>Cada vez que termine de hacer el nuevo arreglo, aumenta el contador de vueltas, hasta que sea igual al contador run, salimos del while, y retornamos el valor del resultado, que vendría siendo un arreglo.</li>
</ul>

Función completada:
```javascript
function foldArray(array, runs) {
  let countFolds = 0,
  aux = [];
    
  if (array.length === 1) return array;
    
  let result = array.map((element) => element); //Se trabaja con un arreglo diferente
  let revese = array.map((element) => element); //Se trabaja con un arreglo diferente
  while (countFolds != runs) {
    if (result.length % 2 != 0) {
      //* el largo del arreglo es impar
      revese = revese.map(element => element).reverse()
      for (let i = 0; i < result.length; i++) {
        if(i < Math.ceil((result.length/2)-1)){
          aux.push(result[i]+revese[i])
        }else if(i === Math.ceil((result.length/2)-1)){
          aux.push(result[i])
          result = aux
          revese = aux
          aux = []
          countFolds += 1;
          break;
        }
      }
    }else{
      //* el largo del arreglo es par
      revese = revese.map(element => element).reverse()
      for (let i = 0; i < result.length; i++) {
        if(i < Math.ceil((result.length/2))){
          aux.push(result[i]+revese[i])
        }else{
          result = aux
          revese = aux
          aux = []
          countFolds += 1;
          break;
        }
      }
    }    
  }
  return result;
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(foldArray([ -9, 9, -8, 8, 66, 23 ], 1));
```

<p>Obteniendo como respuesta: <strong>[ 14, 75, 0 ]</strong></p>

<a name='encrypt'></a>

## Encrypt This! exercise

Encrypt this!
<p align="justify">You want to create secret messages which can be deciphered by the Decipher this! kata. Here are the conditions:</p>

<ol>
	<li>Your message is a string containing space separated words.</li>
	<li>
		You need to encrypt each word in the message using the following rules:
		<ul>
			<li>The first letter must be converted to its ASCII code.</li>
			<li>The second letter must be switched with the last letter</li>
		</ul>
	</li>
	<li>Keepin' it simple: There are no special characters in the input.</li>
	
</ol>

<p align="justify">Se nos solicita que a partir de un parámetro que contiene una cadena de texto se codifique un mensaje.</p>

<p align="justify">Las reglas son sencillas, el mensaje es una cadena separada por espacios, para encriptar la información la primera letra debe convertirse a su código ASCII, la segunda letra debe ser intercambiada con la última letra.</p>

<p align="justify">No se menciona esto, pero en caso de que el largo de la palabra en la cadena de texto sea de uno, solo se pasa a código ASCII,y si el largo es de dos, entonces, Solo se transforma a código ASCII la primera palabra, y la segunda letra, se queda como está, tomando en cuenta esto, se realiño la siguiente función:</p>

```javascript
var encryptThis = function (text) {

  if(text.length === 1) return `${text.charCodeAt(0)}`

  let letter = '', mid_letter = '', final_letter = '';
  text = text.split(' ')
  const result = text.map(e => {
    if (e.length > 2) {
      letter = e[0].charCodeAt(0)
      mid_letter = e[1]
      final_letter = e[e.length-1]
      e = e.slice(2, e.length-1);
      e = `${letter}${final_letter}${e}${mid_letter}`
      return e
    }else if (e.length === 2) {
      letter = e[0].charCodeAt(0)
      return `${letter}${e.slice(1)}`
    }
    else{
      return e.charCodeAt(0)
    }
  });
  console.log(result)
  return result.join(' ')
};
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(encryptThis("A wise old owl lived in an oak"));
```

<p>Obteniendo como respuesta: <strong>'65 119esi 111dl 111lw 108dvei 105n 97n 111ka'</strong></p>

<a name='challenge-1'></a>

## Mission Statement

### Versión en español

<p align="justify">¡¡¡Hola!!!, soy Carlos, estudiante de ingeniería y principiante en desarrollo web, actualmente llevó 4 meses estudiando desarrollo web con HTML, CSS y JavaScript, mi principal meta es convertirme en desarrollador FULL STACK JavaScript, dando soluciones a problemas audio visuales. Además de entender inteligencia artificial para el Frontend, soy responsable con cada tema que aprendo, y humilde para compartir mis conocimientos.</p>

### English version

<p align="justify">Hi!!!, I'm Carlos, engineering student and beginner in web development, currently I've been studying web development with HTML, CSS and JavaScript for 4 months, my main goal is to become a FULL STACK JavaScript developer, giving solutions to audio visual problems. Besides understanding artificial intelligence for Frontend, I am responsible with every topic I learn, and humble to share my knowledge.</p>

<a href="../README.md">Inicio</a>