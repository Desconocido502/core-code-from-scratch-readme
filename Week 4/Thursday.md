# Thursday 05-05-2022

<ul>
    <li><a href='#str'><strong>String Cleaning exercise</strong></a></li>
    <li><a href='#password'><strong>Password Validation exercise</strong></a></li>
    <li><strong>Complete your 2nd Core Challenge - 100% Completed 💹</strong></li>
</ul>

<a name="str"></a>

## String Cleaning exercise

<p align="justify">Your boss decided to save money by purchasing some cut-rate optical character recognition software for scanning in the text of old novels to your database. At first it seems to capture words okay, but you quickly notice that it throws in a lot of numbers at random places in the text.</p>

<p align="justify">Se nos soclicita que a partir de una cadena de texto como parámetro, se retorne dicha cadena excluyendo cualquier número encontrado en la cadena de texto. Para esto podemos reutilizar la regex que utilizamos en la anterior kata, la cual sería:</p>

<p align="center">/\d+/g</p>

<p align="justify">Se uso la bandera g, que nos proporciona JavaScript, para indicar que sea una búsqueda global, osea sobre toda la cadena de texto que se encontrará bajo análisis, explicando la regex, se tiene:</p>
<ul>
	<li>0-9: Digitos del 0 al 9, ejemplo: 502</li>
	<li>+: Un cuantificador que indica que puede venir una o más veces alguna regex o algún carácter.</li>
</ul>

Completando la función, queda lo siguiente:

```javascript
function stringClean(s) {
  return s.replace(/\d+/g,'');
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(stringClean('My \"me3ssy\" d8ata issues2! Will1 th4ey ever, e3ver be3 so0lved?'));
```

<p>Obteniendo como respuesta: <strong>'My "messy" data issues! Will they ever, ever be solved?'</strong></p>

<a name="password"></a>

## Password Validation exercise

<p align="justify">You need to write regex that will validate a password to make sure it meets the following criteria:</p>

<ul>
	<li>At least six characters long</li>
	<li>contains a lowercase letter</li>
	<li>contains an uppercase letter</li>
	<li>contains a number</li>
</ul>

<p align="justify">Valid passwords will only be alphanumeric characters.</p>

<p align="justify">Bien se nos solicita que a partir de una cadena como entrada (parámetro), se valide que la cadena sea una contraseña válida, y nos pide requisitos para que sea válida, tiene que tener al menos 6 carácteres, debe contener una letra minúscula, una mayúscula, y contiene un número, además de las contraseñas solo serán validas con carácteres alfanuméricos únicamente. Para estos casos se prefirió hacer las 3 validaciones aparte y la validación de al menos 6 carácteres, obteniendo la siguiente función:</p>

```javascript
function validate(password) {
  return /^\w{6,}$/.test(password) 
  && /[a-z]{1}/.test(password) 
  && /[A-Z]{1}/.test(password)
  && /\d{1}/.test(password);
}
```

<p align="justify">Realizando una prueba se obtiene lo siguiente:</p>

```javascript
console.log(validate('Password123'));
```

<p>Obteniendo como respuesta: <strong>true</strong></p>
<a href="../README.md">Inicio</a>