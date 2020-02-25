---
title: como usar o objectFromPairs no javascript es6
date: "2020-01-04"
description: ''
tags: object,array,beginner
---

Creates an object from the given key-value pairs.

Use `Array.prototype.reduce()` to create and combine key-value pairs.

```js
const objectFromPairs = arr => arr.reduce((a, [key, val]) => ((a[key] = val), a), {});
```

```js
objectFromPairs([['a', 1], ['b', 2]]); // {a: 1, b: 2}
```


[Acesse a Referência original](http://github.com/30-seconds/)
