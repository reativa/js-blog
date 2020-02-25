---
title: como usar o frequencies no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,intermediate
---

Returns an object with the unique values of an array as keys and their frequencies as the values.

Use `Array.prototype.reduce()` to map unique values to an object's keys, adding to existing keys every time the same value is encountered.

```js
const frequencies = arr =>
  arr.reduce((a, v) => {
    a[v] = a[v] ? a[v] + 1 : 1;
    return a;
  }, {});
```

```js
frequencies(['a', 'b', 'a', 'c', 'a', 'a', 'b']); // { a: 4, b: 2, c: 1 }
```

[Acesse a Referência original](http://github.com/30-seconds/)