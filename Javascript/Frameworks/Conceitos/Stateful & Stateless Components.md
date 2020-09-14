# Stateful & Stateless Components

Nos frameworks javascript as aplicações são feitas de **componentes**. Os componentes permitem que você possa dividir a UI em partes independentes, reutilizáveis e pensar em cada parte isoladamente. Você pode passar diferentes propriedades para um componente, que irá utilizar essas props e gerar uma saída. Esses componentes podem conter scoped states (estados que ficam dentro do componente), funções, lifecycle hooks e outras coisas.
Basicamente, o componente **stateful** contém um objeto state scoped e o **stateless** não. Esse conceito é relacionado ao de [Smart & Dumb Components](Smart%20&%20Dumb%20Components.md).

## Stateful Component
Um componente **stateful** armazena informações na memória sobre o estado da aplicação. Ele também tem a capacidade de alterá-lo. É essencialmente uma coisa “viva” que tem conhecimento das mudanças de estado passadas, atuais e futuras.

Algumas das características de um *stateful component* incluem:
- Conduz mudanças de estado por meio de funções
- Fornece dados
- Tem conhecimento vivo do estado atual
- É informado por componentes stateless quando algo precisa ser alterado
- Pode se comunicar com dependências externas
- Renderiza componentes filhos 

## Stateless Component
O componente **stateless** calcula seu estado interno, mas nunca o altera diretamente. Isso permite transparência referencial completa, o que significa que, dadas as mesmas entradas, sempre produzirá a mesma saída. Eles não são essencialmente “vivos”, pois são apenas informações transmitidas. Isso significa que não tem conhecimento das mudanças de estado passadas, atuais ou futuras.

Algumas das características de um *stateless component* incluem:
- Não realiza requests de dados
- Recebem dados por binding
- Emite dados através de event callbacks
- Pode renderizar outros componentes
  
**[WIP]**