---
date: "2020-02-12"
title: '12: Como executar várias expressões em uma linha?'
description: "#PerguntasDeEntrevistas 12"
tags: es6,javascript,interview,entrevistas
---

https://www.instagram.com/tv/B9rt_w-BUft/

Podemos usar a vírgula `,` para executar várias expressões em uma linha. Ele executa da esquerda para a direita e retorna o valor do último item à direita.

```js
let x = 5

x = (x++ , x = addFive(x), x *= 2, x -= 5, x += 10)

function addFive(num) {
  return num + 5
}

```
O que desgraça essa budega faz?

> x++ // x vira 1

> x = addFive(x) // 1 + 5 = x vira 6

> x *= 2 // 7 * 2 = x vira 22

> x -= 5 // x vira 17

> x += 10 // 17 + 10 = x vira 27

Nunca seja a desgraça de programador que escreve um código xemelento desse.

Se eu fosse reescrever esse código eu deixaria assim:

```js
let originalValue = 5

const INCREMENTED_VALUE = originalValue++ 
const INCREMENTED_VALUE_PLUS_FIVE = addFive(INCREMENTED_VALUE)
const RESULT_VALUE_MULTIPLIED_BY_TWO = INCREMENTED_VALUE_PLUS_FIVE * 2
const DECREMENTED_RESULT_BY_FIVE = RESULT_VALUE_MULTIPLIED_BY_TWO - 5
const RESULT_ADDED_WITH_TEN = DECREMENTED_RESULT_BY_FIVE + 10
originalValue = RESULT_ADDED_WITH_TEN

function addFive(num) {
  return num + 5
}
```


Baseado no excelente artigo: [70 Interview Questions](https://dev.to/macmacky/70-javascript-interview-questions-5gfi#14-whats-the-difference-between-and-)