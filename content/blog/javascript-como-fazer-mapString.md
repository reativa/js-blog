---
title: como usar o mapString no javascript es6
date: "2020-01-04"
description: ''
tags: string,array,function,utility,beginner
---

Creates a new string with the results of calling a provided function on every character in the calling string.

Use `String.prototype.split('')` and `Array.prototype.map()` to call the provided function, `fn`, for each character in `str`.
Use `Array.prototype.join('')` to recombine the array of characters into a string.
The callback function, `fn`, takes three arguments (the current character, the index of the current character and the string `mapString` was called upon).

```js
const mapString = (str, fn) =>
  str
    .split('')
    .map((c, i) => fn(c, i, str))
    .join('');
```

```js
mapString('lorem ipsum', c => c.toUpperCase()); // 'LOREM IPSUM'
```


[Acesse a Referência original](http://github.com/30-seconds/)
