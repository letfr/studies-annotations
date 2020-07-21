# O que é Typescript? 

O TypeScript é um projeto [open-source](https://github.com/Microsoft/TypeScript) criado pela Microsoft e lançado em 2012. Foi criado para permitir a verificação de tipo estático opcional, que seria útil no desenvolvimento de aplicativos de grande escala. Um dos motivos pelos quais a Microsoft desenvolveu o TypeScript foi porque suas equipes internas estavam tendo problemas para escalar o JavaScript para os próprios projetos da Microsoft.
Depois que você compila seu código, todo o código Typescript desaparece e produz um código Javascript limpo e seguro para várias plataformas.

Os programas escritos em JavaScript não conhecem o tipo de dados de uma variável até que essa variável receba um valor em *tempo de execução*. A variável pode ser reatribuída ou coagida a um valor de um tipo diferente, sem problemas ou aviso. Isso pode resultar em erros que geralmente são ignorados, especialmente em aplicações grandes.
Já no Typescript, as variáveis ​​podem receber um tipo quando são *declaradas*, que é verificado em tempo de compilação e gera um erro se a variável receber um valor de um tipo diferente, apesar do erro não impedir a execução do código.

## Instalando Typescript

Existem duas maneiras principais de obter as ferramentas TypeScript:

- Via npm (o gerenciador de pacotes Node.js.)
- Instalando os plug-ins do Visual Studio do TypeScript

Para usuários do NPM:
```shell
  npm install -g typescript
```
### Criando seu primeiro arquivo TypeScript e compilando seu código

Crie um arquivo helloWorld.ts com o seguinte código:
```typescript
  function sayHello(name: string) {
    console.log(`Hello World! I'm ${name}!`)
  }

  sayHello('Leticia');
```

Apesar de usarmos uma extensão **.ts** no arquivo, esse código é apenas JavaScript.
Na linha de comando, execute o compilador TypeScript:
```shell
  tsc greeter.ts
```

Pronto! Seu primeiro código em TypeScript escrito e transpilado para JavaScript 🎉

## Tipando variáveis em Typescript 

Abaixo, atribuímos o tipo **string** para name e o tipo **number** para age.

```typescript
function greetings(name: string, age: number) {
  console.log(`Hi! My name is ${name} and I'm ${age}.`)
}
```

- Se chamarmos a função como **greetings('Leticia', '23')** o Typescript vai nos retornar o seguinte erro em tempo de compilação: 
```shell
  Argument of type '"23"' is not assignable to parameter of type 'number'.
```
Ainda assim, o arquivo JavaScript será criado e, quando executado exibirá no console:
> **Hi! My name is Leticia and I'm 23.**

- Se chamarmos a função como **greetings('Leticia')** o Typescript também nos retorna um erro em tempo de compilação, indicando que a função foi chamada com um número inesperado de argumentos: 
```shell
  Expected 2 arguments, but got 1.
  An argument for 'age' was not provided.
```
Se executarmos o arquivo Javascript gerado, o seguinte será exibido no console:
> **Hi! My name is Leticia and I'm undefined.**

## Interfaces

As interfaces definem propriedades, métodos e eventos, que são os membros da interface. As interfaces contêm apenas a declaração dos membros. É responsabilidade da classe derivada definir os membros. Muitas vezes, ajuda a fornecer uma estrutura padrão que as classes derivadas seguiriam.

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
