---
title: como usar o vectorDistance no javascript es6
date: "2020-01-04"
description: 'teste'
tags: math,beginner
---

Returns the distance between two vectors.

Use `Array.prototype.reduce()`, `Math.pow()` and `Math.sqrt()` to calculate the Euclidean distance between two vectors.

```js
const vectorDistance = (...coords) => {
  let pointLength = Math.trunc(coords.length / 2);
  let sum = coords
    .slice(0, pointLength)
    .reduce((acc, val, i) => acc + Math.pow(val - coords[pointLength + i], 2), 0);
  return Math.sqrt(sum);
};
```

```js
vectorDistance(10, 0, 5, 20, 0, 10); // 11.180339887498949
```


[Acesse a Referência original](http://github.com/30-seconds/)
