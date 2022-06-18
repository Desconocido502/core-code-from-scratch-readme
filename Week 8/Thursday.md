# Thursday 02-06-2022

<ul>
  <li><strong>Generics exercise, using Typescript</strong></li>
  <li><strong>TicTacToe exercise, using Typescript</strong></li>
  <li><strong>6th Core Challenge, complete your Interview Prep Core Challenge 100% Completed.</strong></li>
</ul>

## Generics exercise, using Typescript

<p align="justify">Se usará una lista enlazada para implementar el ejemplo de génericos.</p>

<p align="justify">Al aplicar genericos, la ventaja es que podremos realizar una lista enlazada del tipo que queramos desde un tipo primitivo, como <i>number</i>, hasta objetos, en este caso el ejemplo será con números, y empezamos con la clase más independiente:</p>

### Clase Node

```typescript
export default class Node<T> {
  public data: T;
  public next: Node<T> | null = null;

  constructor(data: T) {
    this.data = data;
  }
}
```

<br />

Ahora, con la clase LinkedList:

```typescript
import Node from "./Node";
export default class LinkedList<T> {
  private head: Node<T> | null = null;
  private length: number = 0;

  get size(): number {
    return this.length;
  }

  public add(data: T) {
    if (this.head === null) {
      this.head = new Node(data);
    } else {
      let temp = this.head;
      while (temp.next !== null) {
        temp = temp.next;
      }
      temp.next = new Node(data);
    }
    this.length++;
  }

  public remove() {
    if (this.head !== null) {
      this.head = this.head.next;
      this.length--;
    }
  }

  public addFirst(data: T) {}

  public removeLast() {}

  public toString(): string {
    if (this.length === 0) return "[]";
    let data = "";
    let node = this.head;
    while (node !== null) {
      data = `${data}${node.data},`;
      node = node.next;
    }
    data = data.slice(0, -1);
    return `[${data}]`;
  }
}
```

<br />

### La clase Main:

```typescript
import Runnable from "./interfaces/Runnable";
import LinkedList from "./models/LinkedList";

export default class Main implements Runnable {
  start(): void {
    const l = new LinkedList<number>();
    // console.log(l.toString());
    l.add(1);
    l.add(2);
    l.add(3);
    l.add(4);
    l.addFirst(5);
    console.log(l.toString());
    console.log(l.size);
    l.remove();
    console.log(l.toString());
    console.log(l.size);
    l.removeLast();
    console.log(l.toString());
    console.log(l.size);
  }
}
```

<br />

Por último la clase principal:

### Clase Index

```typesript
import Main from "./Main";
const program = new Main();
program.start();
```

<br />

<p align="justify">Bien, se nos solicita que en la clase LinkedList, agreguemos los metodos de agregar al inicio, y eliminar al final, se presentan los métodos a continuación:</p>

### Método addFirst:

```typescript
public addFirst(data: T) {
    if (this.head === null) {
      this.head = new Node(data);
    } else {
      let temp = this.head;
      this.head = new Node(data);
      this.head.next = temp;
    }
    this.length++;
  }
```

<br />

### Método removeList:

```typescript
public addFirst(data: T) {
    if (this.head === null) {
      return null;
    } else {
      let aux = this.head;
      while (aux.next?.next) {
        aux = aux.next;
      }
      const temp = aux.next;
      aux.next = null;
      this.length--;
      return;
    }
  }
```

<p align="justify">Presentando a continuación los resultados tras agregar los anteriores métodos: </p>

```typescript
const l = new LinkedList<number>();
// console.log(l.toString());
l.add(1);
l.add(2);
l.add(3);
l.add(4);
l.addFirst(5);
console.log(l.toString());
console.log(l.size);
l.remove();
console.log(l.toString());
console.log(l.size);
l.removeLast();
console.log(l.toString());
console.log(l.size);
```

Salida en consola:

```code
[5,1,2,3,4]
5
[1,2,3,4]
4
[1,2,3]
```

<p align="justify">Con eso, completando el ejercicio con génericos.</p>


