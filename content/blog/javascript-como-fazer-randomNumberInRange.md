---
title: como usar o randomNumberInRange no javascript es6
date: "2020-01-04"
description: ''
tags: math,utility,random,beginner
---

Returns a random number in the specified range.

Use `Math.random()` to generate a random value, map it to the desired range using multiplication.

```js
const randomNumberInRange = (min, max) => Math.random() * (max - min) + min;
```

```js
randomNumberInRange(2, 10); // 6.0211363285087005
```


[Acesse a Referência original](http://github.com/30-seconds/)
