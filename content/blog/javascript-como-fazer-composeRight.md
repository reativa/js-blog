---
title: como usar o composeRight no javascript es6
date: "2020-01-04"
description: 'teste'
tags: function,intermediate
---

Performs left-to-right function composition.

Use `Array.prototype.reduce()` to perform left-to-right function composition.
The first (leftmost) function can accept one or more arguments; the remaining functions must be unary.

```js
const composeRight = (...fns) => fns.reduce((f, g) => (...args) => g(f(...args)));
```

```js
const add = (x, y) => x + y;
const square = x => x * x;
const addAndSquare = composeRight(add, square);
addAndSquare(1, 2); // 9
```


[Acesse a Referência original](http://github.com/30-seconds/)
