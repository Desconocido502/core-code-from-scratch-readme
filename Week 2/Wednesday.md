# **Wednesday** 20-04-2022

<ul>
  <li><a href='#holiday'><strong>Holiday VIII - Duty Free exercise</strong></a></li>
  <li><a href='#old'><strong>Twice As Old exercise</strong></a></li>
  <li><a href='#spacing'><strong>Valid Spacing exercise</strong></a></li>
  <li><a href='#fake-binary'><strong>Fake Binary exercise</strong></a></li>
</ul>

<a name='holiday'></a>

## Holiday VIII - Duty Free exercise

<p align="justify">The purpose of this kata is to work out just how many bottles of duty free whiskey you would have to buy such that the saving over the normal high street price would effectively cover the cost of your holiday.</p>
<p align="justify">You will be given the high street price (normPrice), the duty free discount (discount) and the cost of the holiday.</p>
<p align="justify">For example, if a bottle cost £10 normally and the discount in duty free was 10%, you would save £1 per bottle. If your holiday cost £500, the answer you should return would be 500.</p>
<p align="justify">All inputs will be integers. Please return an integer. Round down.</p>

Función a completar

```javascript
function dutyFree(normPrice, discount, hol){

}
```

<p align="justify">Se nos solicita que a partir de tres valores (precio de venta, descuento sin impuestos, costo de vacaciones), obtengamos el calculo de cuántas botellas de whisky libre de impuesto se pueden comprar. Para ello evaluamos la situación.</p>

<p align="justify">Lo primero es entender que nos solicitan, y lo que se solicita es el calculo de ¿cuántas botellas de whisky se pueden compar?</p>
<p align="justify">¿Con que lo calculamos?, Se calcula con los datos ingresados, que son:</p>
<ul>
	<li>precio de venta</li>
	<li>descuento sin impuestos</li>
	<li>costo de vacaciones</li>
</ul>

<p>¿Cómo lo calculamos?</p> 
<ul>
	<li>Lo primero que se hace, es convertir el valor del impuesto en un porcentaje, se hace dividiendo el descuento sin impuestos dentro de 100.</li>
	<li>Luego se multiplica el porcentaje obtenido con el precio de venta  de la botella de whisky.</li>
	<li>Por último, el costo de las vacaciones se divide dentro de la multiplicación obtenida anteriormente. </li>
</ul>

<p align="justify">Así obteniendo, la siguiente función:</p>

```javascript
function dutyFree(normPrice, discount, hol){
  //hol/(normPrice*discount)
  return Math.floor(hol/(normPrice*(discount/100)));
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
dutyFree(24,35,3000)
```

<p>Obteniendo como respuesta: <strong>357</strong></p>

<a name='old'></a>

## Twice As Old exercise

Your function takes two arguments:

<ol>
	<li>current father's age (years)</li>
	<li>current age of his son (years)</li>
</ol>

<p align="justify">Сalculate how many years ago the father was twice as old as his son (or in how many years he will be twice as old).</p>

<p align="justify">Se nos solicita, a partir de dos argumentos (edad actual del padre, edad actual del hijo), obtener el valor de hace ¿cuántos años el padre tenía el doble de la edad del hijo?.</p>

Función a completar:

```javascript
function twiceAsOld(dadYearsOld, sonYearsOld) {
  // your code here
}
```

<p align="justify">¿Qué hay que calcular?, Hace cuantos años el padre tenia el doble de la edad que su hijo o dentro de cuantos años el padre tendrá el doble de la edad de su hijo.</p>

<ol>
	<li>Lo primero que se tiene que hacer es, multiplicar la edad del hijo por dos.</li>
	<li>Lo siguiente que se tendría que hacer es restar la edad del padre con el doble de la edad del hijo.</li>
</ol>

<p align="justify">Con esto, se obtiene la siguiente función:</p>

```javascript
function twiceAsOld(dadYearsOld, sonYearsOld) {
  return Math.abs(dadYearsOld-(sonYearsOld*2))
}
```

<p align="justify">Se hace uso del método abs, ya que, como lo indica el enunciado, hace cuantos años el padre tenia el doble de la edad que su hijo <strong>O</strong> dentro de cuantos años el padre tendrá el doble de la edad de su hijo.</p>

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
twiceAsOld(36,7)
```

<p>Obteniendo como respuesta: <strong>22</strong></p>

<a name='spacing'></a>

## Valid Spacing exercise

<p align="justify">Your task is to write a function called valid_spacing() or validSpacing() which checks if a string has valid spacing. The function should return either true or false (or the corresponding value in each language).</p>
<p align="justify">For this kata, the definition of valid spacing is one space between words, and no leading or trailing spaces. Words can be any consecutive sequence of non space characters. Below are some examples of what the function should return:</p>

Función a completar:

```javascript
function validSpacing(s) {
  // write your code here
}
```

<p align="justify">Se nos solicita, a partir de una cadena como argumento, que se verifique si una cadena tiene un espacio válido. La función debe devolver un true en caso de que la cadena sea válida con sus espaciados y false en caso de que la cadena no sea válida con sus espaciados. Para que la cadena sea válida, se tienen las siguientes validaciones:</p>

<ol>
	<li>No lleva espacios al inicio de la cadena</li>
	<li>No lleva espacios al final de la cadena</li>
	<li>Puede ser cualquier secuencia consecuiva de caracteres sin espacio</li>
	<li>No puede haber mas de un espacio por cada palabra en la cadena</li>
	<li>Si la cadena esta vacía es válida</li>
</ol>

<p align="justify">Tomando en consideración todo lo anterior, se realizan los pasos siguientesÑ</p>

<ul>
	<li>Si la cadena al inicio o al final tiene un espacio vacío retorna false</li>
	<li>Sino, se tendra que hacer un for que recorra la cadena</li>
	<li>Dentro del for verificar que no exista un espacio seguido de otro, si es así se retorna false</li>
	<li>En caso de que dentro del for no se encuentre un espacio seguido de otro, se retorna true</li>
</ul>

Obteniendo la siguiente función:

```javascript
function validSpacing(s) {
  if (s[0] === ' ' || s[s.length-1] === ' ') {
      return false;
  }else{
      for (var i = 0; i < s.length; i++) {
           if (s[i] === ' ' && s[i+1] === ' ') return false;
      }
      return true;
  }
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
validSpacing('Hello  world')
```

<p>Obteniendo como respuesta: <strong>false</strong></p>

<a name='fake-binary'></a>

## Fake Binary exercise

<p align="justify">Given a string of digits, you should replace any digit below 5 with '0' and any digit 5 and above with '1'. Return the resulting string.</p>
<p align="justify">Note: input will never be an empty string.</p>

Función a completar:

```javascript
function fakeBin(x){
}
```

<p align="justify">A partir de una cadena de digitos como argumento de la función, se nos pide retornar una cadena de 1´s y 0´s.</p>
<p align="justify">Cualquier digito que sea menor a 5 se le dará el valor de '0' en caso de que sea mayor o igual a 5 se le dará el valor de '1'.</p>

<p align="justify">Tomando en cuenta las validaciones anteriores, se obtiene la siguiente funcion:</p>

```javascript
function fakeBin(x){
    let falso_binario = ""
    for (var i = 0; i < x.length; i++) {
        if (x[i] < '5') {
            falso_binario += '0'
        }else{
            falso_binario += '1'
        }
    }
    return falso_binario
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(fakeBin('45385593107843568'))
```

<p>Obteniendo como respuesta: <strong>01011110001100111</strong></p>
<a href="../README.md">Inicio</a>