---
title: como usar o over no javascript es6
date: "2020-01-04"
description: ''
tags: function,intermediate
---

Creates a function that invokes each provided function with the arguments it receives and returns the results.

Use `Array.prototype.map()` and `Function.prototype.apply()` to apply each function to the given arguments.

```js
const over = (...fns) => (...args) => fns.map(fn => fn.apply(null, args));
```

```js
const minMax = over(Math.min, Math.max);
minMax(1, 2, 3, 4, 5); // [1,5]
```

[Acesse a Referência original](http://github.com/30-seconds/)
