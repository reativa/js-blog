---
title: como usar o sumBy no javascript es6
date: "2020-01-04"
description: 'teste'
tags: math,array,function,intermediate
---

Returns the sum of an array, after mapping each element to a value using the provided function.

Use `Array.prototype.map()` to map each element to the value returned by `fn`, `Array.prototype.reduce()` to add each value to an accumulator, initialized with a value of `0`.

```js
const sumBy = (arr, fn) =>
  arr.map(typeof fn === 'function' ? fn : val => val[fn]).reduce((acc, val) => acc + val, 0);
```

```js
sumBy([{ n: 4 }, { n: 2 }, { n: 8 }, { n: 6 }], o => o.n); // 20
sumBy([{ n: 4 }, { n: 2 }, { n: 8 }, { n: 6 }], 'n'); // 20
```


[Acesse a Referência original](http://github.com/30-seconds/)
