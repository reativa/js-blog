---
title: como usar o compose no javascript es6
date: "2020-01-04"
description: ''
tags: function,intermediate
---

Performs right-to-left function composition.

Use `Array.prototype.reduce()` to perform right-to-left function composition.
The last (rightmost) function can accept one or more arguments; the remaining functions must be unary.

```js
const compose = (...fns) => fns.reduce((f, g) => (...args) => f(g(...args)));
```

```js
const add5 = x => x + 5;
const multiply = (x, y) => x * y;
const multiplyAndAdd5 = compose(
  add5,
  multiply
);
multiplyAndAdd5(5, 2); // 15
```


[Acesse a Referência original](http://github.com/30-seconds/)
