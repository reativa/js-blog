---
title: como usar o compact no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,beginner
---

Removes falsy values from an array.

Use `Array.prototype.filter()` to filter out falsy values (`false`, `null`, `0`, `""`, `undefined`, and `NaN`).

```js
const compact = arr => arr.filter(Boolean);
```

```js
compact([0, 1, false, 2, '', 3, 'a', 'e' * 23, NaN, 's', 34]); // [ 1, 2, 3, 'a', 's', 34 ]
```


[Acesse a Referência original](http://github.com/30-seconds/)
