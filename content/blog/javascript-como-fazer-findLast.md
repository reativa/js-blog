---
title: como usar o findLast no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,beginner
---

Returns the last element for which the provided function returns a truthy value.

Use `Array.prototype.filter()` to remove elements for which `fn` returns falsy values, `Array.prototype.pop()` to get the last one.

```js
const findLast = (arr, fn) => arr.filter(fn).pop();
```

```js
findLast([1, 2, 3, 4], n => n % 2 === 1); // 3
```


[Acesse a Referência original](http://github.com/30-seconds/)
