---
title: como usar o digitize no javascript es6
date: "2020-01-04"
description: ''
tags: math,array,beginner
---

Converts a number to an array of digits.

Convert the number to a string, using the spread operator (`...`) to build an array.
Use `Array.prototype.map()` and `parseInt()` to transform each value to an integer.

```js
const digitize = n => [...`${n}`].map(i => parseInt(i));
```

```js
digitize(123); // [1, 2, 3]
```


[Acesse a Referência original](http://github.com/30-seconds/)
