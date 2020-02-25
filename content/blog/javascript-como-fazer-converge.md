---
title: como usar o converge no javascript es6
date: "2020-01-04"
description: ''
tags: function,intermediate
---

Accepts a converging function and a list of branching functions and returns a function that applies each branching function to the arguments and the results of the branching functions are passed as arguments to the converging function.

Use `Array.prototype.map()` and `Function.prototype.apply()` to apply each function to the given arguments.
Use the spread operator (`...`) to call `coverger` with the results of all other functions.

```js
const converge = (converger, fns) => (...args) => converger(...fns.map(fn => fn.apply(null, args)));
```

```js
const average = converge((a, b) => a / b, [
  arr => arr.reduce((a, v) => a + v, 0),
  arr => arr.length
]);
average([1, 2, 3, 4, 5, 6, 7]); // 4
```


[Acesse a Referência original](http://github.com/30-seconds/)
