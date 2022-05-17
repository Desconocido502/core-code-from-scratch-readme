# Monday 16-05-2022

<ul>
  <li><strong>Checked the everyday types in typescript 💹</strong></li>
  <li><a href="#square"><strong>Square(n) Sum exercise, using Typescript</strong></a></li>
  <li><a href="#growth"><strong>Growth Of A Population exercise, using Typescript</strong></a></li>
  <li><a href="#mumbling"><strong>Mumbling exercise, using Typescript</strong></li></a>
  <li><a href="#wolf"><strong>A Wolf In Sheep's Clothing exercise, using Typescript</strong></a></li>
</ul>

<a name="square"></a>

## Square(n) Sum exercise, using Typescript

<p align="justify">Complete the square sum function so that it squares each number passed into it and then sums the results together.</p>

<p align="justify">For example, for [1, 2, 2] it should return 9 because 1^2 + 2^2 + 2^2 = 9.</p>

<p align="justify">Se nos solicita que completemos la función para que retorne la suma de cada uno de los números del arreglo al cuadrado.</p>


<p align="justify">Para esto, simplemente usamos el método reduce junto con el método Pow que ofrece la libreria de Math de JS.</p>

Función completada:
```typescript
export function squareSum(numbers: number[]): number {
    return numbers.reduce((pv: number,cv: number) => pv + Math.pow(cv, 2),0);
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```typescript
console.log(squareSum([0,3,4,5]));
```

<p>Obteniendo como respuesta: <strong>50</strong></p>

<a name="growth"></a>

## Growth Of A Population exercise, using Typescript

<p align="justify">In a small town the population is p0 = 1000 at the beginning of a year. The population regularly increases by 2 percent per year and moreover 50 new inhabitants per year come to live in the town. How many years does the town need to see its population greater or equal to p = 1200 inhabitants?</p>

<p align="justify">Se nos solicita calcular ¿cuántos años necesita el pueblo para ver su población mayor o igual a n cantidad de habitantes? En si es un problema de estadistica básica combinado con progrmación.</p>

<p align="justify">Para el calculo de población, simplemente nos dan un fórmula de manera implicíta, la cual es:</p>

```code
operation = p0 + (p0 * (percent/100) + aug)
```

donde:

<ul>
  <li>p0: Es el número de habitantes iniciales en la población.</li>
  <li>percent: Es el porcentaje con el que crecerá la población.</li>
  <li>aug: Habitantes que se van de la población.</li>
  <li>p: Poblacion a la que se debe igualar o superar en x años.</li>
</ul>

<p align="justify">Teniendo esto en cuenta, se realizo el siguiente código:</p>

Función completada:
```typescript
class operacion {
    public static nbYear = (p0:number, percent:number, aug:number, p:number) => {
        let operation: number = p0,  year: number = 0;
        while(p < operation){
            operation = Math.floor(operation + (operation * (percent/100)) + aug);
            year += 1;
        }
        return year;
    }
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```typescript
let x: operacion = new operacion();
console.log(operacion.nbYear(1000,2,50,1200));
```

<p>Obteniendo como respuesta: <strong>3</strong></p>

<a name="mumbling"></a>

## Mumbling exercise, using Typescript

<p align="justify">This time no story, no theory. The examples below show you how to write function accum:</p>

<strong>Examples:</strong>

```code
accum("abcd") -> "A-Bb-Ccc-Dddd"
accum("RqaEzty") -> "R-Qq-Aaa-Eeee-Zzzzz-Tttttt-Yyyyyyy"
accum("cwAt") -> "C-Ww-Aaa-Tttt"
```

<p align="justify">The parameter of accum is a string which includes only letters from a..z and A..Z.</p>

<p align="justify">Esta kata es un tanto interesante, ya que no trae muchas indicaciones de como realizar el problema, mas que observar la entrada y la salida de datos, y es sencillo, ya que solo con ver, nos damos cuenta de lo siguiente:</p>

<ul>
  <li>Se ingresa por parámetro una cadena de texto.</li>
  <li>Son letras de a-z o A-Z combinadas.</li>
  <li>Se tienen que volver minúsculas todas la letras de la cadena de entrada.</li>
  <li>De retorno La primera letra siempre debe ir en mayúscula y el resto en minúsculas.</li>
  <li>La letra se repite las veces en la posición que se encuentre, osea que si la letra está de primero, solo se repite una vez, si la letra está en la décima posición se repetirá 10 veces y así sucesivamente.</li>
</ul>

<p align="justify">Con dicha información realizamos la siguiente función en TypeScript:</p>

Función completa:
```typescript
export function accum(s: string): string {
    let cadena: string = '', str = s.toLowerCase().split("").map((e:string, index:number) => {
        for (let i = 0; i < (index+1); i++) {
            if(i == 0) cadena += e.toUpperCase()
            else cadena += e
        }
        e = cadena, cadena = ''
        return e;
    });
    return str.join("-");
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```typescript
console.log(accum('RqaEzty'));
```

<p>Obteniendo como respuesta: <strong>'R-Qq-Aaa-Eeee-Zzzzz-Tttttt-Yyyyyyy'</strong></p>

<a name="wolf"></a>

## A Wolf In Sheep's Clothing exercise, using Typescript

<p align="justify">Wolves have been reintroduced to Great Britain. You are a sheep farmer, and are now plagued by wolves which pretend to be sheep. Fortunately, you are good at spotting them.</p>

<p align="justify">Warn the sheep in front of the wolf that it is about to be eaten. Remember that you are standing at the front of the queue which is at the end of the array:</p>

```code
[sheep, sheep, sheep, sheep, sheep, wolf, sheep, sheep]
   7      6      5      4      3            2      1
```

<p align="justify">If the wolf is the closest animal to you, return "Pls go away and stop eating my sheep". Otherwise, return "Oi! Sheep number N! You are about to be eaten by a wolf!" where N is the sheep's position in the queue.</p>

<strong>Examples:</strong>
Example 1:
<p align="center">["sheep", "sheep", "sheep", "wolf", "sheep"]</p>
<p align="center">"Oi! Sheep number 1! You are about to be eaten by a wolf!"</p>
Example 2:
<p align="center">["sheep", "sheep", "wolf"]</p>
<p align="center">"Pls go away and stop eating my sheep"</p>

<p align="justify">Para solucionar dicho problema, nos mencionan que tenemos una cola simulada, en este es un array, pero simulando el proceso de una cola al revés, cuando digo al revés es por que su inicio esta al final del array.</p>

<p align="justify">Bien, para solucionarlo, nos dicen que como entrada de la función se tiene un arreglo de strings, en donde el arreglo tendrá ovejas y siempre un lobo, el lobo puede estar en cualquier posición de la cola.</p>

<p align="justify">Para dar la solución es sencillo, usando el método de indexof, que nos retorna el indice donde se encuentra lo que se esta buscando en el arreglo, y en caso de que no lo encuentre, retorna -1, pero como la kata menciona que siempre habrá un lobo, entonces nunca nos devolverá un -1.</p>

<p align="justify">El otro método utilizado fue reverse, que nos ayuda a voltear el arreglo, al orden inverso a como estaba originalmente, ahora de forma global para la función lo que realizo fue, aplicar un reverse al arreglo seguido de un indexof buscando al lobo, y retornando el indice donde se encuentra.</p>

<p align="justify">Con dicha información realizamos la siguiente función en TypeScript:</p>

Función completa:
```typescript
export function warnTheSheep(queue: string[]): string {
    let index_wolf = queue.reverse().indexOf('wolf');
    if (index_wolf == 0) return "Pls go away and stop eating my sheep";
    return `Oi! Sheep number ${index_wolf}! You are about to be eaten by a wolf!`
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```typescript
console.log(warnTheSheep(["sheep", "sheep", "sheep", "sheep", "sheep", "wolf","sheep", "sheep"]));
```

<p>Obteniendo como respuesta: <strong>'Oi! Sheep number 2! You are about to be eaten by a wolf!'</strong></p>

<a href="../README.md">Inicio</a>