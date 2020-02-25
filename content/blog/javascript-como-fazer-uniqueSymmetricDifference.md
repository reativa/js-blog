---
title: como usar o uniqueSymmetricDifference no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,math,intermediate
---

Returns the unique symmetric difference between two arrays, not containing duplicate values from either array.

Use `Array.prototype.filter()` and `Array.prototype.includes()` on each array to remove values contained in the other, then create a `Set` from the results, removing duplicate values.

```js
const uniqueSymmetricDifference = (a, b) => [
  ...new Set([...a.filter(v => !b.includes(v)), ...b.filter(v => !a.includes(v))])
];
```

```js
uniqueSymmetricDifference([1, 2, 3], [1, 2, 4]); // [3, 4]
uniqueSymmetricDifference([1, 2, 2], [1, 3, 1]); // [2, 3]
```


[Acesse a Referência original](http://github.com/30-seconds/)
