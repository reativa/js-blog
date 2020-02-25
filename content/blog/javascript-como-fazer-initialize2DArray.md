---
title: como usar o initialize2DArray no javascript es6
date: "2020-01-04"
description: ''
tags: array,intermediate
---

Initializes a 2D array of given width and height and value.

Use `Array.prototype.map()` to generate h rows where each is a new array of size w initialize with value. If the value is not provided, default to `null`.

```js
const initialize2DArray = (w, h, val = null) =>
  Array.from({ length: h }).map(() => Array.from({ length: w }).fill(val));
```

```js
initialize2DArray(2, 2, 0); // [[0,0], [0,0]]
```


[Acesse a Referência original](http://github.com/30-seconds/)
