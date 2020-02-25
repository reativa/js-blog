---
title: como usar o minN no javascript es6
date: "2020-01-04"
description: ''
tags: array,math,beginner
---

Returns the `n` minimum elements from the provided array.
If `n` is greater than or equal to the provided array's length, then return the original array (sorted in ascending order).

Use `Array.prototype.sort()` combined with the spread operator (`...`) to create a shallow clone of the array and sort it in ascending order.
Use `Array.prototype.slice()` to get the specified number of elements.
Omit the second argument, `n`, to get a one-element array.

```js
const minN = (arr, n = 1) => [...arr].sort((a, b) => a - b).slice(0, n);
```

```js
minN([1, 2, 3]); // [1]
minN([1, 2, 3], 2); // [1,2]
```


[Acesse a Referência original](http://github.com/30-seconds/)
