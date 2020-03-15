---
date: "2020-02-15"
title: '15: O que são closures?'
description: "#PerguntasDeEntrevistas 15"
tags: es6,javascript,interview,entrevistas
---


### 15. O que são closures ?

**Closures** é um tópico controverso. O que eu gostaria de ouvir como entrevistador seria algo como:

> Closures significa que uma função interna sempre tem acesso as variáveis e aos parâmetros de sua função externa, mesmo após o retorno da função externa.

Cê ta ligado que dá pra criar função dentro de função né?

exemplo:

```js
function OuterFunction () {
  var outerVariable = 1

  function InnerFunction () {
    console.log(outerVariable)
  }

  InnerFunction()
}
```

No exemplo acima, InnerFunction() pode acessar a variável `outerVariable` mesmo ela estando declarada no escopo de cima.

```js
function OuterFunction () {
  var outerVariable = 100
  var parameters = JSON.stringify(arguments)

  function InnerFunction () {
    console.log(
      `[OUTER CLOSURE] OuterVariable continua viva no meu coração: ${outerVariable}`
    )
    console.log(
      `[OUTER CLOSURE] Parâmetros que mandaram para o Outer: ${parameters}`
    )
    console.log(`[INNER] Meus parâmetros: ${JSON.stringify(arguments)}`)
  }

  return InnerFunction
}

var innerFunc = OuterFunction(123, "vral")
innerFunc()
```

Ele chama a `OuterFunction` mas a única referência que você tem é a da `InnerFunction`, mas MESMO ASSIM você continua tendo acesso as variáveis que foram passadas pelo parâmetro para a `OuterFunction` bem como o que foi declarado nela que no caso é a `outerVariable`

Isso permite que ninguém externamente consiga mudar essas variáveis de dentro do escopo do OuterFunction, olha só:

```js
var counter = (function () {
  var privateCounter = 0

  function changeBy (val) {
    privateCounter += val
  }

  return {
    increment: function () {
      changeBy(1)
    },

    decrement: function () {
      changeBy(-1)
    },

    value: function () {
      return privateCounter
    },
  }
})()

var original = counter.value()
console.log("Contador Original: ", original)

alert(counter.value()) // altera o valor

counter.increment()
counter.increment()

console.log("Contador Original: ", original) // continua a mesma bosta
alert(counter.value())

counter.decrement()
alert(counter.value())

console.log("Contador Original: ", original) // continua a mesma bosta

```

-   Explicação do [Douglinhas](http://www.crockford.com/javascript/private.html) (um dos principais devs de JS do mundo).

-   Tutorial gostosinho do [TutorialsTeacher](https://www.tutorialsteacher.com/javascript/closure-in-javascript).

Baseado no excelente artigo: [70 Interview Questions](https://dev.to/macmacky/70-javascript-interview-questions-5gfi)
