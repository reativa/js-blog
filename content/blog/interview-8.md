---
date: "2020-02-08"
title: '8: Diferenças de event.target e event.currentTarget?'
description: "#PerguntasDeEntrevistas 8"
tags: es6,javascript,interview,entrevistas
---

https://www.instagram.com/tv/B9hokfIHKDX/

O **event.target** é o elemento no qual o evento **ocorreu** ou o elemento que **acionou** o evento.

Exemplo de HTML:

Caso queira executar o exemplo, use o [codepen.io](http://codepen.io)

```html
<div onclick="clickFunc(event)" style="text-align: centermargin:15px
border:1px solid redborder-radius:3px">
    <div style="margin: 25px border:1px solid royalblueborder-radius:3px">
        <div style="margin:25pxborder:1px solid skyblueborder-radius:3px">
          <button style="margin:10px">
             Button
          </button>
        </div>
    </div>
  </div>
```

Exemplo de JavaScript.

```js
function clickFunc(event) {
  console.log(event.target) // botão
  //console.log(event.currentTarget) // div 
}

```

Nesse caso ele aciona no BOTÃO e não na DIV, por mais que tenhamos configurado o evento na div em si, quem é o target é o cara que foi acionado no evento.

### currentTarget ?

O **event.currentTarget** é o elemento no qual anexamos **explicitamente o** manipulador de eventos (div nesse caso).

Mesmo exemplo, só vamos mudar no JS para usar o `currentTarget`:

```js
function clickFunc(event) {
  // console.log(event.target) // botão
  console.log(event.currentTarget) // div 
}

```

Nesse caso ele vai apontar pra div (onde configuramos a ação) e não pro botão.

Baseado no excelente artigo: [70 Interview Questions](https://dev.to/macmacky/70-javascript-interview-questions-5gfi#14-whats-the-difference-between-and-)