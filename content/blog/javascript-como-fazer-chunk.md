---
title: como usar o chunk no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,intermediate
---

Chunks an array into smaller arrays of a specified size.

Use `Array.from()` to create a new array, that fits the number of chunks that will be produced.
Use `Array.prototype.slice()` to map each element of the new array to a chunk the length of `size`.
If the original array can't be split evenly, the final chunk will contain the remaining elements.

```js
const chunk = (arr, size) =>
  Array.from({ length: Math.ceil(arr.length / size) }, (v, i) =>
    arr.slice(i * size, i * size + size)
  );
```

```js
chunk([1, 2, 3, 4, 5], 2); // [[1,2],[3,4],[5]]
```


[Acesse a Referência original](http://github.com/30-seconds/)
