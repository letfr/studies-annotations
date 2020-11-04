# Reatividade

O React e o Vue.js são exemplos de frameworks reativos. Esses frameworks monitoram as mudanças nas propriedades e a página reage automaticamente às mudanças. Quando uma propriedade é alterada, reagem apenas os componentes que dependem dela. Assumindo que a página Web seja desenvolvida segundo uma hierarquia de componentes, tipicamente a mudança de uma propriedade afeta uma porção muito pequena da página, e a detecção de mudanças só precisa verificar aquela porção. O estado da UI é uma função pura das propriedades, e o estado da UI é sempre consistente em relação às propriedades. O desenvolvedor ocupa-se de "o que deve ser mostrado", não de "como mostrar".
No seu código, eventos como clique, chamadas HTTP ou alterações de variável, tem um efeito colateral em sua aplicação: ela se torna assíncrona. 

## RxJs
RxJS é uma biblioteca para compor programas assíncronos e baseados em eventos usando **observáveis**. Ele fornece um tipo de núcleo, o Observable, tipos de satélite (Observer, Schedulers, Subject) e operadores como map, filter, reduce, every, etc para permitir o tratamento de eventos assíncronos como coleções.

**[WIP]**