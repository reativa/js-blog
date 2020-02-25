---
title: como usar o average no javascript es6
date: "2020-01-04"
description: 'teste'
tags: math,array,beginner
---

Returns the average of two or more numbers.

Use `Array.prototype.reduce()` to add each value to an accumulator, initialized with a value of `0`, divide by the `length` of the array.

```js
const average = (...nums) => nums.reduce((acc, val) => acc + val, 0) / nums.length;
```

```js
average(...[1, 2, 3]); // 2
average(1, 2, 3); // 2
```


[Acesse a Referência original](http://github.com/30-seconds/)
