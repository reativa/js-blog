---
title: como usar o getType no javascript es6
date: "2020-01-04"
description: ''
tags: type,beginner
---

Returns the native type of a value.

Returns lowercased constructor name of value, `"undefined"` or `"null"` if value is `undefined` or `null`.

```js
const getType = v =>
  v === undefined ? 'undefined' : v === null ? 'null' : v.constructor.name.toLowerCase();
```

```js
getType(new Set([1, 2, 3])); // 'set'
```


[Acesse a Referência original](http://github.com/30-seconds/)
