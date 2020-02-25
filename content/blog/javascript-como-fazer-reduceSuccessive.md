---
title: como usar o reduceSuccessive no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,function,intermediate
---

Applies a function against an accumulator and each element in the array (from left to right), returning an array of successively reduced values.

Use `Array.prototype.reduce()` to apply the given function to the given array, storing each new result.

```js
const reduceSuccessive = (arr, fn, acc) =>
  arr.reduce((res, val, i, arr) => (res.push(fn(res.slice(-1)[0], val, i, arr)), res), [acc]);
```

```js
reduceSuccessive([1, 2, 3, 4, 5, 6], (acc, val) => acc + val, 0); // [0, 1, 3, 6, 10, 15, 21]
```


[Acesse a Referência original](http://github.com/30-seconds/)
