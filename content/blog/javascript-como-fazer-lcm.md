---
title: como usar o lcm no javascript es6
date: "2020-01-04"
description: ''
tags: math,recursion,beginner
---

Returns the least common multiple of two or more numbers.

Use the greatest common divisor (GCD) formula and the fact that `lcm(x,y) = x * y / gcd(x,y)` to determine the least common multiple.
The GCD formula uses recursion.

```js
const lcm = (...arr) => {
  const gcd = (x, y) => (!y ? x : gcd(y, x % y));
  const _lcm = (x, y) => (x * y) / gcd(x, y);
  return [...arr].reduce((a, b) => _lcm(a, b));
};
```

```js
lcm(12, 7); // 84
lcm(...[1, 3, 4, 5]); // 60
```


[Acesse a Referência original](http://github.com/30-seconds/)
