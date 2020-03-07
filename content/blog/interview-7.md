---
date: "2020-02-07"
title: '7: Qual é a diferença entre event.preventDefault() e event.stopPropagation()?'
description: "#PerguntasDeEntrevistas 7"
tags: es6,javascript,interview,entrevistas
---

O método `event.preventDefault()` **evita** o comportamento padrão de um elemento.

Se usado em um `form`, ele **impede** o envio (submit).

Se usado em um `anchor` (<a>), ele **impede** a navegação.

Se usado em um `contextmenu`, **impede** a exibição.

Enquanto o `event.stopPropagation()` interrompe a propagação de um evento ou impede a ocorrência do evento na fase de bubbling ou capturing (veja aula anterior).

### Como saber se o `event.preventDefault()` foi usado em um elemento?

Podemos usar a propriedade `event.defaultPrevented` no objeto de evento, ele retorna um `boolean` indicando se o `event.preventDefault()` foi chamado em um elemento específico.

Exemplinho da massa:
Caso queira executar o exemplo, use o [codepen.io](http://codepen.io)

HTML:

```html
<p><a id="link1" href="#link1">Esse sim vai funcionar pq a gente não fez nada nele.</a></p>
<p><a id="link2" href="#link2">Tenta ir pro link 2</a> (ele não vai ir pq a gente bloqueou)</p>
<p id="log"></p>
```

JS:

```js
function stopLink(event) {
  event.preventDefault();
}

function logClick(event) {
  const log = document.getElementById('log');
 
  if (event.target.tagName === 'A') {
    if (event.defaultPrevented) {
      log.innerText = 'Bloqueadão no baguio hein pai slc!\n' + log.innerText;
    }
    else {
      log.innerText = 'Esse sim pode!...\n' + log.innerText;
    }
  }
}

const a = document.getElementById('link2');
a.addEventListener('click', stopLink);
document.addEventListener('click', logClick);
```

Ainda não entendeu? Calma, acesse esses materiais:

- [Livro Eloquent JS - Manipulando Eventos](https://github.com/braziljs/eloquente-javascript/blob/master/chapters/14-manipulando-eventos.md)

- [Excelente Explicação da Loop infinito](http://loopinfinito.com.br/2013/05/14/entendendo-captura-e-propagacao-de-eventos/)


Baseado no excelente artigo: [70 Interview Questions](https://dev.to/macmacky/70-javascript-interview-questions-5gfi#14-whats-the-difference-between-and-)