---
title: como usar o forEachRight no javascript es6
date: "2020-01-04"
description: ''
tags: array,function,intermediate
---

Executes a provided function once for each array element, starting from the array's last element.

Use `Array.prototype.slice(0)` to clone the given array, `Array.prototype.reverse()` to reverse it and `Array.prototype.forEach()` to iterate over the reversed array.

```js
const forEachRight = (arr, callback) =>
  arr
    .slice(0)
    .reverse()
    .forEach(callback);
```

```js
forEachRight([1, 2, 3, 4], val => console.log(val)); // '4', '3', '2', '1'
```


[Acesse a Referência original](http://github.com/30-seconds/)
