# Monday 25-04-2022

<a name='who'></a>

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

<a name='big-counting'></a>

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

<a name='your-order'></a>

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

<a href="../README.md">Inicio</a>