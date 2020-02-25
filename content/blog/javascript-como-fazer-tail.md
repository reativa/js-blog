---
title: como usar o tail no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,beginner
---

Returns all elements in an array except for the first one.

Return `Array.prototype.slice(1)` if the array's `length` is more than `1`, otherwise, return the whole array.

```js
const tail = arr => (arr.length > 1 ? arr.slice(1) : arr);
```

```js
tail([1, 2, 3]); // [2,3]
tail([1]); // [1]
```


[Acesse a Referência original](http://github.com/30-seconds/)