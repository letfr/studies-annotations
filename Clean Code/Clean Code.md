# Clean code segundo Uncle Bob

O livro Clean Code: A Handbook of Agile Software Craftsmanship escrito por Robert C. Martin, também conhecido como Uncle Bob nos ensina sobre a importância de escrever código limpo e com qualidade e nos dá várias sugestões incríveis de como fazer isso. 
É extremamente importante manter em mente que estamos escrevendo código que será lido por outras pessoas. Um  código limpo deve ser compreensível, simples e direto. Assim, tarefas como adicionar uma nova funcionalidade ou refatoração serão simples.
Além disso, você deve dedicar um tempo extra para definir a arquitetura e o padrão do seu código.

## "A duplicação é o principal inimigo de um sistema bem projetado."

Utilize o princípio *DRY - Don’t repeat yourself* (Não repita a si mesmo). 
Um código duplicado não garante que as instâncias repetidas serão modificadas quando uma alteração for feita, além de impactar no desempenho da aplicação.

## "Uma classe deve ter somente uma razão para mudar"

Um dos princípios SOLID é *SRP — Single Responsibility Principle* (Princípio da Responsabilidade Única).
Esse princípio declara que uma classe deve ser especializada em um único assunto e possuir apenas uma responsabilidade. 
Isso permite que os testes automatizados sejam mais fáceis de implementar e que o código seja reutilizável. 

## "Você deve nomear uma variável usando o mesmo cuidado com o qual nomeia um filho primogênito."

É essencial nomear variáveis, funções, parâmetros, classes ou métodos de acordo com suas funcionalidades, de forma direta, possibilitando um bom entendimento do que se trata.
É preciso passar, de forma direta, a ideia central da variável ou método. Lembre-se de que um nome descritivo longo é melhor que um nome enigmático curto.

## "Se não for testado, está quebrado"

Utilizar *TDD - Test Driven Development* (Desenvolvimento Orientado por Testes) no seu projeto vai assegurar que seu código tenha qualidade e confiabilidade. Mas, seu teste deve ser limpo também.
- Os testes devem ser rápidos. Quando os testes são lentos, você não deseja executá-los com frequência. 
- Os testes não devem depender um do outro. Um teste não deve configurar as condições para o próximo teste. Você deve poder executar cada teste independentemente e executar os testes na ordem que desejar.
- Certifique-se de escrever testes apenas para um único conceito. Fazer muitas coisas em um teste geralmente é um sinal de que precisa ser quebrado.

## Ferramentas

Existem algumas ferramentas que podem te ajudar no momento de escrever código limpo. Para javascript, por exemplo, podemos utilizar o [ESLint](https://eslint.org/) para identificar e relatar padrões, o [Husky](https://www.npmjs.com/package/husky) para previnir commits ruins, e diversas [extensões para VSCode](https://marketplace.visualstudio.com/VSCode). 

Alguns artigos que podem te ajudar na hora de escrever um código limpo:

[TDD changed my life](https://medium.com/javascript-scene/tdd-changed-my-life-5af0ce099f80)
[These tools will help you write clean code](https://medium.com/free-code-camp/these-tools-will-help-you-write-clean-code-da4b5401f68e)
[S.O.L.I.D: The first five principles of object oriented design](https://www.digitalocean.com/community/conceptual_articles/s-o-l-i-d-the-first-five-principles-of-object-oriented-design)

**[WIP]**