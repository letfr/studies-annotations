## Classes

Uma classe define o comportamento de seus objetos através de métodos, e os estados possíveis destes objetos através de atributos.
Se você conhece alguma linguagem orientada a objetos como Java ou C#, já sabe como funciona o sistema de classes no Typescript. 

Declarando uma classe em Typescript:
```typescript
class Greeter {
  greeting: string;

  constructor(message: string) {
    this.greeting = message;
  }

  greet() {
    return "Hello, " + this.greeting;
  }
}

let greeter = new Greeter("world");
```

O **constructor** pode ser usado para retornar um valor para ser usado como instância da classe.

Um dos padrões fundamentais na programação baseada em classe é ser capaz de estender classes existentes para criar novas usando **herança**.

```typescript
class Animal {
  move(distanceInMeters: number = 0) {
    console.log(`Animal moved ${distanceInMeters}m.`);
  }
}

class Dog extends Animal {
  bark() {
    console.log("Woof! Woof!");
  }
}

const dog = new Dog();
dog.bark();
dog.move(10);
dog.bark();
```

## Modificadores de acesso

Os modificadores de acesso servem para restringir quem pode acessar cada elemento da sua classe. Existem três tipos de modificadores: 
  - **public** permite acesso de fora da classe; 
  - **private** - não permite o acesso de fora da classe;
  - **protected** - permite acesso apenas dentro da classe e suas classes derivadas;

**[WIP]**