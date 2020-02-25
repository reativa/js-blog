---
title: como usar o toSafeInteger no javascript es6
date: "2020-01-04"
description: ''
tags: math,beginner
---

Converts a value to a safe integer.

Use `Math.max()` and `Math.min()` to find the closest safe value.
Use `Math.round()` to convert to an integer.

```js
const toSafeInteger = num =>
  Math.round(Math.max(Math.min(num, Number.MAX_SAFE_INTEGER), Number.MIN_SAFE_INTEGER));
```

```js
toSafeInteger('3.2'); // 3
toSafeInteger(Infinity); // 9007199254740991
```


[Acesse a Referência original](http://github.com/30-seconds/)
