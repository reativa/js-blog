---
title: como usar o take no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,beginner
---

Returns an array with n elements removed from the beginning.

Use `Array.prototype.slice()` to create a slice of the array with `n` elements taken from the beginning.

```js
const take = (arr, n = 1) => arr.slice(0, n);
```

```js
take([1, 2, 3], 5); // [1, 2, 3]
take([1, 2, 3], 0); // []
```


[Acesse a Referência original](http://github.com/30-seconds/)
