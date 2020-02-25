---
title: como usar o filterFalsy no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,beginner
---

Filters out the falsy values in an array.

Use `Array.prototype.filter()` to get an array containing only truthy values.

```js
const filterFalsy = arr => arr.filter(Boolean);
```

```js
filterFalsy(['', true, {}, false, 'sample', 1, 0]); // [true, {}, 'sample', 1]
```


[Acesse a Referência original](http://github.com/30-seconds/)
