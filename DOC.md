# Introdução ao Vue.js 2

## Pré-requisitos

- Conhecimento básico em HTML, CSS e JavasScript;
- [Node.js](https://nodejs.org/en/download) ou [Yarn](https://yarnpkg.com/getting-started/install) para instalação e gerenciamento de dependências.

## O que é o Vue.js?

Vue (pronuncia-se `/vjuː/`, como **view**, em inglês) é um **framework progressivo** para a construção de interfaces de usuário. A biblioteca principal é focada exclusivamente na camada visual *(view layer)*, sendo fácil adotar e integrar com outras bibliotecas ou projetos existentes.

## Como instalar?

Para mais opções de instalação [clique aqui](https://br.vuejs.org/v2/guide/installation.html).

### CDN

Para propósitos de prototipação ou aprendizado, você pode usar a versão mais recente com:
```html
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
```

Para produção, recomenda-se vincular um  número de versão específico para evitar bugs:
```html
<script src="https://cdn.jsdelivr.net/npm/vue@2.6.12"></script>
```

#### Primeiros passos

A forma mais simples de testar Vue.js é usando o [exemplo de "Hello World" no CodeSandbox](https://codesandbox.io/s/github/vuejs/vuejs.org/tree/master/src/v2/examples/vue-20-hello-world), ou criar um arquivo `index.html` e incluir o código:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <title>My first Vue app</title>
  <script src="https://unpkg.com/vue"></script>
</head>

<body>
  <div id="app">
    {{ message }}
  </div>

  <script>
    var app = new Vue({
      el: '#app',
      data: {
        message: 'Hello World!'
      }
    })
  </script>
</body>
</html>
```

### NPM

NPM é o método de instalação recomendado para construção de aplicações em larga escala com o Vue. Ele combina perfeitamente com empacotadores de módulos, tais como Webpack ou Browserify.

```bash
# última versão estável
$ npm install vue
```

## CLI

O [Vue CLI](https://cli.vuejs.org/) visa ser a linha de base de ferramentas padrão para o ecossistema Vue. Garante que as várias ferramentas de construção funcionem perfeitamente em conjunto com padrões razoáveis para que você possa se concentrar em escrever seu aplicativo em vez de passar dias discutindo com as configurações. Ao mesmo tempo, ainda oferece a flexibilidade de ajustar a configuração de cada ferramenta sem a necessidade ejetar as configurações do Webpack.

### Instalação

Para instalar o pacote, use um dos seguintes comandos. Você precisa de privilégios de administrador para executá-los, a menos que o npm tenha sido instalado em seu sistema por meio de um gerenciador de versões Node.js (por exemplo, n ou nvm).

```bash
$ npm install -g @vue/cli
# OR
$ yarn global add @vue/cli
```

### Criando um novo projeto

Para criar um novo projeto, execute o comando e escolha as opções disponíveis de acordo com sua necessidade e aguarde até que o processo de criação seja concluído:

```bash
# criar o projeto
$ vue create NOME_DO_PROJETO

# abrir o diretório do projeto
$ cd NOME_DO_PROJETO

# rodar o projeto
$ npm run serve
```

### Estrutura básica do projeto

A estrutura pode mudar um pouco de acordo com as opções selecionadas durante o processo de criação do projeto.

```bash
meu-projeto/
├── node_modules/ # dependências do Node.js
├── public/ # index.html e favicons
└── src/ # componentes, configurações e assets
    ├── assets/ # css e imagens
    ├── components/ # componentes menores
    └── views/ # view componentes
```

## Componentes

### Estrutura de um componente

Todo componente é formado por três grandes blocos ("tags"):

- **template:** Contrução HTML (tags, componentes, diretivas, invocação de métodos, filtros e etc). Essa tag necessita apenas de um elemento filho caso seja inserido mais de um elemento ocorrerá um erro na aplicação;
- **script:** importação de módulos, controle do ciclo de vida do componente, criação de métodos, atributos, filtros e etc. Permite trabalhar com Typescript.
- **style:** Estilização do componente, com opção de trabalhar ou não com pré-processadores css (Sass, Less, Stylus ...).

```html
<template>
  <!-- HTML -->
</template>

<script>
  // script
</script>

<style>
  /* styles */
</style>
```

### Tipos de componentes

- **Dumb components**: Componentes de apresentação, não tem lógica, e não guardam estados, apenas reenderizam as *properties* passadas como parâmetro.
- **Container components (smart components)**: Contêm a regra de negócio e são utilizados para controlar os dados que são passados via *properties* para os **dumb components**.

### Criando nosso primeiro componente

```html
<template>
  <button>{{ text }}</button>
</template>

<script>
export default {
  name: 'Counter',
  data () {
    return {
      text: 'Button'
    }
  }
}
</script>

<style scoped>
button {
  background-color: #069;
  border: none;
  border-radius: 4px;
  color: #fff;
  font-size: 12px;
  outline: none;
  padding: 10px;
}
</style>
```

[Clique aqui para ver o exemplo](https://ederssouza.github.io/vuejs-training/#/exemplos/componente-basico)

### Ciclo de vida de um componente

Abaixo está um diagrama para o ciclo de vida da instância. Você não precisa entender completamente tudo o que está acontecendo neste momento, mas conforme você aprender e construir mais coisas, este diagrama será uma referência útil.

![Ciclo de vida de um componente](https://br.vuejs.org/images/lifecycle.png)

[Clique aqui para ver o exemplo](https://ederssouza.github.io/vuejs-training/#/exemplos/componente-ciclo-de-vida)

### Principais diretivas

- **`v-text`**: Atualiza o `textContent` do elemento;
- **`v-html`**: Atualiza o `innerHTML` do elemento;
- **`v-show`**: Alterna a propriedade CSS `display` do elemento baseado na condição de verdadeiro ou falso do valor da expressão;
- **`v-if`**: Renderiza condicionalmente o elemento baseado na condição de verdadeiro ou falso do valor da expressão;
- **`v-else`**: Denota o "bloco senão" de uma cadeia `v-if` ou `v-if`/`v-else-if`;
- **`v-else-if`**: Denota o "bloco senão se" para `v-if`. Pode ser encadeado;
- **`v-for`**: Renderiza o elemento ou bloco de template múltiplas vezes baseado nos dados de origem (source data), pode ser utilizado com valores do tipo `Array`, `Object`, `Number` e `String`;
- **`v-on`** ou **`@`**: Atribui uma escuta de evento ao elemento;
- **`v-bind`** ou **`:`**: Dinamicamente faz a interligação de um ou mais atributos ou propriedades de um componente a uma expressão;
- **`v-model`**: Cria uma interligação de mão dupla (two-way binding) em um elemento de entrada (input) de formulário ou componente.

[Clique aqui para ver o exemplo](https://ederssouza.github.io/vuejs-training/#/)

### Criando métodos

Os métodos criados podem acessar diretamente a instância VM ou podem ser utilizados em expressões ou diretivas. Também terão seu contexto `this` atribuído a instância Vue.

[Clique aqui para ver o exemplo](https://ederssouza.github.io/vuejs-training/#/exemplos/metodos)

### Passando props para um componente

Uma lista/hash de atributos que são expostos para aceitar dados do componente pai. Possui tanto uma sintaxe baseada em Array como, alternativamente, uma sintaxe baseada em Object, que permite configurações avançadas como checagem de tipos, validações personalizadas e valores padrão.

Com a sintaxe baseada em Object, você pode usar as seguintes opções:

- **`type`**: pode ser um dos seguintes construtores nativos: `String`, `Number`, `Boolean`, `Array`, `Object`, `Date`, `Function`, `Symbol`, qualquer função construtora personalizada ou um array dessas. Irá verificar se um prop tem o tipo determinado e emitirá um aviso se não tem.
- **`default`**: `any`
Especifica um valor padrão para o prop. Se o prop não é passado, este valor será usado em seu lugar. Valores padrão de tipo `Object` ou `Array` devem ser retornados de uma função factory.
- **`required`**: `Boolean`
Define se o prop é necessário. Em ambiente de não-produção, um aviso de console será lançado se esse valor for verdadeiro e o prop não for passado.

[Clique aqui para ver o exemplo](https://ederssouza.github.io/vuejs-training/#/exemplos/props)

### Emitindo eventos

`vm.$emit( eventName, [...args] )` lança um evento na instância atual. Qualquer argumento adicional será passado para a função de callback da escuta. Esse evento poderá ser capturado pelo elemento pai.

[Clique aqui para ver o exemplo](https://ederssouza.github.io/vuejs-training/#/exemplos/evento-emit)

## Filtros

O Vue permite que você defina filtros que podem ser utilizados para aplicação de formatação de texto.

```html
<template>
  <div>
    <strong>CNPJ:</strong> {{ '00000000000191' | cnpj }}
  </div>
</template>

<script>
export default {
  name: 'Filters',
  filters: {
    cnpj (str = '') {
      return String(str).replace(/^(\d{2})(\d{3})(\d{3})(\d{4})(\d{2})$/, '$1.$2.$3/$4-$5')
    }
  }
}
</script>
```

[Clique aqui para ver o exemplo](https://ederssouza.github.io/vuejs-training/#/exemplos/filtros)

## Referências

- [O que é Vue.js?](https://br.vuejs.org/v2/guide/#O-que-e-Vue-js)
- [Primeiros Passos / instalação](https://br.vuejs.org/v2/guide/#Primeiros-Passos)
- [Diagrama do Ciclo de Vida](https://br.vuejs.org/v2/guide/instance.html#Diagrama-do-Ciclo-de-Vida)
- [Diretivas](https://br.vuejs.org/v2/api/index.html#Diretivas)
- [Props](https://br.vuejs.org/v2/api/index.html#props)
- [Métodos da Instância / Eventos](https://br.vuejs.org/v2/api/index.html#Metodos-da-Instancia-Eventos)
- [Filtros](https://br.vuejs.org/v2/guide/filters.html)
- [Roteamento](https://router.vuejs.org)
