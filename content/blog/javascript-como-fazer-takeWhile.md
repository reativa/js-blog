---
title: como usar o takeWhile no javascript es6
date: "2020-01-04"
description: ''
tags: array,function,intermediate
---

Removes elements in an array until the passed function returns `true`. Returns the removed elements.

Loop through the array, using a `for...of` loop over `Array.prototype.entries()` until the returned value from the function is `true`.
Return the removed elements, using `Array.prototype.slice()`.

```js
const takeWhile = (arr, func) => {
  for (const [i, val] of arr.entries()) if (func(val)) return arr.slice(0, i);
  return arr;
};
```

```js
takeWhile([1, 2, 3, 4], n => n >= 3); // [1, 2]
```


[Acesse a Referência original](http://github.com/30-seconds/)
