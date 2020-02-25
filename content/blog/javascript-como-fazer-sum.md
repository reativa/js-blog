---
title: como usar o sum no javascript es6
date: "2020-01-04"
description: 'teste'
tags: math,array,beginner
---

Returns the sum of two or more numbers/arrays.

Use `Array.prototype.reduce()` to add each value to an accumulator, initialized with a value of `0`.

```js
const sum = (...arr) => [...arr].reduce((acc, val) => acc + val, 0);
```

```js
sum(1, 2, 3, 4); // 10
sum(...[1, 2, 3, 4]); // 10
```


[Acesse a Referência original](http://github.com/30-seconds/)
