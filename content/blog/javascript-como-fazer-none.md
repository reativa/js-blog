---
title: como usar o none no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,function,beginner
---

Returns `true` if the provided predicate function returns `false` for all elements in a collection, `false` otherwise.

Use `Array.prototype.some()` to test if any elements in the collection return `true` based on `fn`.
Omit the second argument, `fn`, to use `Boolean` as a default.

```js
const none = (arr, fn = Boolean) => !arr.some(fn);
```

```js
none([0, 1, 3, 0], x => x == 2); // true
none([0, 0, 0]); // true
```


[Acesse a Referência original](http://github.com/30-seconds/)
