---
title: como usar o sample no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,random,beginner
---

Returns a random element from an array.

Use `Math.random()` to generate a random number, multiply it by `length` and round it off to the nearest whole number using `Math.floor()`.
This method also works with strings.

```js
const sample = arr => arr[Math.floor(Math.random() * arr.length)];
```

```js
sample([3, 7, 9, 11]); // 9
```


[Acesse a Referência original](http://github.com/30-seconds/)
