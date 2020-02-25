---
title: como usar o all no javascript es6
date: "2020-01-04"
description: ''
tags: array,function,beginner
---

Returns `true` if the provided predicate function returns `true` for all elements in a collection, `false` otherwise.

Use `Array.prototype.every()` to test if all elements in the collection return `true` based on `fn`.
Omit the second argument, `fn`, to use `Boolean` as a default.

```js
const all = (arr, fn = Boolean) => arr.every(fn);
```

```js
all([4, 2, 3], x => x > 1); // true
all([1, 2, 3]); // true
```


[Acesse a Referência original](http://github.com/30-seconds/)
