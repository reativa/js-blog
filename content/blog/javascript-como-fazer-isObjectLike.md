---
title: como usar o isObjectLike no javascript es6
date: "2020-01-04"
description: 'teste'
tags: type,object,beginner
---

Checks if a value is object-like.

Check if the provided value is not `null` and its `typeof` is equal to `'object'`.

```js
const isObjectLike = val => val !== null && typeof val === 'object';
```

```js
isObjectLike({}); // true
isObjectLike([1, 2, 3]); // true
isObjectLike(x => x); // false
isObjectLike(null); // false
```


[Acesse a Referência original](http://github.com/30-seconds/)
