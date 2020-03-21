---
title: como usar o all no javascript es6
date: "2020-01-04"
description: ''
tags: array,function,beginner
---

Retorna `verdadeiro` caso o valor todos os valores que você passe no array do primeiro argumento, condizem com a segunda verificação.

Caso você não passe valor algum, ele só vai checar se os valores são verdadeiros.

```js
const all = (arr, fn = Boolean) => arr.every(fn);
```

```js
all([4, 2, 3], x => x > 1); // true
all([1, 2, 3]); // true
```


[Acesse a Referência original](http://github.com/30-seconds/)
