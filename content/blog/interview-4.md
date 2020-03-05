---
date: "2020-02-04"
title: '4: Qual é a maneira mais rápida de converter uma string em um número?'
description: "#PerguntasDeEntrevistas 4"
tags: es6,javascript,interview,entrevistas
---

De acordo com a [documentação](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Unary_plus) da [MDN,](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Unary_plus) `+` é a maneira mais rápida de converter uma string em um número porque ela não executa nenhuma operação no valor se já for um número.

Exemplo:

```js
console.log(typeof '123') // string
console.log(typeof +'123') // number
```

Baseado no excelente artigo: [70 Interview Questions](https://dev.to/macmacky/70-javascript-interview-questions-5gfi#14-whats-the-difference-between-and-)