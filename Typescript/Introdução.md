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
## Criando seu primeiro arquivo TypeScript e compilando seu código

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
  tsc helloWorld.ts
```

Pronto! Seu primeiro código em TypeScript escrito e transpilado para JavaScript 🎉

## Configurando o TypeScript com tsconfig

Você pode configurar o TypeScript utilizando um arquivo JSON [tsconfig](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html), que pode te ajudar a controlar o comportamento do compilador. 
Para criar o arquivo de configuração, você precisa criar um novo diretório e na raiz da pasta através do terminal execute o comando para gerar um novo arquivo de configuração TypeScript.

```shell
  tsc --init
```

Será gerado um arquivo *tsconfig.json* com uma propriedade **compilerOptions** com várias propriedades e comentários, em frente a cada propriedade está a explicação da finalidade daquele campo.  

```shell
  "target": "es5", /* Specify ECMAScript target version: 'ES3' (default), 'ES5', 'ES2015', 'ES2016', 'ES2017', 'ES2018', 'ES2019' or 'ESNEXT'. */
  "outDir": "public/js", /* Redirect output structure to the directory. */
```

A propriedade **target** especifica a versão do ECMAScript a ser utilizada para compilação. Como padrão, ele define a versão **ES3**, mas você pode definir **"ES5"** por exemplo. Já **"outDir"** define o diretório de saída do código compilado, ou seja, a pasta que você quer que a saída JavaScript fique.
Dessa forma, você pode definir vários comportamentos para o seu compilador TypeScript, funcionando melhor para sua necessidade.
Nesse [link](https://www.typescriptlang.org/docs/handbook/compiler-options.html) você pode ver a lista completa de opções para o compilador. 

