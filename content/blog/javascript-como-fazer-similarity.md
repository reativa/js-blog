---
title: como usar o similarity no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,math,beginner
---

Returns an array of elements that appear in both arrays.

Use `Array.prototype.filter()` to remove values that are not part of `values`, determined using `Array.prototype.includes()`.

```js
const similarity = (arr, values) => arr.filter(v => values.includes(v));
```

```js
similarity([1, 2, 3], [1, 2, 4]); // [1, 2]
```


[Acesse a Referência original](http://github.com/30-seconds/)
