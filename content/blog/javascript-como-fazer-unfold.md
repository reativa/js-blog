---
title: como usar o unfold no javascript es6
date: "2020-01-04"
description: ''
tags: function,array,intermediate
---

Builds an array, using an iterator function and an initial seed value.

Use a `while` loop and `Array.prototype.push()` to call the function repeatedly until it returns `false`.
The iterator function accepts one argument (`seed`) and must always return an array with two elements ([`value`, `nextSeed`]) or `false` to terminate.

```js
const unfold = (fn, seed) => {
  let result = [],
    val = [null, seed];
  while ((val = fn(val[1]))) result.push(val[0]);
  return result;
};
```

```js
var f = n => (n > 50 ? false : [-n, n + 10]);
unfold(f, 10); // [-10, -20, -30, -40, -50]
```


[Acesse a Referência original](http://github.com/30-seconds/)
