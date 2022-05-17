# Tuesday 10-05-2022

<ol>
    <li><strong>Checked the TypeScript Handbook</strong>💹</li>
    <li><strong> Type vs interface in TypeScript has been read</strong>💹</li>
    <li><a href='#tp_object'><strong>TypeScript Object Type exercise</strong></a></li>
    <li><a href='#tp_unions'><strong>TypeScript Unions exercise</strong></a></li>
</ol>

<a name="tp_object"></a>

## TypeScript Object Type exercise

### Ejercicio 1

<p align="justify">Se nos esta enseñando a como usar los tipos de objetos, hay tres maneras, pueden ser anónimos, por interfaces o de tipo alias</p>

### Anónimos

```typescript
function greet(person: { name: string; age: number }) {
  return "Hello " + person.name;
}
```

### Interfaces

```typescript
interface Person {
  name: string;
  age: number;
}
 
function greet(person: Person) {
  return "Hello " + person.name;
}
```

### Alias

```typescript
type Person = {
  name: string;
  age: number;
};
 
function greet(person: Person) {
  return "Hello " + person.name;
}
```

<p align="justify">En el primer ejercicio se nos solicito arreglar el tipo de Objeto, en este caso fue por Alias, quedando asi:</p>

```typescript
export type User = {
    name: string;
    age: number;
    occupation: string;
};

export const users: User[] = [
    {
        name: 'Max Mustermann',
        age: 25,
        occupation: 'Chimney sweep'
    },
    {
        name: 'Kate Müller',
        age: 23,
        occupation: 'Astronaut'
    }
];

export function logPerson(user: User) {
    console.log(` - ${user.name}, ${user.age}`);
}

console.log('Users:');
users.forEach(logPerson);
```

<a name="tp_unions"></a>

### Ejercicio 2

<p align="justify">Falta el tipo 'persona', definalo y utilicelo en la matriz de personas y la función logPerson para arreglar todos los errores de TS.</p>

Unions:
<p align="justify">Los tipos de unión nos permiten crear un nuevo tipo que puede tener un valor de uno o varios tipos más. Para crear un tipo de unión, tenemos que usar la |palabra clave. Con esto se soluciona el 2do ejercicio, ya que el arreglo de personas puede ser o la interface User o la interface Admin.</p>

 ```typescript
 interface User {
    name: string;
    age: number;
    occupation: string;
}

interface Admin {
    name: string;
    age: number;
    role: string;
}

export type Person = User | Admin;

export const persons: Person[]  = [
    {
        name: 'Max Mustermann',
        age: 25,
        occupation: 'Chimney sweep'
    },
    {
        name: 'Jane Doe',
        age: 32,
        role: 'Administrator'
    },
    {
        name: 'Kate Müller',
        age: 23,
        occupation: 'Astronaut'
    },
    {
        name: 'Bruce Willis',
        age: 64,
        role: 'World saver'
    }
];

export function logPerson(user: Person) {
    console.log(` - ${user.name}, ${user.age}`);
}

persons.forEach(logPerson);
 ```
 
 ### Ejercicio 3
 
<p align="justify">Corregir los errores de tipo logPerson, La función logPerson debe aceptar tanto al usuario como al administrador, y debe generar información relevante de acuerdo con la entrada: ocupación para Usuario y rol Admin.</p>

No entendi mucho, solo verificamos que 'role' este en el objeto de person osea => 'role' in person, y eso lo solucionaba todo, toca leer mas.

 ### Ejercicio 4

<p align="justify">Descubre como ayudar a TypeScript a comprender los tipos en esta situación y aplique las correciones necesarias.</p>

<p align="justify">Lo mismo que el ejercicio 3, solo que ahora preguntamos en diferentes if</p>

```typescript
export function logPerson(person: Person) {
    let additionalInformation: string = '';
    if ('role' in person) {
        additionalInformation = person.role;
    }
    if ('occupation' in person) {
        additionalInformation = person.occupation;
    }
    console.log(` - ${person.name}, ${person.age}, ${additionalInformation}`);
}
```

### Ejercicio 5

<p align="justify">Sin duplicar estructuras de tipos, modifique definición de la función filterUsers para que podamos pasar solo aquellos criterios que son necesarios, y no toda la información del usuario como es requerido ahora de acuerdo a escribir Mayor dificultad, excluir 'tipo' de los criterios de filtro.</p>

<a href="../README.md">Inicio</a>