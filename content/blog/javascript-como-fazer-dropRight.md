---
title: como usar o dropRight no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,beginner
---

Returns a new array with `n` elements removed from the right.

Use `Array.prototype.slice()` to remove the specified number of elements from the right.

```js
const dropRight = (arr, n = 1) => arr.slice(0, -n);
```

```js
dropRight([1, 2, 3]); // [1,2]
dropRight([1, 2, 3], 2); // [1]
dropRight([1, 2, 3], 42); // []
```


[Acesse a Referência original](http://github.com/30-seconds/)
