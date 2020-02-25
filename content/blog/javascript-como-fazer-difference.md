---
title: como usar o difference no javascript es6
date: "2020-01-04"
description: ''
tags: array,math,beginner
---

Returns the difference between two arrays.

Create a `Set` from `b`, then use `Array.prototype.filter()` on `a` to only keep values not contained in `b`.

```js
const difference = (a, b) => {
  const s = new Set(b);
  return a.filter(x => !s.has(x));
};
```

```js
difference([1, 2, 3], [1, 2, 4]); // [3]
```


[Acesse a Referência original](http://github.com/30-seconds/)
