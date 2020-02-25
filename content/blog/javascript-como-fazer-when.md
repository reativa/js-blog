---
title: como usar o when no javascript es6
date: "2020-01-04"
description: ''
tags: function,intermediate
---

Tests a value, `x`, against a predicate function. If `true`, return `fn(x)`. Else, return `x`. 

Return a function expecting a single value, `x`, that returns the appropriate value based on `pred`.

```js
const when = (pred, whenTrue) => x => (pred(x) ? whenTrue(x) : x);
```

```js
const doubleEvenNumbers = when(x => x % 2 === 0, x => x * 2);
doubleEvenNumbers(2); // 4
doubleEvenNumbers(1); // 1
```


[Acesse a Referência original](http://github.com/30-seconds/)
