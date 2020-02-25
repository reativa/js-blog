---
title: como usar o union no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,math,beginner
---

Returns every element that exists in any of the two arrays once.

Create a `Set` with all values of `a` and `b` and convert to an array.

```js
const union = (a, b) => Array.from(new Set([...a, ...b]));
```

```js
union([1, 2, 3], [4, 3, 2]); // [1,2,3,4]
```


[Acesse a Referência original](http://github.com/30-seconds/)
