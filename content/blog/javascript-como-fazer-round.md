---
title: como usar o round no javascript es6
date: "2020-01-04"
description: ''
tags: math,intermediate
---

Rounds a number to a specified amount of digits.

Use `Math.round()` and template literals to round the number to the specified number of digits.
Omit the second argument, `decimals` to round to an integer.

```js
const round = (n, decimals = 0) => Number(`${Math.round(`${n}e${decimals}`)}e-${decimals}`);
```

```js
round(1.005, 2); // 1.01
```


[Acesse a Referência original](http://github.com/30-seconds/)
