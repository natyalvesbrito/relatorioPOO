# Relatório - Programação orientada a objetos

## Conceitos Básicos

### Pontos realizados 

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

- Codificou atributos protegidos e/ou privados - Em quais classes? Quais atributos? Por que não são públicos?

No comedouro:

```cpp
class Horario {

  private:

    int hora;
    int minuto;
...
class Refeicao {

  private:

    Horario horarioDefinido;
    bool refeicaoFeita;
```

Os atributos privados estão nas classes Horario e Refeicao, como no código acima. Eles não são públicos para impedir modificações erradas e gerar problemas no código, sendo assim, podemos ter mais controle dos resultados.

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

- Instalou e usou bibliotecas de terceiros  - Quais bibliotecas? Para que servem?

No comedouro:

```cpp
#include <WiFi.h>   -- conecta e gerencia redes wi-fi
#include "time.h" -- obter o horário atual
#include <FirebaseESP32.h> -- conectar o ESP32 com o Firebase, para gerenciar os dados em nuvem
#include <ESP32Servo.h> -- controla os motores servo
#include <string.h> -- manipular strings
```

### Pontos ainda não realizados 

- Codificou métodos destrutores
Em quais classes?

- Codificou atributos estáticos
Em quais classes? Por que eles sãos estáticos? Por que esses nomes e tipos?

- Codificou métodos estáticos
Em quais classes? Quais métodos? Por que o esses nomes e parâmetros?

- Codificou interfaces ou classes puramente virtuais
Quais classes/interfaces?

- Codificou classes abstratas ou classes virtuais
Quais classes?

- Codificou métodos protegidos e/ou privados
Em quais classes? Quais métodos? Por que não são públicos?

- Codificou enums
Quais enum?

- Codificou propriedades - Em quais classes? Quais propriedades?

## Design

### Pontos realizados 

- Identificou e codificou classes de dados - Quais classes?

As classes no webapp: Editor e Navegador.

As classes no comedouro: Comedor, Horario e Refeicao.

- Usou diagramas UML para discutir a solução - Fazer upload dos diagramas.

Diagrama está nesse repositório.

- Ocultou informações usando atributos e ou métodos protected/private - Em quais classes? Quais atributos e métodos? Por que foi importante ocultar esses dados?

As classes Horario e Refeicao possuem atributos privados para impedir problemas com alterações indevidas.

### Pontos não realizados 

- Identificou e codificou classes de comportamento
Quais classes?

- Usou polimorfismo
Com quais classes?

- Usou objetos imutáveis
Quais objetos?

- Ocultou informações usando interfaces ou classes puramente virtuais
Em quais classes/interfaces?

- Codificou classes imutáveis
Quais classes? Por que foi importante elas serem imutáveis?

## Boas Práticas

### Pontos realizados 

- Usou conceitos de SOLID - Quais conceitos? Onde?

Separação de responsabilidades, nas funções, classes e métodos.

Função calcularTotal() faz apenas isso.

```js
function calcularTotal() {
        const selects = document.querySelectorAll('.refeicao-item select[name="quantidade"]');
        let total = 0;


        selects.forEach(select => {
            total += parseInt(select.value);
        });

        document.getElementById("total-value").querySelector('h3').textContent = total + 'g';
    }

    document.querySelectorAll('.refeicao-item select[name="quantidade"]').forEach(select => {
        select.addEventListener('change', calcularTotal);
    });
```

classe Navegador apenas navega entre páginas.

```js
class Navegador {
        constructor(elementId, page) {
            this.element = document.getElementById(elementId);
            this.page = page;
        }

        navegar() {
            window.location.href = this.page;
        }
    }
```

Classe Editor apenas edita elementos na página.

```js
class Editor {
    constructor(elementId) {
        this.element = document.getElementById(elementId);
    }

    editar() {
        var novoValor = prompt(`Digite o novo valor para ${this.element.id}:`);
        if (novoValor !== null) {
            this.element.textContent = novoValor;
        }
    }
}
```


- Usou conceitos de código limpo - Quais conceitos? Onde?

Nomenclatura descritiva: nossas variáveis possuem nomes auto-descritivos de acordo com a função, por exemplo, "Editor", "Navegador", "Horario" e "Refeicao".

Separação de responsabilidades (Single Responsibility Principle): cada função, classe e método possui apenas uma responsabilidade, por exemplo, a função "calcularTotal()" faz apenas isso, pega os valores que precisam ser somados, soma e retorna o valor.

Evitar código duplicado: refatoramos partes do código para poder evitar repetição, criando as classes e funções.


### Pontos não realizados 

- Codificou testes unitários - Como executo os testes?

- Codificou padrões de projeto Quais padrões? Onde?

## Extras

### Pontos realizados 

- Versionou todo o projeto integrador com GIT - Fazer upload da saída do gitlog

Saída do gitlog está no repositório.

- Publicou todo projeto integrador no Gitlab, Github, ou semelhantes - Enviar link

Link: https://github.com/leticia-hub/projeto-integrador


### Pontos não realizados 

- Implantou/Hospedou ( deploy ) o projeto integrador
Enviar link e descrever como foi feito deploy

- Contribuiu com o material da disciplina criando “issues”
Enviar link das issues

- Contribuiu com o material da disciplina criando PRs/MRs
Enviar link dos PRs/MRs

- Publicou pacotes/bibliotecas do projeto integrador no pypi, maven central, ou semelhantes - Enviar link