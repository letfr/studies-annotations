# Smart & Dumb Components

## Dumb Components
O *"Dumb component"* também conhecido como *"Presentational component"* tem a responsabilidade única de apresentar algo ao DOM. Nada mais. Esses componentes apenas renderizam as props que são passadas no DOM e não tem nenhum state interno para administrar. Esse tipo de componente é altamente reutilizável, uma vez que, você só precisa enviar as props e poderá utilizar o mesmo componente em diversas partes do código com conteúdo totalmente diferente.

```js
<template>
  <header>
    <h1>{{ title }}</h1>
  </header>
</template>

<script>
export default {
  name: 'Header',
  props: {
    title: {
      type: String,
      required: true,
    },
  },
};
</script>
```

Algumas das características dos Dumb Components são:
- Foco na UI. Geralmente loaders, modals, buttons e inputs são exemplos de dumb components.
- Recebem props para permitir que sejam dinâmicos e reutilizáveis.
- Não faz import dependências.

## Smart Components
Os *Smart components* ou *Container components* controlam states e se preocuparam com o funcionamento da aplicação. O smart component faz o trabalho pesado e passa os dados para o dumb component. Esses componentes também costumam conter outras funções de retorno de chamada que são usadas para atualizar o estado e são passadas para seus componentes filhos como props.

```js
<template>
  <div>
    <button @click="active = !active">{{ dropdownTitle }}</button>
    <div v-if="active" class="dropdown__menu">
      <ul class="dropdown__menu-nav">
        <li v-for="title in menuList" :key="title" class="dropdown__menu-item">
          {{ title }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Dropdown',
  props: {
    dropdownTitle: {
      type: String,
      required: true,
    },
    menuList: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      active: false,
    };
  },
};
```

O componente raiz de um aplicativo é um bom exemplo de **smart component**. Muitas vezes, é responsável por manter várias partes do estado de todo o aplicativo e precisa transmitir funções adicionais aos componentes filhos para que o estado possa ser atualizado quando um usuário interagir com a aplicação.

Algumas das características dos Smart Components são:
- Manipulam dados. Os smart components podem buscar, capturar alterações e transmitir dados da aplicação.
- Utiliza lifecycle hooks, APIs, bibliotecas.
- Gerencia state e sabe quando renderizar novamente um componente.

## Benefícios desta abordagem
Ao utilizar a abordagem de **smart and dumb components** você obtém algumas vantagens:

### Separação de interesses.
Ao separar os componentes dessa maneira, cada tipo de componente lida com uma responsabilidade diferente. Enquanto o *dumb component* lida com a UI, o *smart component* lida com o funcionamento do app. Assim, o entendimento da aplicação é intuitivo.

### Reutilização
Você pode usar o mesmo *dumb component* com props completamente diferentes em diversas partes da sua aplicação, evitando duplicação de código e seguindo o conceito de **DRY** (Don't repeat yourself).

### Flexibilidade
A refatoração se torna mais simples utilizando essa separação de componentes. No caso do *dumb component*, você só precisa fazer a mudança em apenas um arquivo, e todos os lugares onde utiliza esse componente vão refletir a mudança. Se a mudança é do funcionamento da aplicação, você saberá que precisa mudar um *smart component*. 

### Legibilidade do código
Quanto menos código você tiver por arquivo e mais organizado for o seu código, mais fácil será não apenas para você entender seu código, mas para os outros entenderem o que está acontecendo.

### Testes unitários
Os *dumb components* são muito fáceis de serem testado. Tudo o que você precisa testar é a renderização da UI e das props recebidas.