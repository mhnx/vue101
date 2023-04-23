## Seção 01: Introdução
Aqui eu vou documentar o que eu aprender do Vue, como comandos e conceitos e algumas pequenas explicações. Vamos lá!

Site oficial: [https://vuejs.org/](https://vuejs.org/)

Com as ferramentas certas, você pode construir qualquer coisa! Com a tecnologia certa, você consegue dar vida à suas visões! Desde 2014 milhões de desenvolvedores têm escolhido Vue por que ele tem tudo que você precisa para rapidamente criar e escalar produtos, seja você um freelancer, uma nova startup ou uma companhia de empreendimento madura. O Vue é uma tecnologia confiável que lhe dá as ferramentas certas para o trabalho não importa o quão grande você é.

Por debaixo dos panos, o Vue tem um sistema reativo refinado combinado com renderização declarativa. Isso significa que o Vue faz muito do trabalho pesado por você. Por que o Vue é um framework progressivo você pode começar com a biblioteca principal (Core) e ir adicionando as peças que você precisa do seu ecossistema interconectado que conta com o seu próprio roteador (Vue Router), soluções de gerenciamento de estado (State Management), utilitários de teste (Testing Utils), uma interface de linha de comando (CLI) e mais.

O Vue é projetado para parear com todas as outras tecnologias apropriadas como TypeScript dando a você e seu time a flexibilidade para usar o Vue da forma mais adequada para o seu fluxo de trabalho. Seu design cuidadoso impede que seus componentes sobre renderizem, mantendo sua aplicação com performance ao escalar. Ao invés de você ter que otimizar seu código, o Vue pega seu código e o otimiza de maneira inteligente ao compilar. Assim você renderiza rápido e permanece rápido. O Vue lhe devolve a liberdade para focar em se tornar criativo e continuar produtivo, desfrutando do processo de desenvolvimento novamente. Ao escolher o Vue, você está investindo numa tecnologia que é investida em você. Então convidamos você a se juntar à comunidade Vue.

Ecossistema do Vue:

- Server Side Rendering
- Static Site Generation
- Vue Router
- Stage Management
- IDE Support
- Testing Utils
- Build Toolchain

### 001 - 1. Boas Vindas
JavaScript é uma das linguagens que mais tem revolucionado nos últimos anos. E, por conta disso, 3 frameworks foram desenvolvidos e ganharam destaque: React, Angular e Vue.

O Vue é usado para criar aplicações mais performáticas, que mantém o estado dos dados, carregando-os de maneira mais simples. Além disso o Vue com recursos como: **Two-way data binding** (vinculação de dados bidirecional), suas bibliotecas oficias **Vuex** e **Vue Router**.

### 002 - 2. A História do Vue
## Seção 02: Preparando o ambiente
### 003 - 3. Instalando o Visual Studio Code
### 004 - 4. Instalando o Node.js
### 005 - 5. Instalando o Git

## Seção 03: Primeiros passos
### 006 - 6. Download do Vue e Primeiro Exemplo
### 007 - 7. Download com CDN
### 008 - 8. Download com npm
A instalação é simples. Pelo site do Vue dá pra baixar o arquivo vue.js ou pegar o link para o CDN.

Uma terceira forma de instalar é pelo NPM. Essa forma é indicada para projetos em larga escala, com muitos componentes. O NPM traz o Webpack, que é o responsável por criar o bundle (arquivo final com os arquivos do projeto).

A princípio esse projeto usa a versão 2.7.14.
Para instalar digite o seguinte comando no seu terminal:

```
npm i vue@2.7.14
```
### 009 - 9. Download com Yarn
Podemos ainda instalar pelo Yarn, um gerenciador de pacotes criado pelo Facebook.

A diferença entre o Yarn e o NPM é que o Yarn é mais rápido e mais seguro.

```
npm i -g yarn
```

```
yarn add vue@2.7.14
```

### 010 - 10. Download com vue-cli
É uma ferramenta criada pelo próprio time desenvolvedor do Vue.

Ele vai fazer todo o “trabalho sujo”. Assim a gente pode usar mais tempo desenvolvendo código sem se preocupar com detalhes de configurações de servidor, etc.

```
npm install -g @vue/cli
# OU
yarn global add @vue/cli
```

Para criar um app usamos o seguinte comando:
```
vue create first_app
# DEPOIS
cd first_app
yarn serve
```

Isso vai abrir um servidor web para podermos visualizar o app que o CLI criou. É a partir dele que vamos criar o novo próprio projeto.

## Seção 04: Conceitos Fundamentais
### 011 - 11. Visão Geral da Seção
#### Passagem de dados

```
new Vue({
  data: {
    name: 'Hello World!'
  }
})

<h1>{{ name }}</h1>
```

#### Métodos

```
new Vue({
  methods: {
    changeName: function(newName) {
      this.name = newName
    }
  }
})

<button v-on:click="changeName('Evan You')">Trocar nome</button>
```

#### Computed Properties (Propriedades computadas)

```
new Vue({
  computed: {
    valorEmPorcentagem: function() {
      return this.valor + '%';
    }
  }
})

<p>{{ valorEmPorcentagem }}</p>
```

#### Watchers

```
new Vue({
  watch: {
    valor: function() {
      // Alterando o valor da propriedade de maneira dinâmica
    }
  }
})
```

#### Ciclo de vida da instância Vue

```
new Vue({
  created: function() {
    alert('A instância foi criada')
  }
})
```

#### Filtros

```
new Vue({
  filters: {
    toUpper: function(valor) {
      return valor.toUpperCase();
    }
  }
})

<p>{{ valor | toUpper }}</p>
```

### 012 - 12. Passagem de dados com o Vue
**Por que usar?**
É um dos fundamentos do Vue. Além disso facilita a comunicação do servidor com a interface (aplicação do lado do cliente) e vice-versa.

**Como realizar a passagem de dados?**
- 1 - Interpolação
Informamos o valor do texto na instância Vue. Exibimos esse texto no HTML usando: {{ identificador }}

- 2 - HTML
Informamos o HTML puro na instância Vue. Exibimos HTML usando a diretiva _v-html_.

- 3 - Atributos
Informamos o valor do atributo na instância Vue. Passamos seu valor para o HTML usando a diretiva _v-bind:nome\_do\_atributo_.

- 4 - Expressões JavaScript
Informamos o valor do texto na instância Vue. Manipulamos o valor do HTML usando  {{ identificador + expressão JS }}

### 013 - 13. Criando métodos
### 014 - 14. Computed Properties
### 015 - 15. Computed Properties vs Métodos
### 016 - 16. Definindo novo valor para uma Computed Property
### 017 - 17. Watchers
### 018 - 18. Ciclo de Vida do Vue
### 019 - 19. Trazendo dados ao renderizar a página
### 020 - 20. Filtros
### 021 - 21. Conhecendo uma coleção de Filtros Personalizados
### 022 - Teste 1: Você se Lembra? Conceitos Fundamentais

## Seção 05: Diretivas
### 023 - 22. Visão Geral da Seção
### 024 - 23. v-if e v-else
### 025 - 24. v-show
### 026 - 25. v-if vs v-show
### 027 - 26. v-text
### 028 - 27. v-html
### 029 - 28. v-once
### 030 - 29. v-for
### 031 - 30. v-bind
### 032 - 31. Informando argumentos dinamicamente para ov-bind
### 033 - 32. v-model
### 034 - 33. v-on
### 035 - 34. Usando o v-on para filtrar uma listadinamicamente
### 036 - 35. v-slot
### 037 - 36. v-pre
### 038 - 37. v-cloak
### 039 - 38. Criando Diretivas Personalizadas
### 040 - 39. Funções para Criação de Diretivas
### 041 - 40. Parâmetros para uma DiretivaPersonalizada
### 042 - 41. Diretivas Personalizadas - ArgumentosDinâmicos
### 043 - 42. Diretivas Personalizadas - Recebendo váriosvalores
### 044 - Teste 2: Você se Lembra? Diretivas

## Seção 06: Desafio 1 - Criando Um Blog
### 045 - 43. Apresentação do Desafio
### 046 - 44. Adicionando Vue ao projeto e criando lógicade login
### 047 - 45. Carregando posts dinamicamente
### 048 - 46. Limitando caracteres exibidos nopost
### 049 - 47. Código Final do Desafio

## Seção 07: Estilização
### 050 - 48. Visão Geral da Seção
### 051 - 49. Estilos em linha usando objetos
### 052 - 50. Estilos com múltiplos valores
### 053 - 51. Estilos em linha usando arrays
### 054 - 52. Aplicando classes usando objetos
### 055 - 53. Aplicando classes usando arrays
### 056 - Teste 3: Você se Lembra? Estilização

## Seção 08: Animações
### 057 - 54. Visão Geral da Seção
### 058 - 55. Transições CSS
### 059 - 56. Animações CSS
### 060 - 57. Animações Personalizadas
### 061 - 58. Animações com JavaScript
### 062 - 59. Definindo duração da animação
### 063 - 60. Transição entre Elementos
### 064 - 61. Mudando a Orientação da Transição
### 065 - Teste 4: Você se Lembra? Animações

## Seção 09: Eventos
### 066 - 62. Visão Geral da Seção
### 067 - 63. Definindo um Evento
### 068 - 64. O Objeto Event
### 069 - 65. Modificadores de Eventos
### 070 - 66. Modificadores de Teclado
### 071 - 67. Modificadores de Teclas deSistema
### 072 - 68. Modificador .exact
### 073 - 69. Modificadores de Botões doMouse
### 074 - 70. Aplicando mais de um evento
### 075 - Teste 5: Você se Lembra? Eventos

## Seção 10: Desafio 2 - Criando Uma Página De Login
### 076 - 71. Apresentação do Desafio
### 077 - 72. Adicionando o Vue e configurandotransição
### 078 - 73. Programando envio do formulário e mensagem desucesso
### 079 - 74. Código Final do Projeto

## Seção 11: Componentes
### 080 - 75. O que é um Componente?
### 081 - 76. Criando um Componente Global
### 082 - 77. Criando um Componente Local
### 083 - 78. Criando um Componente comvue-cli
### 084 - 79. Praticando: Criando o componente Header
### 085 - 80. Praticando: Criando o componente Footer
### 086 - 81. Praticando: Criando o componente Section
### 087 - 82. Praticando: Criando o componente News
### 088 - 83. Props - Informando dados para um componente
### 089 - 84. Praticando: Informando props para componente News
### 090 - 85. Comunicação entre componentes com eventos
### 091 - 86. Praticando: Comunicação entre componentes
### 092 - 87. v-model em componentes
### 093 - 88. Praticando: v-model em componentes
### 094 - 89. Praticando: Ciclo de Vida de um Componente
### 095 - 90. Slots
### 096 - 91. Praticando: Slots
### 097 - 92. Dando nomes aos Slots
### 098 - 93. Praticando: Dando nomes aos Slots
### 099 - 94. Mixins
### 100 - 95. Praticando: Criando Mixins
### 101 - 96. Componentes Dinâmicos
### 102 - 97. Praticando: Componentes Dinâmicos
### 103 - 98. Async Components
### 104 - 99. Praticando: Async Components
### 105 - Teste 6: Você se Lembra? Componentes

## Seção 12: Vuex
### 106 - 100. O que é o Vuex?
### 107 - 101. Instalando o Vuex
### 108 - 102. State
### 109 - 103. Praticando: State
### 110 - 104. Getters
### 111 - 105. Praticando: Getters
### 112 - 106. Praticando: Carregando notícias usandoGetters
### 113 - 107. Mutations
### 114 - 108. Praticando: Mutations
### 115 - 109. Actions
### 116 - 110. Praticando: Actions
### 117 - 111. Praticando: Adaptando o v-model noVuex
### 118 - 112. Módulos
### 119 - 113. Praticando: Módulos
### 120 - Teste 7: Você se Lembra? Vuex

## Seção 13: Vue Router
### 121 - 114. O que é o Vue Router?
### 122 - 115. Instalando o Vue Router
### 123 - 116. Como criar rotas
### 124 - 117. Praticando: Criando rotas
### 125 - 118. Métodos para navegação
### 126 - 119. Praticando: Métodos para navegação
### 127 - 120. Informando parâmetros para asrotas
### 128 - 121. Praticando: Informando parâmetros para a rotade
### 129 - 122. Criando rotas filhas
### 130 - 123. Criando nomes para as Rotas
### 131 - 124. Praticando: Criando nomes para asRotas
### 132 - 125. Criando nomes para as views
### 133 - 126. Definindo a Ordem das Rotas
### 134 - 127. Redirect e Alias
### 135 - 128. Praticando: Redirect e Alias
### 136 - 129. Página 404 (Not Found)
### 137 - 130. Praticando: Página 404 (NotFound)
### 138 - 131. Navigation Guards - Global
### 139 - 132. Navigation Guards - Local
### 140 - 133. Navigation Guards - Componentes
### 141 - 134. Praticando: Criando validação pararenderização de um
### 142 - 135. Transições entre as rotas
### 143 - 136. Praticando: Transições entre asrotas
### 144 - Teste 8: Você se Lembra? Vue Router

## Seção 14: Conclusão
### 145 - 137. Conclusão do Curso