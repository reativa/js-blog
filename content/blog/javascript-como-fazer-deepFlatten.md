---
title: como usar o deepFlatten no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,recursion,intermediate
---

Deep flattens an array.

Use recursion.
Use `Array.prototype.concat()` with an empty array (`[]`) and the spread operator (`...`) to flatten an array.
Recursively flatten each element that is an array.

```js
const deepFlatten = arr => [].concat(...arr.map(v => (Array.isArray(v) ? deepFlatten(v) : v)));
```

```js
deepFlatten([1, [2], [[3], 4], 5]); // [1,2,3,4,5]
```


[Acesse a Referência original](http://github.com/30-seconds/)
