---
title: como usar o flip no javascript es6
date: "2020-01-04"
description: 'teste'
tags: function,intermediate
---

Flip takes a function as an argument, then makes the first argument the last.

Return a closure that takes variadic inputs, and splices the last argument to make it the first argument before applying the rest.

```js
const flip = fn => (first, ...rest) => fn(...rest, first);
```

```js
let a = { name: 'John Smith' };
let b = {};
const mergeFrom = flip(Object.assign);
let mergePerson = mergeFrom.bind(null, a);
mergePerson(b); // == b
b = {};
Object.assign(b, a); // == b
```

[Acesse a Referência original](http://github.com/30-seconds/)
