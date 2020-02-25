---
title: como usar o pull no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,intermediate
---

Mutates the original array to filter out the values specified.

Use `Array.prototype.filter()` and `Array.prototype.includes()` to pull out the values that are not needed.
Use `Array.prototype.length = 0` to mutate the passed in an array by resetting it's length to zero and `Array.prototype.push()` to re-populate it with only the pulled values.

```js
const pull = (arr, ...args) => {
  let argState = Array.isArray(args[0]) ? args[0] : args;
  let pulled = arr.filter(v => !argState.includes(v));
  arr.length = 0;
  pulled.forEach(v => arr.push(v));
};
```

```js
let myArray = ['a', 'b', 'c', 'a', 'b', 'c'];
pull(myArray, 'a', 'c'); // myArray = [ 'b', 'b' ]
```

[Acesse a Referência original](http://github.com/30-seconds/)
