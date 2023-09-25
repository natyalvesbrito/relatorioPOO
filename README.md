# Relatório - Programação orientada a objetos

## Conceitos Básicos
- Codificou classes - Quais classes? Para que serve?

No WebApp:

Classe Editor e classe Navegador.

A clase Editor serve para pegar o elemento na página html por meio do Id e possui um método dentro dela para posteriormente, quando o usuário clicar no botão de edição, irá receber um input e alterar o valor do elemento na página.

A classe Navegador serve para navegar entre as páginas html, foi utilizada para criar um objeto para cada página e possui um método que posteriormente foi utilizado para levar à página do objeto quando o usuário clicar no botão.


- Codificou atributos - Em quais classes? Quais atributos? Por que esses nomes e tipos?

No WebApp:

```js
class Editor {
    constructor(elementId) {
        this.element = document.getElementById(elementId);
    }
```

O atributo "element" armazena o Id do elemento no html na classe Editor, para depois poder ser modificado pelo método "editar()".

O nome é porque armazena o elemento html, o tipo é um objeto do DOM, um elemento HTML.

```js
class Navegador {
    constructor(elementId, page) {
        this.element = document.getElementById(elementId);
        this.page = page;
    }
```

O atributo "element" na classe Navegador faz o mesmo que na classe Editor, além disso, essa classe possui o atributo "page" que irá guardar o endereço para a página html que irá ser direcionado no objeto.

O nome do "element" é porque armazena o elemento html, o tipo é um objeto do DOM, um elemento HTML.

O nome do "page" é porque ele armazena uma string com o endereço html da página.


- Codificou métodos - Em quais classes? Quais métodos? Por que o esses nomes e parâmetros?

No web app:

```js
class Editor {
    ...
    editar() {
        var novoValor = prompt(`Digite o novo valor para ${this.element.id}:`);
        if (novoValor !== null) {
            this.element.textContent = novoValor;
        }
    }
}

class Navegador {
    ...
    navegar() {
        window.location.href = this.page;
    }
}
```

Método editar() e método navegar() nas classes como representa o código acima. O método editar possui esse nome porque ele edita o elemento html na página, já o método navegar possui esse nome porque ele navega entre as páginas html.


- Codificou atributos estáticos
Em quais classes? Por que eles sãos estáticos? Por que esses nomes e tipos?

- Codificou métodos estáticos
Em quais classes? Quais métodos? Por que o esses nomes e parâmetros?

- Codificou métodos construtores - Em quais classes?

Sim, na classe Editor e Navegador.

```js
class Editor {
    constructor(elementId) {
        this.element = document.getElementById(elementId);
    }
    ...
}

class Navegador {
    constructor(elementId, page) {
        this.element = document.getElementById(elementId);
        this.page = page;
    }
    ...
}
```

- Codificou métodos destrutores
Em quais classes?

- Codificou atributos protegidos e/ou privados
Em quais classes? Quais atributos? Por que não são públicos?

- Codificou métodos protegidos e/ou privados
Em quais classes? Quais métodos? Por que não são públicos?

- Codificou interfaces ou classes puramente virtuais
Quais classes/interfaces?

- Codificou classes abstratas ou classes virtuais
Quais classes?

- Instanciou objetos - Quais objetos?

```js
const idadeEditor = new Editor("idade");
const pesoEditor = new Editor("peso");
const racaEditor = new Editor("raça");
const corEditor = new Editor("cor");

...

const alimentacaoNav = new Navegador("botaoAlimentacao", "paginaalimentacao.html");
const principalNav = new Navegador("botaoPrincipal", "paginaprincipal.html");
const saudeNav = new Navegador("botaoSaude", "paginasaude.html");
```

- Instalou e usou bibliotecas de terceiros 
Quais bibliotecas? Para que server?

- Codificou enums
Quais enum?

- Codificou propriedades
Em quais classes? Quais propriedades?


## Design

## Boas Práticas

## Extras

