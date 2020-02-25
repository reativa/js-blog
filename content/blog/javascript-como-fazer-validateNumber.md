---
title: como usar o validateNumber no javascript es6
date: "2020-01-04"
description: 'teste'
tags: utility,math,intermediate
---

Returns `true` if the given value is a number, `false` otherwise.

Use `!isNaN()` in combination with `parseFloat()` to check if the argument is a number.
Use `isFinite()` to check if the number is finite.
Use `Number()` to check if the coercion holds.

```js
const validateNumber = n => !isNaN(parseFloat(n)) && isFinite(n) && Number(n) == n;
```

```js
validateNumber('10'); // true
```


[Acesse a Referência original](http://github.com/30-seconds/)
