---
title: como usar o nthElement no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,beginner
---

Returns the nth element of an array.

Use `Array.prototype.slice()` to get an array containing the nth element at the first place.
If the index is out of bounds, return `undefined`.
Omit the second argument, `n`, to get the first element of the array.

```js
const nthElement = (arr, n = 0) => (n === -1 ? arr.slice(n) : arr.slice(n, n + 1))[0];
```

```js
nthElement(['a', 'b', 'c'], 1); // 'b'
nthElement(['a', 'b', 'b'], -3); // 'a'
```


[Acesse a Referência original](http://github.com/30-seconds/)
