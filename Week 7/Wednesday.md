# Wednesday 18-05-2022

<ul>
  <li><strong>Interfaces guided exercise, using Typescript</strong>☑️</li>
  <li><a href="#build"><strong>Build Tower exercise, using Typescript</strong></a></li>
  <li><a href="#meeting"><strong>Meeting exercise, using Typescript</strong></a></li>
</ul>


<a name="build"></a>

##  Build Tower exercise, using Typescript

<p align="justify">Build a pyramid-shaped tower given a positive integer number of floors. A tower block is represented with "*" character.</p>

<p align="justify">For example, a tower with 3 floors looks like this:</p>

```code
[
  "  *  ",
  " *** ", 
  "*****"
]
```

<p align="justify">Se nos solicita que a partir de un número de entrada, se retorne un arreglo de strings, creando una torre, los caracteres a usar son '*', y ' ', para ello realizamos la siguiente solución:</p>

<ul>
  <li>Se declaro un arreglo de strings.</li>
  <li>Se utiliza un for para realizar un recorrido e ir insertando los caracteres correspondientes a la torre.</li>
  <li>Se retorna el arreglo de strings.</li>
</ul>

<p align="justify">Algo muy importante a tomar en cuenta es que dentro del for se utiliza el método repeat, que nos permite colocar n cantidad de veces un caracter que querramos dentro de un string.</p>

<p align="justify">Lo siguiente a tomar en cuenta es que para crear la torre ocupamos de un asterisco y de un espacio en blanco. La creación de la torre se realiza con los asteriscos, la cantidad de asteriscos será siempre un valor impar, osea 1,3,5,7,9, etc. Para describirlos números impares de tiene la fórmula <strong>2n-1 o 2n+1</strong>, donde n representa el número de una iteración.</p>

<p align="justify">Bien para dar solución general del problema, se tiene que en la parte del buble for, al ingresar la cadena de caracteres dentro de la torre utilizar la función repeat, para este caso, diremos que si son espacios en blanco (' '), se repite: El número ingresado menos el valor de la iteración menos uno, y en caso de se trata de un asterisco ('*'), se repite: La multiplicación de dos por el valor de la iteración, y a dicho resultado se le resta uno. Esto se realiza en el siguiente orden:</p>

<p align="justify">Espacio(s) en blanco - Asterisco(s) - Espacio(s) en blanco</p>

<p align="justify">Bien con esto, presentamos el siguiente código:</p>

```typescript
export const towerBuilder = (nFloors: number): string[] => {
  let tower: string[] = [];
  for (let i = 0; i < nFloors; i++) {
    tower.push(
      " ".repeat(nFloors - i - 1) +
        "*".repeat(2 * i + 1) +
        " ".repeat(nFloors - i - 1)
    );
  }
  return tower;
}
```

<p align="justify">Realizando una prueba se tiene:</p>

```typescript
console.log(towerBuilder(3));
```

<p align="justify">Salida:</p>

```code
[
  "  *  ",
  " *** ", 
  "*****"
]
```

<a name="meeting"></a>

## Meeting exercise, using Typescript

John has invited some friends. His list is:

```code
s = "Fred:Corwill;Wilfred:Corwill;Barney:Tornbull;Betty:Tornbull;Bjon:Tornbull;Raphael:Corwill;Alfred:Corwill";
```

Could you make a program that

* makes this string uppercase
* gives it sorted in alphabetical order by last name.

<p align="justify">When the last names are the same, sort them by first name. Last name and first name of a guest come in the result between parentheses separated by a comma.</p>

So the result of function meeting(s) will be:

```code
"(CORWILL, ALFRED)(CORWILL, FRED)(CORWILL, RAPHAEL)(CORWILL, WILFRED)(TORNBULL, BARNEY)(TORNBULL, BETTY)(TORNBULL, BJON)"
```
<p align="justify">It can happen that in two distinct families with the same family name two people have the same first name too.</p>

<strong>Notes:</strong>

* You can see another examples in the "Sample tests".

<p align="justify">Se nos solicita que a partir de un string como argumento para la función, se retorne una nueva cadena de texto, en si la cadena de entrada, trae un listado de personas los cuales Juan ha invitado, entre dichos invitados vienen personas con el mismo apellido o incluso con el mismo nombre. Entonces, lo solicitado es que los caracteres sean mayúsculas, y que se ordenen alfabéticamente por apellido, en caso de que los apellidos sean iguales, que se ordenen por nombre.</p>

<p align="justify">Como resultado se devuelve una cadena con los nombres y apellidos de los invitados de forma ordenada y por cada invitado tenemos: <strong>(Name, Last Name)</strong>, con todo esto pasamos a la explicación de la función:</p>

<ul>
  <li>Declaramos una variable aux, esta nos servirá para almacenar el nombre y apellido de la persona temporalamente.</li>
  <li>Luego declaramos otra variable llamada persons, que almacenará objetos de tipo persona dentro del arreglo, y aplicamos los siguientes métodos:
  <ul>
    <li>toUpperCase: Método encargado de volver máyusculas todas las letras de una cadena de texto.</li>
    <li>split: Método que retorna un arreglo de caracteres, al cual se le pasa un argumento, que le indicará donde cortar cada string.</li>
    <li>Map: Método para realizar directrices dentro de un arreglo, y devolver uno nuevo.</li>
    <li>Sort: Método encargado de ordenar un arreglo.</li>
    <li>Join: Método para unir un arreglo en una cadena de string, por medio de un delimitador.</li>
  </ul>
  </li>
  <li>Bien, para seguir avanzado luego de la explicación de los métodos, lo primero que haremos es volver la cadena de texto en mayúsculas, luego aplicamos split, para que nos separe la cadena de texto por medio de un punto y coma, en este punto tendríamos: <strong>Name:Last Name</strong>, no está demás decir que se aplico una interface, creada para dar solución al problema, la cual realiza un contrato, para que aparezca el nombre y el apellido de x persona.</li>
  <li>Siguiendo con el paso anterior, aplicamos un map, el cual nos ayudará a iterar elemento por elemento, y dentro de el realizaremos nuevamente un split para separar el nombre y el apellido de cada invitado. Retornando un objeto persona y almacenarlo en el arreglo.</li>
  <li>Ahora, lo que hacemos es decirle al arreglo de personas que aplique el método sort, en este caso al método sort se le puede pasar una función para ordenarlo a nuestra manera, ya que vamos a ordenar un array de objetos, y por tanto lo ordenaremos por un valor, donde el valor puede ser un nombre o apellido.</li>
  <li>En el caso de que los apellidos sean iguales, se ordenarán por el nombre, y en el caso de que los nombres sean iguales que se sigan ordenado  alfabéticamente.</li>
  <li>Ya que tenemos ordenado el array de objetos, aplicamos un map, donde lo que haremos es pasar del objeto a una cadena de texto, que se almacenaría en el nuevo arreglo de esta manera: <strong>(Last name,  name)</strong>, por último para unir los elementos aplicamos el método join, y retornamos la nueva cadena de texto.</li>
</ul>

Función completa

```typescript
function meeting(s: string): string {
  let aux: string[],
    persons: person[] = s
      .toUpperCase()
      .split(";")
      .map((e: string) => {
        aux = e.split(":");
        return { name: aux[0], last_name: aux[1] };
      });
  return persons
    .sort((a: person, b: person) =>
      a.last_name > b.last_name
        ? 1
        : a.last_name === b.last_name
        ? a.name > b.name
          ? 1
          : -1
        : -1
    )
    .map((persona: person) => {
      return `(${persona.last_name}, ${persona.name})`;
    })
    .join("");
}
```

Haciendo una prueba:

```typescript
console.log(
  meeting(
    "Fred:Corwill;Wilfred:Corwill;Barney:Tornbull;Betty:Tornbull;Bjon:Tornbull;Raphael:Corwill;Alfred:Corwill"
  )
);
```

Salida:
<p align="justify"><strong>'(CORWILL, ALFRED)(CORWILL, FRED)(CORWILL, RAPHAEL)(CORWILL, WILFRED)(TORNBULL, BARNEY)(TORNBULL, BETTY)(TORNBULL, BJON)'</strong></p>

<a href="../README.md">Inicio</a>