---
title: como usar o RGBToHex no javascript es6
date: "2020-01-04"
description: 'teste'
tags: utility,intermediate
---

Converts the values of RGB components to a color code.

Convert given RGB parameters to hexadecimal string using bitwise left-shift operator (`<<`) and `toString(16)`, then `String.padStart(6,'0')` to get a 6-digit hexadecimal value.

```js
const RGBToHex = (r, g, b) => ((r << 16) + (g << 8) + b).toString(16).padStart(6, '0');
```

```js
RGBToHex(255, 165, 1); // 'ffa501'
```


[Acesse a Referência original](http://github.com/30-seconds/)