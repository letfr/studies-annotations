## Interfaces

As [interfaces](https://www.typescriptlang.org/docs/handbook/interfaces.html) definem propriedades, métodos e eventos, que são os membros da interface. As interfaces contêm apenas a **declaração** dos membros. É responsabilidade da classe derivada definir os membros. Muitas vezes, ajuda a fornecer uma estrutura padrão que as classes derivadas seguiriam.

```typescript
enum Gender {
  Male = 'Male',
  Female = 'Female',
};

interface Person {
  gender: Gender;
  heigth: number;
  weight: number;
  hairColor?: () => string;
};

const Leticia: Person = {
  gender: Gender.Female,
  heigth: 160,
  weight: '50kg',
  hairColor: 'Brown',
};
```

A const **Leticia** deriva da interface **Person**, que define o tipo de cada propriedade. Essa interface contém uma propriedade *gender*: **enum** (uma coleção de valores que podem ser numéricos ou de string), as propriedades *height* e *weight* : **number**, e a última *hairColor*: **string** como opcional.

- Ao definir a propriedade *weight* como uma string *'50kg'*, em tempo de compilação vamos receber o seguinte erro:
```shell
  Type 'string' is not assignable to type 'number'.
  The expected type comes from property 'weight' which is declared here on type 'Person'
```

Abaixo criamos uma const apenas contendo **height** e **weight**:
```typescript
const Leticia: Person = {
  heigth: 160,
  weight: 50,
};
```

A propriedade **hairColor** foi definida como opcional *(hairColor?: () => string;)*, mas teremos um erro na propriedade **gender** que está faltando:
```shell
  Property 'gender' is missing in type '{ heigth: number; weight: number; }' but required in type 'Person'.
```

**[WIP]**
