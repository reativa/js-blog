---
title: como usar o symmetricDifferenceWith no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,function,intermediate
---

Returns the symmetric difference between two arrays, using a provided function as a comparator.

Use `Array.prototype.filter()` and `Array.prototype.findIndex()` to find the appropriate values.

```js
const symmetricDifferenceWith = (arr, val, comp) => [
  ...arr.filter(a => val.findIndex(b => comp(a, b)) === -1),
  ...val.filter(a => arr.findIndex(b => comp(a, b)) === -1)
];
```

```js
symmetricDifferenceWith(
  [1, 1.2, 1.5, 3, 0],
  [1.9, 3, 0, 3.9],
  (a, b) => Math.round(a) === Math.round(b)
); // [1, 1.2, 3.9]
```


[Acesse a Referência original](http://github.com/30-seconds/)
