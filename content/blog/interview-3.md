---
date: "2020-01-09"
title: '3: O que o operador OR || faz?'
description: "#PerguntasDeEntrevistas 3"
tags: es6,javascript,interview,entrevistas
---
### 3: O que o operador OR || faz?

O operador `||` ou **Logical OR** encontra a primeira expressão *verdadeira* em seus operandos e a retorna. Isso também emprega curto-circuito para evitar trabalho desnecessário.

```js
console.log(null || 1 || undefined) // logga 1, nem chega a executar o resto
```

Ele inicializava valores padrões antes do ES6 chegar. 

```javascript
function logName(name) {
  var n = name || "Mark" // atribui a variável Mark caso não tenha nome
  console.log(n)
}

logName() //logs "Mark"
```

Exemplo no ES6:

```js
function logName(name = 'Mark') { // atribui a variável Mark caso não tenha nome
  var n = name 
  console.log(n)
}

logName() //logs "Mark"
```




Baseado no excelente artigo: [70 Interview Questions](https://dev.to/macmacky/70-javascript-interview-questions-5gfi#14-whats-the-difference-between-and-)