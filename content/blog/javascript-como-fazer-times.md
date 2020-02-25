---
title: como usar o times no javascript es6
date: "2020-01-04"
description: 'teste'
tags: function,intermediate
---

Iterates over a callback `n` times

Use `Function.call()` to call `fn` `n` times or until it returns `false`.
Omit the last argument, `context`, to use an `undefined` object (or the global object in non-strict mode).

```js
const times = (n, fn, context = undefined) => {
  let i = 0;
  while (fn.call(context, i) !== false && ++i < n) {}
};
```

```js
var output = '';
times(5, i => (output += i));
console.log(output); // 01234
```


[Acesse a Referência original](http://github.com/30-seconds/)
