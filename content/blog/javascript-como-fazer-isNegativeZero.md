---
title: como usar o isNegativeZero no javascript es6
date: "2020-01-04"
description: 'teste'
tags: math,utility,beginner
---

Checks if the given value is equal to negative zero (`-0`).

Checks whether a passed value is equal to `0` and if `1` divided by the value equals `-Infinity`.

```js
const isNegativeZero = val => val === 0 && 1 / val === -Infinity;
```

```js
isNegativeZero(-0); // true
isNegativeZero(0); // false
```


[Acesse a Referência original](http://github.com/30-seconds/)
