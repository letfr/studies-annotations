# Reatividade

O React e o Vue.js são exemplos de frameworks reativos. Mas afinal, o que é reatividade? Esses frameworks reativos monitoram as mudanças nas propriedades e a página **reage** automaticamente às mudanças. Quando uma propriedade é alterada, reagem apenas os componentes que dependem dela. Assumindo que a página Web seja desenvolvida seguindo uma hierarquia de componentes, a mudança de uma propriedade afeta uma porção muito pequena da página, e a detecção de mudanças só precisa verificar aquela parte.
No seu código, **eventos** como clique, chamadas HTTP ou alterações de variável, tem um efeito colateral em sua aplicação: ela se torna *assíncrona*. 

## Observer Pattern

Em resumo, o padrão **Observer** oferece um modelo de assinatura *(subscribe)* no qual os objetos assinam um evento e são notificados quando o evento ocorre. Esse padrão é a base da *programação orientada a eventos*, incluindo JavaScript. 
*Observers* também são capazes de cancelar a assinatura do observador e emitir erros.
Os *Subscribers* consomem/observam os dados transmitidos. Eles também recebem os erros e eventos de conclusão do Observable.
Os *Operators* são usados para criar observáveis (timers, ranges), para transformar observáveis (map, buffer, group, scan, etc), para filtrar (filter, distinct, skip, debounce, etc), para combinar (zip, merge, combine latest, etc).
*Schedulers* nos permitem adicionar facilmente threading aos nossos Observers e Subscribers.


## RxJs

RxJS é uma [biblioteca javascript](https://rxjs-dev.firebaseapp.com) para compor programas assíncronos e baseados em eventos usando **observáveis**. Ele fornece um tipo de núcleo, o Observable, tipos de satélite (Observer, Schedulers, Subject) e operadores como map, filter, reduce, every, etc para permitir o tratamento de eventos assíncronos como coleções.
Os conceitos essenciais em RxJS que resolvem o gerenciamento de eventos assíncronos são:

- **Observable**: representa a ideia de uma coleção invocável de valores ou eventos futuros.
- **Observer**: é uma coleção de callbacks que sabem ouvir os valores entregues pelo Observable.
- **Subscription**: representa a execução de um Observable, é principalmente útil para cancelar a execução.
- **Operators**: são funções puras que permitem um estilo de programação funcional de lidar com coleções utilizando map, filter, concat, reduce, etc.
- **Subject:**: é o equivalente a um EventEmitter e a única forma de multicast de um valor ou evento para vários Observers.
- **Schedulers**: são despachantes centralizados para controlar a simultaneidade, permitindo-nos coordenar quando a computação acontece, por exemplo, setTimeout ou requestAnimationFrame ou outros.


## Mas e aí, vale a pena usar programação reativa?

Esse pattern pode ser muito útil nos dias de hoje! Estamos em um momento no qual temos um grande fluxo de dados em nossas aplicações. Os usuários querem os dados com rapidez. As aplicações assíncronas desempenham um importante papel nesse contexto. A programação reativa vai tornar o trabalho assíncrono com fluxo de dados mais simples, uma threading complexa mais fácil de lidar, além de utilizar operadores que facilitam e tornam o código limpo e legível. 

### Referências

- [RxJs](https://rxjs-dev.firebaseapp.com)
- [Programação Reativa - @ljtfreitas](https://elo7.dev/programacao-reativa-parte-2/)
- [Programação Reativa](https://epxx.co/artigos/reativo.html)
- [Observer Pattern](https://www.dofactory.com/javascript/design-patterns/observer)
- [Why you should learn Reactive Programming](https://medium.com/corebuild-software/why-you-should-learn-reactive-programming-51b6ffc31425)
