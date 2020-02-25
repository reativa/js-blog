---
title: como usar o mapNumRange no javascript es6
date: "2020-01-04"
description: ''
tags: math,beginner
---

Maps a number from one range to another range.

Returns `num` mapped between `outMin`-`outMax` from `inMin`-`inMax`.

```js
const mapNumRange = (num, inMin, inMax, outMin, outMax) =>
  ((num - inMin) * (outMax - outMin)) / (inMax - inMin) + outMin;
```

```js
mapNumRange(5, 0, 10, 0, 100); // 50
```


[Acesse a Referência original](http://github.com/30-seconds/)
