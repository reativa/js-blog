---
title: como usar o initializeArrayWithValues no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,math,intermediate
---

Initializes and fills an array with the specified values.

Use `Array(n)` to create an array of the desired length, `fill(v)` to fill it with the desired values.
You can omit `val` to use a default value of `0`.

```js
const initializeArrayWithValues = (n, val = 0) => Array(n).fill(val);
```

```js
initializeArrayWithValues(5, 2); // [2, 2, 2, 2, 2]
```


[Acesse a Referência original](http://github.com/30-seconds/)
