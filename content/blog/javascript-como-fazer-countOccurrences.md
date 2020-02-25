---
title: como usar o countOccurrences no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,intermediate
---

Counts the occurrences of a value in an array.

Use `Array.prototype.reduce()` to increment a counter each time you encounter the specific value inside the array.

```js
const countOccurrences = (arr, val) => arr.reduce((a, v) => (v === val ? a + 1 : a), 0);
```

```js
countOccurrences([1, 1, 2, 1, 2, 3], 1); // 3
```


[Acesse a Referência original](http://github.com/30-seconds/)
