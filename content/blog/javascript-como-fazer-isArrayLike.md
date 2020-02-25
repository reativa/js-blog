---
title: como usar o isArrayLike no javascript es6
date: "2020-01-04"
description: ''
tags: type,array,intermediate
---

Checks if the provided argument is array-like (i.e. is iterable).

Check if the provided argument is not `null` and that its `Symbol.iterator` property is a function.

```js
const isArrayLike = obj => obj != null && typeof obj[Symbol.iterator] === 'function';
```

```js
isArrayLike(document.querySelectorAll('.className')); // true
isArrayLike('abc'); // true
isArrayLike(null); // false
```


[Acesse a Referência original](http://github.com/30-seconds/)
