---
title: como usar o includesAny no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,beginner
---

Returns `true` if at least one element of values is included in arr , `false` otherwise.

Use `Array.prototype.some()` and `Array.prototype.includes()` to check if at least one element of `values` is included in `arr`.

```js
const includesAny = (arr, values) => values.some(v => arr.includes(v));
```

```js
includesAny([1, 2, 3, 4], [2, 9]); // true
includesAny([1, 2, 3, 4], [8, 9]); // false
```

[Acesse a Referência original](http://github.com/30-seconds/)
