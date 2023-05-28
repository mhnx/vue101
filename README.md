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

```js
new Vue({
  data: {
    name: 'Hello World!'
  }
})

<h1>{{ name }}</h1>
```

#### Métodos

```js
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

```js
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

```js
new Vue({
  watch: {
    valor: function() {
      // Alterando o valor da propriedade de maneira dinâmica
    }
  }
})
```

#### Ciclo de vida da instância Vue

```js
new Vue({
  created: function() {
    alert('A instância foi criada')
  }
})
```

#### Filtros

```js
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
Os métodos são funções que nos permitem realizar ações em nossa aplicação: interações com o usuário, manipulações de dados, etc.

Para isso usamos a propriedade _methods_ da instância Vue e a diretiva _v-on_.

É possível criar dois tipos de métodos: (1) métodos estáticos: que executam uma ação definida sem esperar parâmetros, e (2) métodos que esperam parâmetros.

Para ver um exemplo veja o arquivo ```methods.html``` e no console do navegador invoque a função assim: ```app.reverseMessage()```.

### 014 - 14. Computed Properties
As propriedades computadas são uma maneira elegante de manipular nossos dados. As propriedades computadas nos permitem criar uma nova propriedade baseada em uma já existente.

Para criar uma propriedade computada vamos utilizar a propriedade da instância Vue chamada de _computed_. Informamos esse valor através no HTML através de uma interpolação com o nome da propriedade computada criada; por exemplo: ```{{ computed_property }}```.

> É importante que as propriedades computadas sejam fáceis de serem lidas.

### 015 - 15. Computed Properties vs Métodos
Qual é a diferença?
- Os métodos realizam ações, eventos.
- As propriedades computadas manipulam dados.

Ainda, as propriedades computadas _ficam em cache_. Seus valores são armazenados como sendo uma nova propriedade da instância Vue, sendo requisitadas apenas uma vez. Por conta disso, as propriedades computadas consomem menos memória, se comparadas aos métodos.

### 016 - 16. Definindo novo valor para uma Computed Property
Geralmente as propriedades computadas apenas retornam valores. No entanto, também é possível atribuir novos valores através de um objeto com os métodos ```get``` e ```set```.

Acesse o arquivo ```computed-properties-set-value.html``` e digite no console do navegador o seguinte:
```
app.fullName = 'Mahonri Maia'
```

### 017 - 17. Watchers
Um _watcher_ (observador) é um recurso do Vue que nos permite observar mudanças de valores em uma determinada propriedade.

Quando a mudança é detectada uma ação é executada.

É importante observar que os _watchers_ são a base do conceito da reatividade. O Vue utiliza os watchers por debaixo dos panos em muitas situações para atualizar dados no HTML assim que recebidos seja via console ou qualquer outro datasource.

Para criar um _watcher_ usamos a propriedade ```watch``` da instância Vue. Dentro dela informamos o nome da propriedade que queremos monitorar e a função a ser executada.

O exemplo da criação de um _watcher_ será feito no arquivo: ```watchers.html```. Nele usaremos a diretiva ```v-model```, que é muito usado em campos de formulário porque, quando informamos pra ele uma propriedade, ele fica de olho nela para fazer o _Two-way data binding_—ou seja, nós podemos definir o valor de uma propriedade dentro do input e isso já é atualizado na instância Vue.

> Observe que se você puder usar _computed properties_ ao invés de _watchers_ você deve fazer isso para economizar recursos.

### 018 - 18. Ciclo de Vida do Vue
O ciclo de vida de uma instância Vue envolve uma série de funções que são executadas em várias etapas da existência da instância, semelhante as etapas da vida humana.

Há funções que são executadas antes, durante e após a aplicação ser montada no navegador para ser exibida ao usuário.

Veja uma lista de funções que podem ser utilizadas nas diversas etapas do ciclo de vida de uma instância Vue:
| Funções               | Descrição                                                                                                                                                                          |
|-----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ```beforeCreate()```  | Executada assim que a instância Vue é criada, mas antes dos dados, eventos e watchers estarem disponíveis.                                                                         |
| ```created()```       | Executada assim que a instância Vue é criada. Tem à disposição os recursos básicos: dados, computed properties, events, watchers, etc. Contudo, a aplicação ainda não foi montada. |
| ```beforeMount()```   | Executada um pouco antes do processo de montagem da aplicação começar.                                                                                                             |
| ```mounted()```       | Chamada assim que o processo de montagem é finalizado, já tem acesso a propriedade this.el, para manipular o componente.                                                           |
| ```beforeUpdate()```  | Chamada quando os dados são atualizados na página, mas antes dessas mudanças serem refletidas no HTML.                                                                             |
| ```updated()```       | Chamada assim que o HTML é alterado devido à mudança de dados na instância Vue.                                                                                                    |
| ```beforeDestroy()``` | Chamada antes da aplicação ser finalizada ou destruída.                                                                                                                            |
| ```destroyed()```     | Chamada assim que a instância Vue é destruída. Nesse momento não é possível mais ter a cesso aos recursos do Vue.                                                                  |

Exemplos:
```js
let app = new Vue({
  created: function() {
    console.log('A instância foi criada')
  }
})
```

```js
let app = new Vue({
  mounted: function() {
    console.log('A aplicação foi montada')
  }
})
```

### 019 - 19. Trazendo dados ao renderizar a página
No arquivo ```lifecycle.html``` foram adicionados os seguintes trechos de código para exemplificar a renderização de dados vindos de outra fonte:

```html
...
<ul>
  <li v-for="state in states">{{ state.nome }}</li>
</ul>
```
```js
data: {
  ...
  states: []
}
```
```js
...
created() {
  fetch('https://servicodados.ibge.gov.br/api/v1/localidades/estados').then(response => {
    response.json().then(data => {
      this.states = data;
    })
  }).catch(err => {
    console.log(err)
  })
}
...
```

Vide commit: "Renderização de dados usando fetch e a diretiva v-for"

### 020 - 20. Filtros
Filtros são uma maneira de formatar os dados que informamos em uma página. Ou seja, os dados não são alterados, mas sim a forma como eles são exibidos.

**Como criar?**
No JavaScript, informamos a propriedade ```filters``` na instância Vue. Cada filtro será uma função.

Usamos uma barra vertical (```|```) e, em seguida, o nome do filtro para aplicá-lo.

Por exemplo:
```js
let app = new Vue({
  filters: {
    meu_filtro1: function() {
      // Transformação dos dados e seu returno
    },
    meu_filtro2: function() {
      // Transformação dos dados e seu returno
    }
  }
})
```

```html
<p>{{ variavel | meu_filtro1 | meu_filtro2 }}</p>
```

> É possível aplicar mais de um filtro. Lembre que o segundo filtro vai transformar o dado depois de transformado pelo primeiro filtro.

### 021 - 21. Conhecendo uma coleção de Filtros Personalizados
Vamos utilizar a biblioteca [vue2-filters](https://www.npmjs.com/package/vue2-filters).

```html
<script src="https://cdn.jsdelivr.net/npm/vue2-filters/dist/vue2-filters.min.js"></script>
```

Para ver um exemplo veja o arquivo ```filters.html``` e no console do navegador altere o valor da variável ```name``` assim: ```app.name = ''```.

> Nessa aula vimos os filtros: ````placeholder```, ```truncate``` e ```pluralize```.

### 022 - Teste 1: Você se Lembra? Conceitos Fundamentais

## Seção 05: Diretivas
### 023 - 22. Visão Geral da Seção
Diretiva significa instrução ou norma que deve ser seguida.

No Vue.js, uma diretiva informa a um elemento HTML quais ações ele deve executar.

Uma diretiva é informada como um atributo HTML normal, na tag de abertura do elemento. Ela é prefixada com ```v-```, deixando claro que é um atributo específico do Vue.

### 024 - 23. v-if e v-else
A diretiva ```v-if``` serve para determinar se uma tag/elemento deve ser exibido ou não com base em uma condição (condição simples ou expressão)—se a condição não for atendida, o elemento é removido da tela.

**Como criar?**

Informamos a condição dentro da tag com as diretivas ```v-if```, ```v-else``` ou ```v-else-if```. Além disso podemos definir dentro da instância Vue uma propriedade para ser usada na condição.

**Boas Práticas**

Quando usamos ```v-if```, ```v-else``` em elementos diferentes, é interessante adicionar o atributo ```key``` em cada um deles, evitando conflitos de renderização.

Por exemplo:
```html
<div v-if="condicao" key="success">
  Sucesso
</div>

<div v-else key="error">
  Erro
</div>
```

### 025 - 24. v-show
A diretiva ```v-show``` serve para determinar se uma tag/elemento deve ser exibido ou não com base em uma condição (condição simples ou expressão)—se a condição não for atendida, o elemento é removido da tela.

**Como criar?**

Informamos a condição dentro da tag com a diretiva ```v-show```. Além disso podemos definir dentro da instância Vue uma propriedade para ser usada na condição.

### 026 - 25. v-if vs v-show
**Qual é a diferença entre ```v-if``` e ```v-show```?**

- ```v-if```: **Insere ou remove** um elemento.
- ```v-show```: **Exibe ou esconde** um elemento (muda a propriedade CSS _display_ da tag).

**Como usar um ou outro?**

O ```v-if``` é mais lento. Exige mais do servidor pois sempre recria o elemento. Use-o quando for improvável que a condição de exibição mude constantemente.

O ```v-show``` é mais leve. Exige do servidor para renderizar o elemento apenas da primeira vez. Use-o quando a condição de exibição mudar constantemente.

### 027 - 26. v-text
A diretiva ```v-text``` serve para exibir o valor de uma propriedade da instância Vue no HTML. Note que essa diretiva possui o mesmo efeito da interpolação.

Na verdade, quando utilizamos a interpolação, o Vue usa a diretiva ```v-text``` por debaixo dos panos.

**Como criar?**

Informamos o nome da propriedade na diretiva ```v-text```. Por exemplo: ```v-text="propriedade"```.

Observe que é necessário criar a propriedade com o mesmo nome na instância Vue (no objeto ```data```).

### 028 - 27. v-html
**Qual sua função?**

Interpretar e exibir o valor HTML puro vindo de uma propriedade da instância Vue (Não é interpredado como um template Vue).

> Ele altera a propriedade ```innerHTML``` de uma tag.

**Como criar?**

Informamos o nome da propriedade na diretiva ```v-html```. Por exemplo: ```v-html="propriedade"```.

Observe que é necessário criar a propriedade com o mesmo nome na instância Vue (no objeto ```data```) contendo o HTML que queremos exibir.

**Cuidado**
> A renderização dinâmica do HTML é uma porta aberta para ataques XSS. Use essa diretiva em ambientes seguros e com cautela!

### 029 - 28. v-once
**Qual sua função?**

Exibir o valor de uma propriedade da instância Vue **apenas uma vez**.

Deixa o elemento estático, podendo contribuir na melhoria da performance do site.

**Como criar?**

Informamos a diretiva ```v-once``` na tag que desejamos deixar estática (não espera parâmetros).

Por exemplo: ```<a v-once>{{ propriedade }}</a>```

Ao atualizar o valor de uma propriedade no console, por exemplo, a propriedade não é atualizada no HTML dinamicamente pois o elemento que possui a diretiva ```v-once``` se tornou um elemento estático.

### 030 - 29. v-for
**Qual sua função?**

A diretiva ```v-for``` é usada para exibir uma quantidade maior de informações, levando em conta uma lista de propriedades.

Falando de outra forma, ela é usada para percorrer um array ou objeto com esses valores e exibir em uma tag repetidas vezes.

**Como criar?**

Informamos a diretiva ```v-for``` na tag que desejamos repetir.

Por exemplo: ```v-for="item in propriedade"```

Podemos acessar também o índice do array ou o nome da propriedade do objeto.

### 031 - 30. v-bind
**Qual sua função?**

Vincular o valor de qualquer propriedade a uma variável do Vue.

Com isso podemos fazer com que importantes atributos como ```href```, ```src```, ```class```, etc, se tornem dinâmicos.

**Como criar?**

Informamos a diretiva ```v-bind``` na tag que desejamos informar o atributo.

Por exemplo: ```v-bind:href="linkSite"```

Essa diretiva possui uma forma abreviada de ser chamada, apenas informando ```:``` (dois pontos) e o atributo que queremos tornar dinâmico.

Por exemplo: ```:src="imgSrc"```

**Boas práticas**

É importante manter um padrão quando chamarmos a forma abreviada das diretivas.

Se chamarmos uma forma abreviada, devemos usá-la sempre no contexto, mas não misturá-la com a forma convencional.

Por exemplo, não devemos fazer o seguinte código:
```html
<input
  v-bind:value="valor"
  :placeholder="valor2"
>
```

### 032 - 31. Informando argumentos dinamicamente para o v-bind
A partir da versão 2.6 do Vue.js é possível informar os argumentos para a diretiva de forma dinâmica, se baseando em uma propriedade da instância Vue.

Para isso basta informar a propriedade da instância Vue que vai substituir o atributo entre colchetes ```[]``` e o nome da propriedade que vai conter o valor para o atributo do elemento HTML.

Veja os códigos abaixo:
```html
<span title="título do span">Texto</span>
```

Substituindo o atributo e o valor por propriedades da instância Vue ficaria assim:
```html
<span :[atributo]="valor">Texto</span>
```

Onde na instância Vue conteria:
```js
let app = new Vue({
  el: "#app",
  data: {
    atributo: 'title',
    valor: 'título do span'
  }
})
```

> Observe que no código HTML a diretiva ```v-bind``` foi abreviada.

### 033 - 32. v-model
**Qual sua função?**

Realizar uma ligação de dados bidirecional (o _two-way data binding_).

Com isso, ao alterar o valor de uma propriedade na camada view, também estaremos alterando o valor original desta mesma propriedade.

**Como podemos usar?**

Podemos usar o ```v-model``` em 4 elementos:
1. Na tag _\<input>_;
2. Na tag _\<select>_;
3. Na tag _\<textarea>_;
4. Em componentes.

**Como criar?**

Informamos a diretiva ```v-model``` na tag que desejamos realizar o _two-way data binding_.

Exemplo:
```html
<input type="text" v-model="message">
```

**Modificadores**

Modificadores são propriedades que podemos informar junto com o ```v-model```. Elas são funções específicas, que podem ser muito úteis.

1 - ```.number``` -> Transforma o valor da propriedade de string para número.
2 - ```.trim``` -> Remove os espaços antes e depois da propriedade.
3 - ```.lazy``` -> Define que os eventos de mudança (change) serão ouvidos.

### 034 - 33. v-on
**Qual sua função?**

1 - Criar um ouvinte de evento. Isso é importante para que a aplicação fique mais reativa.
2 - Criar eventos personalizados, principalmente no contexto de componentes.

**Como criar?**

Informamos a diretiva ```v-on``` na tag que desejamos aplicar o evento, junto com o nome dele.

Exemplo: ```v-on:click="metodo"```

Essa diretiva possui uma forma abrevidada de ser chamada, apenas informando ```@``` (arroba) e o nome do evento que queremos definir.

Exemplo: ```@keyup="metodo"```

**Boas práticas**

É importante manter um padrão quando chamarmos a forma abreviada das diretivas.

Se chamarmos uma forma abreviada, devemos usá-la sempre no contexto, mas não misturá-la com a forma convencional.

Por exemplo, não devemos fazer o seguinte código:
```html
<input
  v-on:mouseenter="metodo1"
  @click="metodo2"
>
```

**O que podemos informar para a diretiva?**

1 - O nome de um método
```v-on:click="nomeDoMetodo```

2 - Uma expressão JavaScript
```@dblclick="alert('Hello World')"```

3 - Até mesmo não informar nada, se estivermos usando um modificador.
```@click.prevent```

**Argumentos dinâmicos (novidade da versão 2.6 do Vue)**

Agora também é possível informar os argumentos para a diretiva de maneira dinâmica, se baseando em uma propriedade da instância Vue.

Para isso, basta informar ```[]``` (colchetes) no lugar de um argumento.

Por exemplo: ```v-on:[propriedade]="metodo"```

### 035 - 34. Usando o v-on para filtrar uma lista dinamicamente
Vide exemplo no arquivo ```v-on.html```.

### 036 - 35. v-slot

**Qual sua função?**

Diretiva usada com componentes.

Usada para inserir conteúdo em um componente, através da tag ```<template>```.

**Como criar?**

Informamos a diretiva ```v-slot``` na tag que desejamos adicionar conteúdo, junto com seu nome como argumento.

Exemplo: ```v-slot:div```

Essa diretiva possui uma forma abreviada de ser chamada, apenas informando ```#``` (cerquilha ou hashtag) e o nome do slot que queremos definir.

Exemplo: ```#footer```

**Boas práticas**

É importante manter um padrão quando chamarmos a forma abreviada das diretivas.

Se chamarmos uma forma abreviada, devemos usá-la sempre no contexto, mas não misturá-la com a forma convencional.

Por exemplo, não devemos fazer o seguinte código:
```html
<template v-slot:cabecalho>
<template #site>
```

### 037 - 36. v-pre
**Qual sua função?**

Desabilitar a compilação Vue no elemento em que for aplicado. Em outras palavras, o Vue deixa de funcionar no elemento especificado. 

Observe que o ```v-once``` tem um comportamento similar.

**Por que usar?**

1 - Se desejarmos exibir as chaves de interpolação de variável no navegador.
2 - Se desejarmos aumentar a performance para renderizar nossa aplicação.

**Como criar?**

Informamos a diretiva ```v-pre``` na tag que desejamos desabilitar.

Exemplo: ```<h2 v-pre>{{ name }}</h2>```

Essa diretiva não espera nenhum argumento.

O exemplo acima irá imprimir no navegador o texto "{{ name }}".

### 038 - 37. v-cloak
**Qual sua função?**

Garantir que os elementos serão exibidos apenas quando a instância Vue for completamente carregada.

Evitar que a página fique desestruturada ("quebrada") enquanto ocorre o carregamento.

**Como criar?**

Informamos a diretiva ```v-cloak``` na tag que desejamos aplicar a inteligência de espera.

Exemplo:  
```<h1 v-cloak>Seja bem-vindo, {{ name }}!</h1>```

> Essa diretiva não espera argumentos!

**A importância do CSS**

Para um funcionamento completo, é necessário adicionar um estilo CSS em nosso código, ocultando o elemento até o carregamento da página.
```css
[v-cloak] {
  display: none;
}
```

### 039 - 38. Criando Diretivas Personalizadas
**Quando é necessário?**

Em algumas situações, talvez as diretivas padrão do Vue não atendam à nossa necessidade.

Nesses casos podemos criar nossas próprias diretivas.

**Como criar?**

1 - Globalmente (usando um método da instância Vue)
```js
Vue.directive('nome-diretiva', {})
```

2 - Localmente (usando a propriedade dentro da instância Vue)
```js
new Vue({
  directives: { }
})
```

Por exemplo:
```js
Vue.directive('white', {
  inserted: function(elemento) {
    elemento.style.color = 'white'
  }  
})
```

```html
<p v-white>Hello World</p>
```

### 040 - 39. Funções para Criação de Diretivas
**Possíveis funções ao criar uma diretiva**

1. ```bind()```: chamada quando a diretiva é vinculada a um elemento.
2. ```inserted()```: chamada quando o elemento vinculado é inserido no DOM.
3. ```update()```: chamada quando o elemento pai do elemento vinculado é atualizado.
4. ```unbind()```: chamada quando a diretiva é desvinculada de um elemento.
5. ```componentUpdated()```: chamada quando o componente é atualizado.

Exemplo:
```js
Vue.directive('nome-diretiva', {
  bind: function(elemento) {
    console.log('Fui vinculada a um elemento')
  },
  unbind: function(elemento) {
    console.log('Fui desvinculada de um elemento')
  }
})
```

Para um exemplo veja o arquivo ```custom-directives.html``` na diretiva local ```capitalize```.

> Observe que quando as diretivas fazem uso dessas funções citadas acima, elas deixam de ser chamadas como uma função e passam a ser tratadas como um objeto.
> 
> Isso nos ajuda a perceber que esses métodos são como se fosse um ciclo de vida das diretivas personalizadas, nos permitindo ter um maior controle de cada etapa das diretivas e dos nossos projetos.

### 041 - 40. Parâmetros para uma Diretiva Personalizada
**Parâmetros**
1. ```el```: Elemento que a diretiva está vinculada.
2. ```binding```: Um objeto que traz informações úteis, como o valor informado para a diretiva (```value```), o valor antigo (```oldValue```) e os modificadores (```modifiers```).
3. ```vnode```: O nó HTML virtual produzido pelo Vue.
4. ```oldVnode```: O nó HTML virtual antigo (só terá um valor se estivermos nas funções ```update()``` ou ```componentUpdated()```).

**Exemplo**
```js
Vue.directive('nome-diretiva', {
  bind: function(el, binding) {
    console.log(`O valor informado foi ${binding.value}`)
  }
})
```

**Todas as opções da variável ```binding```**
1. ```name```: Nome da diretiva, sem o prefixo "v-".
2. ```value```: Valor informado para a diretiva.
3. ```oldValue```: Valor antigo da variável, se ela possuir.
4. ```expression```: Expressão JavaScript informada para a diretiva.
5. ```modifiers```: Um objeto com todos os modificadores informados. Eles são identificados por meio do ```.``` (ponto).  
**Exemplo:**
```html
<p v-native.mod1> // Será retornado "{ mod1: true }"
```
6. ```arg```: Se informarmos algum argumento para a diretiva com ```:``` (dois-pontos), ele será exibido aqui.  
**Exemplo:**
```html
<img v-blank:argumento> // Será retornado "argumento"
```

> Os modificadores vão ser muito usados quando usarmos as diretivas de evento.  
> **Exemplo:**
> ```html
> <p v-on.prevent>
> ```

### 042 - 41. Diretivas Personalizadas - Argumentos Dinâmicos
Assim como nas diretivas ```v-bind``` e ```v-on```, podemos criar argumentos dinâmicos, vindos da instância Vue, e adicioná-los às nossas diretivas personalizadas.

**Exemplo:**
```html
new Vue({
  data: {
    name: 'argumento'
  }
})

<div v-star:[name]>May the Force be with you!</div>
```

> Para ver um exemplo, veja o arquivo ```custom-directives.html``` no commit **"Diretivas personalizadas - Argumentos dinâmicos"**, e, no console do navegador, altere os valores de ```argument``` e ```distance```: ```app.argument = 'top'``` ou ```app.distance = 350```.

### 043 - 42. Diretivas Personalizadas - Recebendo vários valores
É possível receber mais de um valor para nossa diretiva.

Para isso, basta informar um objeto para ela.

**Exemplo**
```js
new Vue({
  directives: {
    edit-text: {
      inserted: function(el, binding) {
        console.log(binding.value.size)
        console.log(binding.value.color)
      }
    }
  }
})
```
```html
<h2 v-edit-text="{ size: 10, color: 'red' }">Vue.js is awesome!</h2>
```

### 044 - Teste 2: Você se Lembra? Diretivas

## Seção 06: Desafio 1 - Criando Um Blog
### 045 - 43. Apresentação do Desafio
**Conceitos que serão exercitados**
1. Conceitos fundamentais
2. Diretivas

**Objetivos e tarefas**

Objetivo: Criar um blog

Tarefas:
1. Adicionar o Vue.js no projeto;
2. Criar lógica de login e logout no blog;
3. Trazer os posts do blog de maneira dinâmica;
4. Exibir o conteúdo do post apenas até 200 caracteres.

> O arquivo ```desafio-1-blog.zip``` contém o código do projeto onde as tarefas acima deverão ser executadas.
> 
> As próximas aulas dessa seção conterão as respostas propostas pelo professor.
> 
> **É muito importante tentar realizar as tarefas antes de conferir as respostas para exercitar sua lógica de programação e sua compreensão dos conceitos do Vue apresentados até agora.**
> 
> Boa sorte e bons estudos!

### 046 - 44. Adicionando Vue ao projeto e criando lógica de login
### 047 - 45. Carregando posts dinamicamente
### 048 - 46. Limitando caracteres exibidos no post
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
### 073 - 69. Modificadores de Botões do Mouse
### 074 - 70. Aplicando mais de um evento
### 075 - Teste 5: Você se Lembra? Eventos

## Seção 10: Desafio 2 - Criando Uma Página De Login
### 076 - 71. Apresentação do Desafio
### 077 - 72. Adicionando o Vue e configurando transição
### 078 - 73. Programando envio do formulário e mensagem de sucesso
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
### 112 - 106. Praticando: Carregando notícias usando Getters
### 113 - 107. Mutations
### 114 - 108. Praticando: Mutations
### 115 - 109. Actions
### 116 - 110. Praticando: Actions
### 117 - 111. Praticando: Adaptando o v-model no Vuex
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
### 127 - 120. Informando parâmetros para as rotas
### 128 - 121. Praticando: Informando parâmetros para a rota de notícias
### 129 - 122. Criando rotas filhas
### 130 - 123. Criando nomes para as Rotas
### 131 - 124. Praticando: Criando nomes para as Rotas
### 132 - 125. Criando nomes para as views
### 133 - 126. Definindo a Ordem das Rotas
### 134 - 127. Redirect e Alias
### 135 - 128. Praticando: Redirect e Alias
### 136 - 129. Página 404 (Not Found)
### 137 - 130. Praticando: Página 404 (NotFound)
### 138 - 131. Navigation Guards - Global
### 139 - 132. Navigation Guards - Local
### 140 - 133. Navigation Guards - Componentes
### 141 - 134. Praticando: Criando validação para renderização de um componente
### 142 - 135. Transições entre as rotas
### 143 - 136. Praticando: Transições entre as rotas
### 144 - Teste 8: Você se Lembra? Vue Router

## Seção 14: Conclusão
### 145 - 137. Conclusão do Curso