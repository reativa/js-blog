---
title: como usar o intersectionWith no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,function,intermediate
---

Returns a list of elements that exist in both arrays, using a provided comparator function.

Use `Array.prototype.filter()` and `Array.prototype.findIndex()` in combination with the provided comparator to determine intersecting values.

```js
const intersectionWith = (a, b, comp) => a.filter(x => b.findIndex(y => comp(x, y)) !== -1);
```

```js
intersectionWith([1, 1.2, 1.5, 3, 0], [1.9, 3, 0, 3.9], (a, b) => Math.round(a) === Math.round(b)); // [1.5, 3, 0]
```


[Acesse a Referência original](http://github.com/30-seconds/)
