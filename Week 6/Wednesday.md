# Wednesday 18-05-2022

<ul>
  <li><a href="#duplicate"><strong>Duplicate Encoder exercise, using Typescript</strong></a></li>
  <li><a href="#find"><strong>Find The Odd Int exercise, using Typescript</strong></a></li>
  <li><a href="#which"><strong>Which Are In? exercise, using Typescript</strong></a></li>
  <li><a href="#sums"><strong>Sums Of Parts exercise, using Typescript</strong></a></li>
  <li><a href="#consecutive"><strong>Consecutive Strings exercise, using Typescript</strong></a></li>
</ul>

<a href="duplicate"></a>

##  Duplicate Encoder exercise, using Typescript
  
  
<p align="justify">The goal of this exercise is to convert a string to a new string where each character in the new string is "(" if that character appears only once in the original string, or ")" if that character appears more than once in the original string. Ignore capitalization when determining if a character is a duplicate.</p>
  
Examples:
  
```code
"din"      =>  "((("
"recede"   =>  "()()()"
"Success"  =>  ")())())"
"(( @"     =>  "))(("
```
  
<p align="justify">Se nos solicita que a partir de una entrada de datos en este caso una cadena, retornemos una nueva cadena a partir de la cadena original, donde cada carácter de la nueva cadena sea '(' si existen una única ocurrencia, en caso contrario el carácter deberá ser ')'. Ignorando las mayúsculas en la cadena 
original.</p>
  
<p align="justify">Bien para llevar a cabo esto se hizo uso de dos funciones una complementaria y la otra la principal, la función complementaria es la encargada de ver cuantas veces se repite una letra dentro de una cadena.</p>
  
<p align="justify">Laa función principal es la encargada de crear la nueva cadena a partir de las apariciones de una letra en la cadena de texto y retorna la nueva cadena.</p>
  
Función complementaria:
  
```typescript
function cuantasVecesAparece(cadena:string, caracter:string){
  let indices = [];
  for(let i = 0; i < cadena.length; i++) {
    if (cadena[i] === caracter) indices.push(i);
  }
  return indices.length;
}
```
  
Función principal:
  
```typescript
export function duplicateEncode(word: string): string {
  word = word.toLowerCase();
  let count_letter: number, new_word = '';
  for (const letter of word) {
    count_letter = cuantasVecesAparece(word, letter);
    if(count_letter === 1) new_word += '(';
    else new_word += ')';
  }
  return new_word;
}
```
  
<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>
  
```typescript
console.log(duplicateEncode('Success'));
```
  
<p>Obteniendo como respuesta: <strong>')())())'</strong></p>

<a href="find"></a>

##  Find The Odd Int exercise, using Typescript
  
  
<p align="justify">Given an array of integers, find the one that appears an odd number of times.</p>
<p align="justify">There will always be only one integer that appears an odd number of times.</p>
  
<strong>Examples:</strong>
  
```code
[7] should return 7, because it occurs 1 time (which is odd).
[0] should return 0, because it occurs 1 time (which is odd).
[1,1,2] should return 2, because it occurs 1 time (which is odd).
[0,1,0,1,0] should return 0, because it occurs 3 times (which is odd).
[1,2,2,3,3,3,4,3,3,3,2,2,1] should return 4, because it appears 1 time (which is odd).
```
  
<p align="justify">Se nos solicita que a partir de un arreglo como entrada, se encuentre el que aparece un número impar de veces, y se retorne ese número.</p>
  
<p align="justify">Para dicho problema, se hizo uso de una función complementaria y de la función principal, la función complementaria sirve para llevar el conteo de un número que aparece n veces en el arreglo, retorna dicho conteo.</p>
  
<p align="justify">La función principal hará el resto del trabajo, primero creamos un objeto de tipo Set, al cual se le pasará como argumento el arreglo de números y este nos almacenará un nuevo arreglo de números sin repetir.</p>
  
<p align="justify">Bien ahora, declaramos un contador, que nos servirá para llevar la cuenta de las apariciones de cada uno de los números no repetidos. Luego de esto recorremos el arreglo de números no repetidos y dentro del recorrido validamos, con un if, le mandamos la función complementaria a la cual se le pasa el arreglo original y el elemento sin repetir, el cual nos retorna un número, con dicho número averiguamos si es un número impar, en caso de serlo al contador, se le asigna el valor del i-ésimo elemento.</p>
  
<p align="justify">Por último se retorna el número impar encontrado antes, no tenemos fallos ya que el problema indica que siempre se tendrá un número impar dentro del arreglo que se repite las n veces necesarias para que sea un número impar.</p>
  
Función complementaria:
  
```typescript
function count_numbers(array: number[], num: number): number{
  let count = 0;
  for (const n of array) if(n == num) count+=1
  return count;
}
```
  
Función principal:
  
```typescript
export const findOdd = (xs: number[]): number => {
  const numbers_no_repeat = new Set(xs);
  let count = 0;
  numbers_no_repeat.forEach((e:number) => {
    if(count_numbers(xs,e) % 2 !== 0) count = e
  });
  return count;
};
```
  
<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>
  
```typescript
console.log(findOdd([1,2,2,3,3,3,4,3,3,3,2,2,1]));
```
  
<p>Obteniendo como respuesta: <strong>4</strong></p>

<a href="which"></a>

##  Which Are In? exercise, using Typescript
  
  
<p align="justify">Given two arrays of strings a1 and a2 return a sorted array r in lexicographical order of the strings of a1 which are substrings of strings of a2.</p>
  
<strong>Example 1:</strong>
  
```code
a1 = ["arp", "live", "strong"]
  
a2 = ["lively", "alive", "harp", "sharp", "armstrong"]
  
returns ["arp", "live", "strong"]
```
  
<strong>Example 2:</strong>
  
```code
a1 = ["tarp", "mice", "bull"]
  
a2 = ["lively", "alive", "harp", "sharp", "armstrong"]
  
returns []
```
  
<strong>Notes:</strong>
  
<ul>
  <li>Arrays are written in "general" notation. See "Your Test Cases" for examples in your language.</li>
  <li>In Shell bash a1 and a2 are strings. The return is a string where words are separated by commas.</li>
  <li>Beware: r must be without duplicates.</li>
</ul>
  
<p align="justify">Dadas dos matrices de cadenas a1 y a2 devolver una matriz ordenada r en orden lexicográfico de las cadenas de las a1 cuales son subcadenas de cadenas de a2. Dichas matrices son pasadas a la función como un argumento.</p>
  
<p align="justify">Bien lo primero que haremos es declarar r como un arreglo de strings, que contendrá las subcadenas que encuentre en el arreglo b, luego le asignaremos a r un nuevo arreglo usando filter, para filtrar los datos valga la redundancia, dentro de filter comprobaremos elemento por elemento del arreglo a1.</p>
  
<p align="justify">Por cada iteración de a1, se iterará por todo el 2do arreglo para ver si entre los elementos del 2do arreglo se encuentra una subcadena de a1, esto lo hacemos por medio del método includes, preguntando si el elemento del 2do arreglo contiene la subcadena a1, y si es asi, retorna el valor de la subacadena de a1.</p>
  
<p align="justify">Debemos evitar duplicados, y esto lo haremos por medio del objeto Set, que hará el 'trabajo sucio', ya que elimina los duplicados. Luego de esto limpiamos el arreglo de strings 'r'.</p>
  
<p align="justify">Volvemos a cargar los datos sin duplicados al arreglo de strings 'r', recorriendo el objeto Set, y por último devolvemos el arreglo de strings 'r' y ordenandolo lexicográficamente por medio del método sort. Quedando así el siguiente código:</p>
  
```typescript
class G964 {
  public static inArray(a1: string[], a2: string[]): string[] {
    let r: string[];
    r = a1.filter((e) => {
      for (const element of a2) {
        if(element.includes(e)) return e.toLowerCase();
      }
    });
    const no_duplicates = new Set(r)
    r = [];
    no_duplicates.forEach(e => r.push(e));
    return r.sort();
  }
}
```
  
<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>
  
```typescript
console.log(operation.inArray(["arp", "live", "strong"],["lively", "alive", "harp", "sharp", "armstrong"]));
```
  
<p>Obteniendo como respuesta: <strong>[ 'arp', 'live', 'strong' ]</strong></p>

<a href="sums"></a>

##  Sums Of Parts exercise, using Typescript
  
  
<p align="justify">Let us consider this example (array written in general format):</p>
  
```code
ls = [0, 1, 3, 6, 10]
```
  
Its following parts:
  
```code
ls = [0, 1, 3, 6, 10]
ls = [1, 3, 6, 10]
ls = [3, 6, 10]
ls = [6, 10]
ls = [10]
ls = []
```
  
<p align="justify">The corresponding sums are (put together in a list): [20, 20, 19, 16, 10, 0]</p>
  
<p align="justify">The function parts_sums (or its variants in other languages) will take as parameter a list ls and return a list of the sums of its parts as defined above.</p>
  
<strong>Other Examples:</strong>
  
```code
ls = [1, 2, 3, 4, 5, 6] 
parts_sums(ls) -> [21, 20, 18, 15, 11, 6, 0]
  
ls = [744125, 935, 407, 454, 430, 90, 144, 6710213, 889, 810, 2579358]
parts_sums(ls) -> [10037855, 9293730, 9292795, 9292388, 9291934, 9291504, 9291414, 9291270, 2581057, 2580168, 2579358, 0]
```
  
<ul>
  <li>Take a look at performance: some lists have thousands of elements.</li>
  <li>Please ask before translating.</li>
</ul>
  
<p align="justify">Bien para este problema, se nos solicita devolver las sumas por partes, en pocas palabras lo que se necesita es retornar un nuevo arreglo con las sumas parciales del arreglo osea la primera vez se suman todos los valores del arreglo y a la siguiente vuelta se le quita el primer valor del arreglo y vuelve a sumar y asi sucesivamente, hasta que el arreglo quede vacio.</p>
  
<p align="justify">Para realizar el problema, se tiene que declarar el arreglo resultante, luego de esto, realizar la suma total del arreglo la primera vez, y almacenarlo en total.</p>
  
<p align="justify">Luego de esto, el total se almacena en el arreglo de resultados, y empezamos a usar un ciclo for normal.</p>
  
<p align="justify">Dentro del ciclo for almacenaremos la resta de cada número obtenido previamente, en la primera vuelta ya tenemos un valor en el arreglo de resultados, en la primera vuelta este valor se resta con el primer valor del arreglo original, y almacenando dicho resultado de una vez dentro del arreglo de resultados, y asi sucesivamente se hara el proceso, hasta que se llegue a largo del arreglo, para finalmente retornar el arreglo resultante.Quedando así el siguiente código:</p>
  
```typescript
export function partsSums(ls: number[]): number[] {
  const result: number[] = [];
  const total = ls.reduce((pv:number,cv:number) => pv + cv,0);
  result.push(total)
  for (let i = 0; i < ls.length; i++) {
    result.push(result[i] - ls[i]);
  }
  return result;
}
```
  
<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>
  
```typescript
console.log(partsSums([744125, 935, 407, 454, 430, 90, 144, 6710213, 889, 810, 2579358]));
```
  
<p>Obteniendo como respuesta: <strong>[
  10037855, 9293730,
   9292795, 9292388,
   9291934, 9291504,
   9291414, 9291270,
   2581057, 2580168,
   2579358,       0
]</strong></p>

<a href="consecutive"></a>

## Consecutive Strings exercise, using Typescript

<p align="justify">You are given an array(list) strarr of strings and an integer k. Your task is to return the first longest string consisting of k consecutive strings taken in the array.</p>

<strong>Examples:</strong>

```code
strarr = ["tree", "foling", "trashy", "blue", "abcdef", "uvwxyz"], k = 2

Concatenate the consecutive strings of strarr by 2, we get:

treefoling   (length 10)  concatenation of strarr[0] and strarr[1]
folingtrashy ("      12)  concatenation of strarr[1] and strarr[2]
trashyblue   ("      10)  concatenation of strarr[2] and strarr[3]
blueabcdef   ("      10)  concatenation of strarr[3] and strarr[4]
abcdefuvwxyz ("      12)  concatenation of strarr[4] and strarr[5]

Two strings are the longest: "folingtrashy" and "abcdefuvwxyz".
The first that came is "folingtrashy" so 
longest_consec(strarr, 2) should return "folingtrashy".

In the same way:
longest_consec(["zone", "abigail", "theta", "form", "libe", "zas", "theta", "abigail"], 2) --> "abigailtheta"
```

<p align="justify">n being the length of the string array, if n = 0 or k > n or k <= 0 return "" (return Nothing in Elm).</p>


<strong>Note</strong>
<p align="justify">consecutive strings : follow one after another without an interruption</p>

<p align="justify">A partir de una arreglo como argumento para la función y un número K, se necesita retornar la primera cadena más larga que consta de k cadenas <strong>consecutivas</strong> tomadas del arreglo.</p>

<p align="justify">Para realizar este problema hay que tomar en cuenta unas cuantas cosas, como que las cadenas son consecutivas, el valor de k que es las particiones que haremos para unir las palabras y ver cual es la más larga.</p>

<p align="justify">Bien lo primero que hacemos es inicializar unas cuantas variables, un arreglo de strings que almacenará las uniones de las cadenas, otro arreglo de numeros que almacenará el largo de las cadenas unidas, y un indice que nos indicará donde se encuentra almacenado el número, con la  cantidad mas larga.</p>

<p align="justify">Luego validamos que si el largo del arreglo de entrada es igual a 0 o que si k osea el número de particiones es mayor al largo del arreglo de entrada o que si k osea el número de particiones es menor o igual a 0, que retorne una cadena vacia.</p>

<p align="justify">Después, con ciclo for recorremos el arreglo de entrada, y dentro del for preguntamos con un if, si la suma del indice i mas k es menor o igual al largo del arreglo, en caso de que sea verdad, agregaremos al arreglo de cadenas unidas un nuevo arreglo pero no solo eso, sino que dicho arreglo lo estamos conviertiendo en una cadena, osea en este punto se unen los elementos especificados con el método slice.</p>

<p align="justify">Luego de terminar de agregar todas las cadenas, hacemos uso de map en el arreglo de cadenas unidas, las cuales volverán a ser lamacenadas en un nuevo arreglo pero con la diferencia de que se retornará el largo de cada cadena, estas cantidades las almacenará el arreglo de números.</p>

<p align="justify">Ya casi terminando, le decimos al arreglo de números que me busque el indice del número mayor de su arreglo.</p>

<p align="justify">Por último, retornamos la cadena más larga que se encuentra en el arreglo de cadenas, y lo hacemos por medio del indice encontrado anteiormente. Quedando así la solución de la siguiente función:</p>

```typescript
export function longestConsec(strarr: string[], k: number): string {
  let cadenas: string[] = [],cadenas_n: number[] = [],indice: number;
  if (strarr.length === 0 || k > strarr.length || k <= 0) return "";
  for (let i = 0; i < strarr.length; i++) {
    if (i + k <= strarr.length)
      cadenas.push([...strarr.slice(i, i + k)].join(""));
  }
  cadenas_n = cadenas.map((e: string) => e.length);
  indice = cadenas_n.indexOf(Math.max(...cadenas_n));
  return cadenas[indice];
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```typescript
console.log(longestConsec(["tree", "foling", "trashy", "blue", "abcdef", "uvwxyz"], 2));
```

<p>Obteniendo como respuesta: <strong>'folingtrashy'</strong></p>

<a href="../README.md">Inicio</a>
