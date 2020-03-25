---
date: "2020-02-06"
title: '6: O que é a propagação de eventos'
description: "#PerguntasDeEntrevistas 6"
tags: es6,javascript,interview,entrevistas
---

https://www.instagram.com/tv/B9c6bd-nWcw/?utm_source=ig_web_copy_link

Caso queira executar o exemplo, use o [codepen.io](http://codepen.io)

Imagina o seguinte HTML:

```html
<div id="avo">
    <div id="pai">
        <div id="filhao">Filhao</div>
    </div>
</div>
```

Se a gente botar um evento de clique no `#filhao` e no `#avo` qual executaria primeiro?

```js
document.getElementById("avo").addEventListener("click", function (event) {
  console.log("#avo clicado")
})

document.getElementById("filhao").addEventListener("click", function (event) {
  console.log("#filhao clicado")
})

```

A propagação de eventos ocorre no DOM inteiro, e ele pode acontecer de baixo pra cima ou de cima pra baixo, não entendi, como assim?

O evento não vai acontecer magicamente só no seu botão, imagina que tem um mensageiro maluco que vai de nó em nó tentando avisar "mano, o #um foi clicado, ai vai pro próximo e fala a mesma coisa: mano, o #um foi clicado" até chegar em todos os nós, só que esse doidinho pode começar a fazer essa checagem a partir do:

> botão -> em direção a window (Bubbling)

ou da

> window -> em direção ao botão. (Capturing)

Exemplo:

[![Propagação de Eventos](https://res.cloudinary.com/practicaldev/image/fetch/s--Azk8KRbD--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/hjayqa99iejfhbsujlqd.png)](https://res.cloudinary.com/practicaldev/image/fetch/s--Azk8KRbD--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/hjayqa99iejfhbsujlqd.png)

**A Propagação de Eventos** possui **três** fases.

1.  [Fase de captura](#8-whats-event-capturing) - o evento começa a partir de `window` então desce para todos os elementos até atingir o elemento de destino.
2.  [Fase de destino](#12-what-is-eventtarget-) - o evento atingiu o elemento de destino.
3.  [Fase de Bubbling](#7-whats-event-bubbling) - o evento borbulha do elemento alvo e depois sobe todos os elementos até atingir o `window`.


Ainda não entendeu? Calma, acesse esses materiais:

- [Livro Eloquent JS - Manipulando Eventos](https://github.com/braziljs/eloquente-javascript/blob/master/chapters/14-manipulando-eventos.md)

- [Excelente Explicação da Loop infinito](http://loopinfinito.com.br/2013/05/14/entendendo-captura-e-propagacao-de-eventos/)


Baseado no excelente artigo: [70 Interview Questions](https://dev.to/macmacky/70-javascript-interview-questions-5gfi#14-whats-the-difference-between-and-)