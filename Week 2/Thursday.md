# Thursday 21-04-2022

<ul>
    <li><a href='#remove'><strong>Remove All Exclamation Marks From The End Of Sentence exercise</strong></a></li>
    <li><a href='#vocal-remove'><strong>Vowel Remover exercise</strong></a></li>
    <li><a href='#rock-paper-scissor'><strong>Rock Paper Scissors! exercise</strong></a></li>
    <li><a href='#persistent'><strong>Persistent Bugger exercise</strong></a></li>
</ul>


<a name='remove'></a>

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

<a name='vocal-remove'></a>

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

<a name='rock-paper-scissor'></a>

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

<a name='persistent'></a>

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
<a href="../README.md">Inicio</a>