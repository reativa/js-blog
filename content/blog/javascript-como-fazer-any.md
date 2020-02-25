---
title: como usar o any no javascript es6
date: "2020-01-04"
description: ''
tags: array,function,beginner
---

Returns `true` if the provided predicate function returns `true` for at least one element in a collection, `false` otherwise.

Use `Array.prototype.some()` to test if any elements in the collection return `true` based on `fn`.
Omit the second argument, `fn`, to use `Boolean` as a default.

```js
const any = (arr, fn = Boolean) => arr.some(fn);
```

```js
any([0, 1, 2, 0], x => x >= 2); // true
any([0, 0, 1, 0]); // true
```


[Acesse a Referência original](http://github.com/30-seconds/)
