---
title: como usar o nthArg no javascript es6
date: "2020-01-04"
description: 'teste'
tags: utility,function,beginner
---

Creates a function that gets the argument at index `n`. If `n` is negative, the nth argument from the end is returned.

Use `Array.prototype.slice()` to get the desired argument at index `n`.

```js
const nthArg = n => (...args) => args.slice(n)[0];
```

```js
const third = nthArg(2);
third(1, 2, 3); // 3
third(1, 2); // undefined
const last = nthArg(-1);
last(1, 2, 3, 4, 5); // 5
```


[Acesse a Referência original](http://github.com/30-seconds/)
