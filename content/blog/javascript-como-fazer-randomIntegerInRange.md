---
title: como usar o randomIntegerInRange no javascript es6
date: "2020-01-04"
description: 'teste'
tags: math,utility,random,beginner
---

Returns a random integer in the specified range.

Use `Math.random()` to generate a random number and map it to the desired range, using `Math.floor()` to make it an integer.

```js
const randomIntegerInRange = (min, max) => Math.floor(Math.random() * (max - min + 1)) + min;
```

```js
randomIntegerInRange(0, 5); // 2
```


[Acesse a Referência original](http://github.com/30-seconds/)
