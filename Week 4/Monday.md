# Monday 02-05-2022

<ul>
    <li><a href="#for-of"><strong>Learned about for of loop</strong></a></li>
    <ul>
        <li><strong>for of video 💹</strong></li>
        <li><strong>for of examples 💹</strong></li>
    </ul>
    <li><a href="filter"><strong>Array Filter video viewed</strong></a></li>
    <li><a href="reduce"><strong>Array Reduce video viewed</strong></a></li>
    <li><a href="map"><strong>Array Map video viewed</strong></a></li>
    <li><a href="extras"><strong>Extras</strong></a></li>
</ul>

<a name='for-of'></a>

## Learn about for of loop

El for of, recorre valores iterables tales como un objeto iterable, funciona de mejor manera para recorrer arreglos.

<a name='filter'></a>

##  JavaScript Array Filter

<p align="justify">Recorre un arreglo y al mismo tiempo realiza una comprobación de alguna condición para devolver un nuevo arreglo.</p>

```javascript
const edad_personas = [24,17,35,21,7]
const adultos = personas.filter((persona) => persona > 18);
```

Salida:

```javascript
console.log(adultos); //[24,35,21]
```

<a name='reduce'></a>

## JavaScript Array Reduce

<p align="justify">Puede aplicar a una función un acumulador y a cada valor de un arreglo de izquierda a derecha, para <strong>reducirlo</strong> a un solo valor.</p>

```javascript
const suma = [10,20,30].reduce((a,b) => a + b);
```

Salida:
```javascript
console.log(suma); //60
```

<a name='map'></a>

## JavaScript Array Map

<p align="justify">Crea un nuevo arreglo, con los resultados de la llamada a la función indicada que se aplica a cada uno de sus elementos.</p>

```javascript
const numeros = [2,5,7];
const potencias = numeros.map((numero) => Math.pow(numero, 2));
```

Salida:
```javascript
console.log(potencias); //[4,25,49]
```

<a name='extras'></a>

## Extras:

<p align="justify">Algo que es bastante interesante es que se pueden 'concatenar' los métodos, y cuando me refiero a 'concatenar' es unir los métodos, al terminar uno de realizar su procedimiento, inmediatamente el otro empieza a realizar el suyo y devolver lo solicitado en dicha función.</p>

Un ejemplo de esto es el siguiente:

```javascript
const numbers = [1,-1,2,3];

const items = numbers
    .filter(n => n >= 0)
    .map(n => ({value: n}))
    .filter(obj => obj.value > 1)
    .map(obj => obj.value);
```

Salida:
```javascript
console.log(items); 
// 0 : 2
// 1 : 3
``` 

<p align="justify">A grandes rasgos, puede parecer algo confuso, pero en realidad no lo es tanto, lo primero que hacemos es, filtrar los números que sean mayor o igual a 0, descartando los números negativos del arreglo, seguidamente, el map se encarga de retonar un objeto literal al arreglo con los valores que cumplieron la condición de no ser números negativos, luego se vuelve a filtrar los objetos literales del arreglo, en los cuales su valor tiene que ser mayor a uno para poder ser nuevamente almacenador y por último, se llama a map para retornar únicamente sus valores, y no a la key, así solo almacenando los valores en el arreglo. Por ende al imprimir los datos del arreglo items, nos muestra:</p>

Salida:
```javascript
0 : 2
1 : 3
``` 

<a href="../README.md">Inicio</a>