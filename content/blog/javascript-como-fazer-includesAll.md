---
title: como usar o includesAll no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,beginner
---

Returns `true` if all the elements ιν `values` are included in `arr`, `false` otherwise.

Use `Array.prototype.every()` and `Array.prototype.includes()` to check if all elements of `values` are included in `arr`.

```js
const includesAll = (arr, values) => values.every(v => arr.includes(v));
```

```js
includesAll([1, 2, 3, 4], [1, 4]); // true
includesAll([1, 2, 3, 4], [1, 5]); // false
```

[Acesse a Referência original](http://github.com/30-seconds/)
