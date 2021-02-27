# Imutabilidade

Basicamente, a imutabilidade é um conceito que diz: Um valor uma vez declarado, não pode ser alterado!
E acredite, esse simples conceito pode evitar uma série de bugs inesperados difíceis de detectar e raciocinar.
A imutabilidade torna o código mais fácil de ler. Quando os valores não podem mudar, o código é muito mais fácil de raciocinar.
Os dados **imutáveis** não podem alterar sua estrutura ou os dados nela contidos. É definir um valor em uma variável que não pode mudar, tornando esse valor um fato, ou uma espécie de fonte da verdade.
Objetos e arrays, por outro lado, permitem mutação, o que significa que a estrutura de dados pode ser alterada. 

## Tornando objetos imutáveis

Existe uma forma simples de tornar um objeto imutável utilizando **Object.freeze()**, evitando que as propriedades sejam alteradas, adicionadas ou removidas. 
Porém, existe um problema nessa abordagem. Essa função congela superficialmente o objeto, ignorando os objetos aninhados (nested). Para congelamento profundo, precisamos congelar *recursivamente* cada propriedade do tipo objeto, e para isso utilizamos **deepFreeze()**.

```js
function deepFreeze(object) {
  Object.keys(object).forEach(function freezeNestedObjects(name){
    const value = object[name];
      if(typeof value === "object") {
        deepFreeze(value);
      };
  });
  return Object.freeze(object);
}
```

## Desempenho

Sempre que você adiciona algo a um objeto imutável, precisamos criar uma nova instância, copiando os valores existentes e adicionando o novo valor a ela. Isso certamente exigirá mais memória e será mais desafiador do que a mutação de um único objeto.
Como os objetos imutáveis nunca mudam, eles podem ser implementados usando uma estratégia chamada *“compartilhamento estrutural”*, que produz muito menos sobrecarga de memória do que você poderia esperar. Ainda haverá uma sobrecarga em comparação com matrizes e objetos integrados, mas será constante e normalmente pode ser diminuída por outros benefícios habilitados pela imutabilidade. Na prática, o uso de dados imutáveis aumentará, em muitos casos, o desempenho geral do seu aplicativo, mesmo que certas operações isoladas se tornem mais caras.

## Funções puras

O conceito de funções puras é muito importante para a imutabilidade, na prática, podemos dizer que uma não existe sem a outra. As caracterícas que tornam uma função pura são:
- Dadas as mesmas entradas, sempre retornarão as mesmas saídas.
- Não produzem efeitos colaterais, ou seja, não afetam o escopo externo à função. Simplesmente retornam um valor.
- É agnóstica em relação ao escopo externo. Não se baseia em dados externos ao seu próprio escopo.

## Biblioteca Imutável

Mesmo utilizando freeze e deepFreeze, a aplicação ainda está sujeito a falhas em relação a imutabilidade e ao desempenho. É aí que entra o *Immutable.js*.
[Immutable.js](https://immutable-js.github.io/immutable-js/) é uma biblioteca criada pelo Facebook para trabalhar com estruturas de dados imutáveis, onde cada interação nas estruturas fornecidas não alteram, mas geram novas estruturas provenientes destas interações. Essa biblioteca nos fornece estruturas de dados imutáveis, como List, Stack, Map, OrderedMap, Set, OrderedSet e Record, que são estruturas de dados altamente otimizadas.

## Referências

- [Immutable.js](https://immutable-js.github.io/immutable-js/)
- [Learn immutability with JavaScript](https://medium.com/programming-essentials/learn-immutability-with-javascript-6a67e4a48d7f)
- [Por que Usamos Immutable.js](https://blog.getty.io/por-que-usamos-immutable-js-6ef85a4d4604)