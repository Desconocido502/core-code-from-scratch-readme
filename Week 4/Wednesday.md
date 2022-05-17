# Wednesday 04-05-2022

<ul>
    <li><a href="#simple"><strong>Simple Validation Of A Username exercise</strong></a></li>
    <li><a href="get_n_from_str"><strong>Get Number From String exercise</strong></a></li>
</ul>

<a name='simple'></a>

## Simple Validation Of A Username exercise

<p align="justify">Write a simple regex to validate a username. Allowed characters are:</p>

<ul>
	<li>lowercase letters,</li>
	<li>numbers,</li>
	<li>underscore</li>
</ul>

<p align="justify">Length should be between 4 and 16 characters (both included).</p>

<p align="justify">Se nos solicita que a partir de un parámetro, validemos que el parámetro (cadena de texto, con un posible nombre de usuario), sea un nombre de usuario válido. Retornando true si el nombre de usuario es correcto y false en caso de que no sea válido, además de que solo pueden existir entre 4 y 16 caracteres para el nombre de usuario.</p>

<p align="justify">Para dar con la solución lo primero que necesitamos es saber el uso del método test.</p>
<p align="justify">El método test, realiza una búsqueda de una coincidencia entre la regex (expresión regular) y una cadena especificada, retornando true en caso de que sea válida la cadena o false en caso de que no lo sea.</p>

Además de esto, al usar expresiones regulares, necesitamos los conocimientos básicos de regex en JavaScript, para poder resolver el problema, en este caso haremos una diminuta mención al conjunto de reglas que se usaron para validar el nombre de usuario.

<ul>
	<li>[]: Conjunto de carácteres, ejemplo: [a-c], estos incluyen: a,b, y c.</li>
	<li>^: Inicio de una cadena de texto, ejemplo: ^hi!</li>
	<li>$: Final de una cadena de texto, ejemplo: fin$</li>
	<li>a-z: Todas las letras del alfabeto en minúsculas, ejemplo: programacion</li>
	<li>0-9: Digitos del 0 al 9, ejemplo: 502</li>
	<li>_: Guión bajo</li>
	<li>{}: Cuantificadores, estos sirven para determinar el largo de una regex.</li>
</ul>

<p align="justify">Bien, ya explicado por separado, construyamos la regex!!!</p>
<p align="justify">Necesitamos decirle que empezaremos a leer una cadena de texto, seguido le decimos que puede empezar con guion bajo o cualquier letra minúscula, seguido del conjunto de carácteres, en este caso el conjunto sería, letra minúsculas, guión bajo, digitos del 0 al 9, seguido de un cuantificador, que nos permite decirle de donde a donde sería el largo de la cadena de texto válida, en este caso se nos solicita que vaya de 4 a 16 carácteres, los llaves no incluyen los números por lo que se tendrá que colocar de 3 a 15, esto se puede pensar como un arreglo que sus posición inicial empieza con un 0, por último colocamos "$", para indicar el final de la cadena de texto, asi obteniendo la siguiente expresión regular:</p>

<p align="center">^[a-z_][a-z0-9_]{3,15}$</p>

Completando la función, queda lo siguiente:

```javascript
function validateUsr(username) {
    return /^[a-z_][a-z0-9_]{3,15}$/.test(username) 
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(validateUsr('Hasd_12assssssasasasasasaasasasasas'));
```

<p>Obteniendo como respuesta: <strong>false</strong></p>

<a name='get_n_from_str'></a>

## Get Number From String exercise

<p align="justify">Write a function which removes from string all non-digit characters and parse the remaining to number. E.g: "hell5o wor6ld" -> 56</p>

<p align="justify">Se nos solicita que a parir de una cadena de texto como entrada (parámetro), y retornar solo los valores númericos. Bien para esto, lo que haremos es hacer uso de una expresión regular, para encontrar los números. Las reglas son las siguientes</p>

<ul>
	<li>0-9: Digitos del 0 al 9, ejemplo: 502</li>
	<li>+: Un cuantificador que indica que puede venir una o más veces alguna regex o algún carácter.</li>
</ul>

<p align="justify">También se uso la bandera g, que nos proporciona JavaScript, para indicar que sea una búsqueda global, osea sobre toda la cadena de texto que se encontrará bajo análisis. Así obteniendo la siguiente regex:</p>

<p align="center">/\d+/g</p>

Completando la función, queda lo siguiente:

```javascript
function getNumberFromString(s) {
    return parseInt(s.match(/\d+/g).join(''))
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(getNumberFromString('"hell5o wor6ld"'));
```

<p>Obteniendo como respuesta: <strong>56</strong></p>
<a href="../README.md">Inicio</a>