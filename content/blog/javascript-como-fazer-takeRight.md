---
title: como usar o takeRight no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,intermediate
---

Returns an array with n elements removed from the end.

Use `Array.prototype.slice()` to create a slice of the array with `n` elements taken from the end.

```js
const takeRight = (arr, n = 1) => arr.slice(arr.length - n, arr.length);
```

```js
takeRight([1, 2, 3], 2); // [ 2, 3 ]
takeRight([1, 2, 3]); // [3]
```


[Acesse a Referência original](http://github.com/30-seconds/)
