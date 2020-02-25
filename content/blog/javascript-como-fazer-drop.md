---
title: como usar o drop no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,beginner
---

Returns a new array with `n` elements removed from the left.

Use `Array.prototype.slice()` to remove the specified number of elements from the left.

```js
const drop = (arr, n = 1) => arr.slice(n);
```

```js
drop([1, 2, 3]); // [2,3]
drop([1, 2, 3], 2); // [3]
drop([1, 2, 3], 42); // []
```


[Acesse a Referência original](http://github.com/30-seconds/)
