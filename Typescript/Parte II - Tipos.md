
## Os tipos em TypeScript

Os tipos nos ajudam a melhorar a qualidade e a compreensibilidade do código, pois define os tipos de variáveis. Eles são opcionais e  defininem o que uma determinada variável deve ter como valor, assim permitindo ao compilador detectar erros antes do tempo de execução.

### Tipos básicos

Os tipos básicos são: 
- Boolean  
> O tipo de dado mais básico, sendo apenas **true** ou **false**.
- Number
> Tipo **number**, suporta decimais, hexadecimais, binários e octais.
- String
> O tipo **string** dão os dados de texto. Pode ser utilizado aspas duplas **(")**, aspas simples **(')** ou template string **(`)** para envolver os dados da string.
- Array
> O **array** é o tipo de matriz. Podem ser gravados de duas maneiras: utilizando **[]** ou **Array<tipoDoElement>**.
- Tuple
> O tipo **tuple** permitem definir uma matriz com um número fixo de elementos cujos tipos são conhecidos, mas não precisam ser os mesmos. 
- Enum
> O **enum** é um tipo que permite atribuir nomes mais amigáveis a conjuntos de valores numéricos. Por padrão, os enums começam a numerar seus membros a partir de 0. Você pode alterar isso definindo manualmente o valor de um de seus membros.
- Any
> O tipo **any** pode ser utilizados quando não conhecemos o tipo de variável que podemos receber. Um exemplo disso é quando recebemos esse valor de uma biblioteca terceira. Nesses casos, queremos desativar a verificação de tipo e deixar que os valores passem pelas verificações em tempo de compilação sem erros.
- Void
> O tipo **void** é a ausência de ter qualquer tipo. Geralmente é usado como o tipo de retorno de funções que não retornam um valor.
- Null and Undefined
> Como o nome já diz, **null** é o tipo nulo e **undefined** é o tipo indefinido. 
- Never
> O tipo **never** representa o tipo de valores que nunca ocorrem.
- Object
> O **object** é um tipo que representa o tipo não primitivo, ou seja, qualquer coisa que não seja *number, string, boolean, bigint, symbol, null, or undefined*.

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
