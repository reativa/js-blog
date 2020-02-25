---
title: como usar o uniqueElements no javascript es6
date: "2020-01-04"
description: ''
tags: array,beginner
---

Returns all unique values of an array.

Use ES6 `Set` and the `...rest` operator to discard all duplicated values.

```js
const uniqueElements = arr => [...new Set(arr)];
```

```js
uniqueElements([1, 2, 2, 3, 4, 4, 5]); // [1, 2, 3, 4, 5]
```


[Acesse a Referência original](http://github.com/30-seconds/)
