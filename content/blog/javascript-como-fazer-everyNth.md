---
title: como usar o everyNth no javascript es6
date: "2020-01-04"
description: ''
tags: array,beginner
---

Returns every nth element in an array.

Use `Array.prototype.filter()` to create a new array that contains every nth element of a given array.

```js
const everyNth = (arr, nth) => arr.filter((e, i) => i % nth === nth - 1);
```

```js
everyNth([1, 2, 3, 4, 5, 6], 2); // [ 2, 4, 6 ]
```


[Acesse a Referência original](http://github.com/30-seconds/)
