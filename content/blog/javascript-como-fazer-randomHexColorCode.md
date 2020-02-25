---
title: como usar o randomHexColorCode no javascript es6
date: "2020-01-04"
description: 'teste'
tags: utility,random,beginner
---

Generates a random hexadecimal color code.

Use `Math.random` to generate a random 24-bit(6x4bits) hexadecimal number. Use bit shifting and then convert it to an hexadecimal String using `toString(16)`.

```js
const randomHexColorCode = () => {
  let n = (Math.random() * 0xfffff * 1000000).toString(16);
  return '#' + n.slice(0, 6);
};
```

```js
randomHexColorCode(); // "#e34155"
```


[Acesse a Referência original](http://github.com/30-seconds/)
