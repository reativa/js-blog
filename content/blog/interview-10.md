---
date: "2020-02-10"
title: '10: Por que ao comparar dois objetos semelhantes ele retorna falso em JavaScript?'
description: "#PerguntasDeEntrevistas 10"
tags: es6,javascript,interview,entrevistas
---

https://www.instagram.com/tv/B9mke7fFuWY/

Suponha que temos um exemplo abaixo.

```js
let a = { a: 1 }
let b = { a: 1 }
let c = a

console.log(a === b) // logga false mesmo que tenha a mesma propriedade
console.log(a === c) // logga true hmmmmmmm
```

**JavaScript** compara *objetos* e *primitivos* de maneira diferente. 

Nas *primitivas*, as compara por **valor** enquanto nos *objetos* por **referência** ou pelo **endereço na memória em que a variável está armazenada**.

É por isso que o primeiro `log` retorna `false` e o segundo `log` retorna `true`. `a` e `c`tem a mesma referência e `a` e `b` não.

Por isso se você quiser comparar objetos use o stringify por exemplo: 

```js
function jsonEqual(object1, object2) {
    return JSON.stringify(object1) === JSON.stringify(object2);
}
jsonEqual(a, b) // true
```

Baseado no excelente artigo: [70 Interview Questions](https://dev.to/macmacky/70-javascript-interview-questions-5gfi#14-whats-the-difference-between-and-)