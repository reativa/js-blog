---
title: como usar o approximatelyEqual no javascript es6
date: "2020-01-04"
description: ''
tags: math,beginner
---

Checks if two numbers are approximately equal to each other.

Use `Math.abs()` to compare the absolute difference of the two values to `epsilon`.
Omit the third parameter, `epsilon`, to use a default value of `0.001`.

```js
const approximatelyEqual = (v1, v2, epsilon = 0.001) => Math.abs(v1 - v2) < epsilon;
```

```js
approximatelyEqual(Math.PI / 2.0, 1.5708); // true
```


[Acesse a Referência original](http://github.com/30-seconds/)
