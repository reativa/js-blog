---
title: como usar o hammingDistance no javascript es6
date: "2020-01-04"
description: 'teste'
tags: math,beginner
---

Calculates the Hamming distance between two values.

Use XOR operator (`^`) to find the bit difference between the two numbers, convert to a binary string using `toString(2)`.
Count and return the number of `1`s in the string, using `match(/1/g)`.

```js
const hammingDistance = (num1, num2) => ((num1 ^ num2).toString(2).match(/1/g) || '').length;
```

```js
hammingDistance(2, 3); // 1
```


[Acesse a Referência original](http://github.com/30-seconds/)
