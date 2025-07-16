- Directed (A → B): only A holds B.

```ts
import { Child } from "./child";

export class Parent {
  private child!: Child;
  setChild(c: Child) {
    this.child = c;
  }
  notifyChild() {
    this.child.doSomething();
  }
}
```

```mermaid
classDiagram
  class Parent {
    +setChild(c: Child): void
    +notifyChild(): void
  }
  class Child {
    +doSomething(): void
  }
  Parent --> Child
```

- Bidirectional (A ↔ B): each holds a reference to the other

```ts
// node.ts
export class Node {
  constructor(public name: string) {}
  neighbors: Node[] = [];
}

// usage
const a = new Node("A");
const b = new Node("B");
a.neighbors.push(b);
b.neighbors.push(a);
```

```mermaid
classDiagram
  class Node {
    +name: string
    +neighbors: Node[]
  }

  class Node1~Node~
  class Node2~Node~

  Node1 "0..*" <--> "0..*" Node2 : neighbors
```
