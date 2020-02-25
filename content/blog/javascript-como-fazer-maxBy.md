---
title: como usar o maxBy no javascript es6
date: "2020-01-04"
description: ''
tags: math,array,function,beginner
---

Returns the maximum value of an array, after mapping each element to a value using the provided function.

Use `Array.prototype.map()` to map each element to the value returned by `fn`, `Math.max()` to get the maximum value.

```js
const maxBy = (arr, fn) => Math.max(...arr.map(typeof fn === 'function' ? fn : val => val[fn]));
```

```js
maxBy([{ n: 4 }, { n: 2 }, { n: 8 }, { n: 6 }], o => o.n); // 8
maxBy([{ n: 4 }, { n: 2 }, { n: 8 }, { n: 6 }], 'n'); // 8
```


[Acesse a Referência original](http://github.com/30-seconds/)
