---
date: "2020-02-11"
title: '11: O que o !! faz?'
description: "#PerguntasDeEntrevistas 11"
tags: es6,javascript,interview,entrevistas
---

https://www.instagram.com/tv/B9pJPohnn3E/

O operador **NÃO-duplo** (!!) força a conversão do valor um booleano EXPLICITAMENTE, basicamente, é uma maneira elegante de converter um valor em um booleano.

```js
console.log('!!null: ', !!null) //logs false
console.log('!!undefined: ', !!undefined) //logs false
console.log('!!\'\': ', !!'') //logs false
console.log('!!0: ', !!0) //logs false
console.log('!!NaN: ', !!NaN) //logs false
console.log('!!\' \' : ', !!' ') //logs true
console.log('!!{}: ', !!{}) //logs true
console.log('!![]: ', !![]) //logs true
console.log('!!1: ', !!1) //logs true
console.log('!![].length: ', !![].length) //logs false

```

Baseado no excelente artigo: [70 Interview Questions](https://dev.to/macmacky/70-javascript-interview-questions-5gfi#14-whats-the-difference-between-and-)