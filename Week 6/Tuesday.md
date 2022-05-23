# Tuesday 17-05-2022

<ul>
  <li><a href="#rule"><strong>A Rule Of Divisibility By 13 exercise, using Typescript</strong></a></li>
  <li><a href="#playing"><strong>Playing With Digits exercise, using Typescript</strong></a></li>
  <li><a href="#valid"><strong>Valid Braces exercise, using Typescript</strong></a></li>
  <li><a href="#ttt-1"><strong>Tic-Tac-Toe exercise, using Javascript</strong></a></li>
  <li><a href="ttt-2"><strong>Tic-Tac-Toe-Like Table Generator exercise, using Javascript</strong></a></li>
</ul>

<a name="rule"></a>

##  A Rule Of Divisibility By 13 exercise, using Typescript
  
From Wikipedia:
<p align="justify">"A divisibility rule is a shorthand way of determining whether a given integer is divisible by a fixed divisor without performing the division, usually by examining its digits."</p>
<p align="justify">When you divide the successive powers of 10 by 13 you get the following remainders of the integer divisions:</p>
  
1, 10, 9, 12, 3, 4 because:
  
```code
10 ^ 0 ->  1 (mod 13)
10 ^ 1 -> 10 (mod 13)
10 ^ 2 ->  9 (mod 13)
10 ^ 3 -> 12 (mod 13)
10 ^ 4 ->  3 (mod 13)
10 ^ 5 ->  4 (mod 13)
```
  
<p align="justify">Se nos solicita que a partir de un argumento el cual seria un número devolvamos un número estacionario.</p>
  
<p align="justify">Dicho problema es un tanto complejo ya que se tuvo que hacer uso de recursividad, para poder solucionarlo.</p>
  
<p align="justify">Se hizo uso de una función complementaria, para realizar el cálculo correcto de la función principal.</p>
  
<p align="justify">Entrando en detalle, se necesita un arreglo que contendria los números divisores de la potencia de 10 mod 13, y este arreglo seria tan largo como sea el numero de entrada en la función principal, retornando un arreglo.</p>
  
<p align="justify">La misma función principal será la que usará la recursividad directamente, ya que se le pasa el número como parámetro, en este punto aplicamos varios métodos propios de js, como toString, para convertir el número a string, split, para volver la cadena en un arreglo de strings, map, para retornar un nuevo arreglo en el cual se parsean los string a números enteros y por último aplicamos un reverse para darle la vuelta al arreglo.</p>
  
<p align="justify">Luego de esto, se manda a llamar a la función complementaria, a la cual se le manda el largo del arreglo de números menos uno, esto debido a los indices, y declaramos y asignamos un indice en 0.</p>
  
<p align="justify">Después, aplicamos un reduce del arreglo de números al cual se le devuelve la suma de la multiplicación del arreglo de la función complementaria y el arreglo de números.</p>
  
<p align="justify">Al terminar el proceso, quedará un solo número, este será el resultado, y preguntamos si el resultado es igual al número ingresado a la función principal, en caso de que lo sea, retorna el número ya que sería estacionario, en caso contrario, le devolvera la función principal con el resultado obtenido como argumento ya que el número ingresado no es igual al obtenido en pocas palabras no seria estacionario, y es por esa razón que se vuelve a llamar a la función principal de nuevo.</p>
  
<p align="justify">Con dicha información realizamos la siguiente función complementaria en TypeScript:</p>
  
Función complementaria:
  
```typescript
function divisors(large:number): number[]{
  let divisors: number[] = [];
  for (let i = 0; i <= large; i++) {
    divisors.push(10**i % 13);
  }
  return divisors;
}
```
  
<p align="justify">Ahora la  función principal en TypeScript:</p>
  
```typescript
function thirt(n: number): number {
  let x = n.toString().split("").map(e => parseInt(e)).reverse();
  let d = divisors(x.length-1), i = 0;
  let r = x.reduce((pv:number,cv:number) => pv + cv*d[i++],0);
  if (r === n) return r
  return thirt(r);
}
```
  
Juntando ambas se tiene:
  
```typescript
function divisors(large:number): number[]{
  let divisors: number[] = [];
  for (let i = 0; i <= large; i++) {
    divisors.push(10**i % 13);
  }
  return divisors;
}
  
function thirt(n: number): number {
  let x = n.toString().split("").map(e => parseInt(e)).reverse();
  let d = divisors(x.length-1), i = 0;
  let r = x.reduce((pv:number,cv:number) => pv + cv*d[i++],0);
  if (r === n) return r
  return thirt(r);
}
```
  
<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>
  
```typescript
console.log(thirt(85299258));
```
  
<p>Obteniendo como respuesta: <strong>31</strong></p>

<a name="playing"></a>

##  Playing With Digits exercise, using Typescript
  
  
<p align="justify">Some numbers have funny properties. For example:</p>
  
```code
"89 --> 8¹ + 9² = 89 * 1"
  
"695 --> 6² + 9³ + 5⁴= 1390 = 695 * 2"
  
"46288 --> 4³ + 6⁴+ 2⁵ + 8⁶ + 8⁷ = 2360688 = 46288 * 51"
```
  
<p align="justify">Given a positive integer n written as abcd... (a, b, c, d... being digits) and a positive integer p</p>
  
<p align="justify">we want to find a positive integer k, if it exists, such that the sum of the digits of n taken to the successive powers of p is equal to k * n.</p>
  
In other words:
```code
"there an integer k such as : (a ^ p + b ^ (p+1) + c ^(p+2) + d ^ (p+3) + ...) = n * k"
```
  
<p align="justify">If it is the case we will return k, if not return -1.</p>
  
<p align="justify">Note: n and p will always be given as strictly positive integers.</p>
  
<p align="justify">Se nos solicita que a partir de dos argumentos devolvamos un número entero, en si el problema se trata acerca de números que tienen algunas propiedades divertidas, en tal caso el número con propiedades divertidas no es mas que al sumar los digitos del numero con una potencia sucesiva nos da el mismo número multiplicado k veces.</p>
  
<p align="justify">De forma importante, queremos llegar a lo siguiente <br/> Existe un número entero k como: (a ^ p + b ^ (p+1) + c ^(p+2) + d ^ (p+3) + ...) = n * k</p>
  
<p align="justify">Bien para solucionarlo, se hizo de los siguientes métodos que nos ofrece el lenguaje:</p>
  
<ul>
  <li>toString: Método que castea un número a string.</li>
  <li>split: Método que vuelve una cadena en un arreglo de strings</li>
  <li>map: Crea un arreglo nuevo a partir del arreglo original, con las directrices indicadas en una función.</li>
  <li>reduce: Método que reduce un arreglo a un número con las directrices indicadas en una función.</li>
  <li>Math.floor: Redondea un valor decimal a su parte baja, retornando un entero.</li>
</ul>
  
<p align="justify">Ya con esto, procedemos a la explicación mas general, en la cual realizamos un casteo de entero a string a la variable n, luego de esto aplicamos split para que se vuelva un arreglo de strings, cada elemento seria un digito, luego aplicamos un map, en donde convertimos cada elemento a un entero y lo elevamos a la potencia indicada en la variable p, por cada vuelta realizada el valor de p aumenta en uno, y por último aplicamos un reduce al arreglo, quedandonos un solo número.</p>
  
<p align="justify">Ahora a la variable k, que fue previamente declarada al inicio de la función se el asigna la división del número obtenido anteriormente divido entre la variable n que sería el primer número de entrada. Por último se valida que si x osea el primer número de entrada es igual a la múltipliación de la variable k por la variable n, retorne el valor de K, esto quiere decir que el valor de x es igual al valor de la variable n multiplicado K veces, en caso contrario, retorne -1.</p>
  
<p align="justify">Con dicha información realizamos la siguiente función en TypeScript:</p>
  
Función completa:
```typescript
export class G964 {
  public static digPow = (n: number, p: number) => {
    let k:number,x = n
      .toString()
      .split("")
      .map((e: string) => parseInt(e) ** p++)
      .reduce((pv:number, cv:number) =>  pv + cv,0);
    k = Math.floor(x/n);
    if(x === k*n) return k
    return -1;
  };
}
```
  
<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>
  
```typescript
console.log(operacion.digPow(46288, 3));
```
  
<p>Obteniendo como respuesta: <strong>51</strong></p>

<a name="valid"></a>

##  Valid Braces exercise, using Typescript
  
  
<p align="justify">Write a function that takes a string of braces, and determines if the order of the braces is valid. It should return true if the string is valid, and false if it's invalid.</p>
  
<p align="justify">This Kata is similar to the Valid Parentheses Kata, but introduces new characters: brackets [], and curly braces {}. Thanks to @arnedag for the idea!</p>
  
<p align="justify">All input strings will be nonempty, and will only consist of parentheses, brackets and curly braces: ()[]{}.</p>
  
<h5>What is considered Valid?</h5>
<p align="justify">A string of braces is considered valid if all braces are matched with the correct brace.</p>
  
<p align="justify">Se desea validar los brackets "()", "{}", "[]", un nivel mas elevado ya que anteiormente se habian validado solamente los paréntesis, haciendo uso de una pila, ahora seguiremos haciendo usao de nuestra valiosa pila.</p>
  
<p align="justify">Haremos uso de un for-of en vez de un while o de un for normal, ya que el for-of nos ayudará a iterar en cada elemento de la cadena, se declara la pila como un arreglo de strings, y se declara s, como string o undefined, s nos ayudará a comprobar cualquiera de las brackets mencionadas anteriormente.</p>
  
<p align="justify">Dentro del for-of preguntamos si la letra en la i-ésima posición es igual a un paréntesis o si es igual la una llave o si es igual a un corchete, en caso de que sea cualquiera de esas tres opciones se agrega a la pila.</p>
  
<p align="justify">En caso de que la pila se quede vacia se retorna falso, luego de esto usamos la sentencia switch:</p>
  
<ul>
  <li><p align="justify">En el caso de que brace sea igual a ")", se desapila el último valor en la pila y se asigna a 's', y preguntamos si s es igual a "{" o si s es igual a "[", en caso de que uno de estos sea verdadero, se deberá retornar falso, ya que se esperaba que el valor de s fuera "(", osea el par que abre de la brace que cierra. en caso de que si sea simplemente desapila la brace y hace un break.</p></li>
  <li><p align="justify">En el caso de que brace sea igual a "}", se desapila el último valor en la pila y se asigna a 's', y preguntamos si s es igual a "(" o si s es igual a "[", en caso de que uno de estos sea verdadero, se deberá retornar falso, ya que se esperaba que el valor de s fuera "{", osea el par que abre de la brace que cierra. en caso de que si sea simplemente desapila la brace y hace un break.</p></li>
  <li><p align="justify">En el caso de que brace sea igual a "]", se desapila el último valor en la pila y se asigna a 's', y preguntamos si s es igual a "{" o si s es igual a "(", en caso de que uno de estos sea verdadero, se deberá retornar falso, ya que se esperaba que el valor de s fuera "]", osea el par que abre de la brace que cierra. en caso de que si sea simplemente desapila la brace y hace un break.</p></li>
</ul>
  
<p align="justify">Con dicha información realizamos la siguiente función en TypeScript:</p>
  
Función completa:
```typescript
export function validBraces(braces: string): boolean {
  let pila: string[] = [], s:string | undefined;
  for (const brace of braces) {
    if (brace === "(" || brace === "{" || brace === "[") pila.push(brace);
  
    if (pila.length === 0) return false;
  
    switch (brace) {
      case ")":
        s = pila.pop();
        if (s == "{" || s == "[") return false;
        break;
      case "}":
        s = pila.pop();
        if (s == "(" || s == "[") return false;
        break;
      case "]":
        s = pila.pop();
        if (s == "{" || s == "(") return false;
        break;
    }
  }
  return pila.length ? false : true;
}
```
  
<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>
  
```typescript
console.log(validBraces("[({})](]"));
```
  
<p>Obteniendo como respuesta: <strong>false</strong></p>

<a name="ttt-1"></a>

##  Tic-Tac-Toe exercise, using Javascript
  
  
<p align="justify">Implement a Tic-Tac-Toe (AKA: Noughts and crosses, Xs and Os) solver. The input to the solver function will be an array of length 9 representing the board. Output of the function will be the index of the desired move (0-8). You will always be X. You must make a valid move, and a winning move if available.</p>
  
The board is represented as an array with the following indexes:
  
<p align="center"><code>
 0 | 1 | 2 <br/>
---+---+--- <br/>
 3 | 4 | 5 <br/>
---+---+--- <br/>
 6 | 7 | 8 <br/>
</code></p>
  
Valid outputs for the above input would be 0, 1, 2, 4, 5, 7 or 8.
  
<p align="justify">The following board would only have 1 correct output (2) because it is the only move that connects 3 X's in a row:</p>
  
```code
solveTTT(['O', '', '', 'O', 'X', '', 'X', 'O', 'X'])
```
Faltan los problemas 4 y 5, 4 inconcluso y 5 no leido

<a name="ttt-2"></a>

<a href="../README.md">Inicio</a>
