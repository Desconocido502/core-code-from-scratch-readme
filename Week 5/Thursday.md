# Thursday 12-05-2022

<ul>
  <li><a href='#poison'><strong>What's Your Poison? exercise</strong></a></li>
  <li><a href='#diff'><strong>Array.diff exercise</strong></a></li>
  <li><strong>Complete your 3rd Core Challenge - 100% Completed💹.</strong></li>
</ul>

<a name="poison"></a>

## What's Your Poison? exercise

#### The Riddle
<p align="justify">The King of a small country invites 1000 senators to his annual party. As a tradition, each senator brings the King a bottle of wine. Soon after, the Queen discovers that one of the senators is trying to assassinate the King by giving him a bottle of poisoned wine. Unfortunately, they do not know which senator, nor which bottle of wine is poisoned, and the poison is completely indiscernible.</p>

<p align="justify">However, the King has 10 lab rats. He decides to use them as taste testers to determine which bottle of wine contains the poison. The poison when taken has no effect on the rats, until exactly 24 hours later when the infected rats suddenly die. The King needs to determine which bottle of wine is poisoned by tomorrow, so that the festivities can continue as planned.</p>

<p align="justify">Hence he only has time for one round of testing, he decides that each rat tastes multiple bottles, according to a certain scheme.</p>

#### Your Task

<p align="justify">You receive an array of integers (0 to 9), each of them is the number of a rat which died after tasting the wine bottles. Return the number of the bottle (1..1000) which is poisoned.</p>

#### Good Luck!

<p align="justify">Hint: think of rats as a certain representation of the number of the bottle...</p>

<p align="justify">Se nos solicita en este problema de acertijo, que a partir de la entrada de un arreglo con números enteros del 0 al 9, retornemos el número de la botella que se encuentra envenenada.</p>

<p align="justify">Bien para solucionar el problema, nos dejan pequeñas pistas, las cuales son:</p>

<ul>
	<li>Cada número entero del arreglo es el número de una rata que murió después de probar las botellas de vino.</li>
	<li>Pensar en las ratas como una determinada representación del número de la botella.</li>
</ul>

<p align="justify">Bien, al tomar en cuenta las pistas, se nos indica que pensemos en las ratas cono una determinada representación del número de la botella. Osea que, una rata en si, representa el número de una botella en específico, pero además el número de la rata no da directamente el número de la botella envenenada, ya que de algún modo estamos trabajando con números binarios. En fin, la resolución se reduce que cada número en el arreglo representa la elevación a la que debe de estar el número dos para saber el número de botella correspondiente a cada rata.</p>

<p align="justify">LLegando al resultado de que, al sumar todas las potencias de dos de cada número que existe en el arreglo, se obtiene el número de botella envenenada, quedando así el resultado:</p>

Función completada:
```javascript
function find(rats) {
    return rats.reduce((pv, cv) => pv+Math.pow(2, cv),0);
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(find([0, 1, 9, 3, 5]));
```

<p>Obteniendo como respuesta: <strong>555</strong></p>

<a name="diff"></a>

## Array.diff exercise

<p align="justify">Your goal in this kata is to implement a difference function, which subtracts one list from another and returns the result.</p>
<p align="justify">It should remove all values from list a, which are present in list b keeping their order.</p>

```javascript
arrayDiff([1,2],[1]) == [2]
```

<p align="justify">If a value is present in b, all of its occurrences must be removed from the other:</p>

```javascript
arrayDiff([1,2,2,2,3],[2]) == [1,3]
```

<p align="justify">Para dicho problema se nos solicita que a partir de dos arreglos de entrada (parámetros), se reste una lista de otra y se retorne la lista limpia, en pocas palabras, se deben borrar los elementos de la lista 'a' que esten en la lista 'b', manteniendo el orden, y en caso de que en la lista 'a' existan n ocurrencias de un elemento de b, se eliminen.</p>

<p align="justify">Para solucionar el problema usamos el método filter y el método includes.</p>
<ul>
	<li>Método filter: Se usa para 'filtrar' los elementos del arreglo.</li>
	<li>Método includes: Sirve para verificar si un x elemento se encuentra en un arreglo.</li>
</ul>

<p align="justify">Bien, comentando como funciona el método, se diría que filtrariamos elemento por elemento el arreglo a, y por cada elemento del arreglo de a preguntamos si no se incluye en el arreglo b, si es válido se retorna el valor al arreglo mismo, finalmente se retorna el arreglo limpio, sin ocurrecias y sin números que esten dentro del arreglo b.</p>

Función completada:
```javascript
function arrayDiff(a, b) {
    return a.filter((element) => {
        if (!b.includes(element)) return a
    });
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(arrayDiff([1,2,2,2,3],[2]));
```

<p>Obteniendo como respuesta: <strong>[1,3]</strong></p>

<a href="../README.md">Inicio</a>
