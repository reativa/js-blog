---
title: como usar o ary no javascript es6
date: "2020-01-04"
description: 'teste'
tags: function,intermediate
---

Creates a function that accepts up to `n` arguments, ignoring any additional arguments.

Call the provided function, `fn`, with up to `n` arguments, using `Array.prototype.slice(0, n)` and the spread operator (`...`).

```js
const ary = (fn, n) => (...args) => fn(...args.slice(0, n));
```

```js
const firstTwoMax = ary(Math.max, 2);
[[2, 6, 'a'], [6, 4, 8], [10]].map(x => firstTwoMax(...x)); // [6, 6, 10]
```

[Acesse a Referência original](http://github.com/30-seconds/)
