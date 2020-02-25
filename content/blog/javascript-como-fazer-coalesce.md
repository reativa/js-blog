---
title: como usar o coalesce no javascript es6
date: "2020-01-04"
description: ''
tags: utility,beginner
---

Returns the first non-null/undefined argument.

Use `Array.prototype.find()` to return the first non `null`/`undefined` argument.

```js
const coalesce = (...args) => args.find(_ => ![undefined, null].includes(_));
```

```js
coalesce(null, undefined, '', NaN, 'Waldo'); // ""
```


[Acesse a Referência original](http://github.com/30-seconds/)
