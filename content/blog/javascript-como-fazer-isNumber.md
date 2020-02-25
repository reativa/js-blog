---
title: como usar o isNumber no javascript es6
date: "2020-01-04"
description: 'teste'
tags: type,math,beginner
---

Checks if the given argument is a number.

Use `typeof` to check if a value is classified as a number primitive. 
To safeguard against `NaN`, check if `val === val` (as `NaN` has a `typeof` equal to `number` and is the only value not equal to itself).

```js
const isNumber = val => typeof val === 'number' && val === val;
```

```js
isNumber(1); // true
isNumber('1'); // false
isNumber(NaN); // false
```


[Acesse a Referência original](http://github.com/30-seconds/)
