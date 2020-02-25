---
title: como usar o dropWhile no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,function,intermediate
---

Removes elements in an array until the passed function returns `true`. Returns the remaining elements in the array.

Loop through the array, using `Array.prototype.slice()` to drop the first element of the array until the returned value from the function is `true`.
Returns the remaining elements.

```js
const dropWhile = (arr, func) => {
  while (arr.length > 0 && !func(arr[0])) arr = arr.slice(1);
  return arr;
};
```

```js
dropWhile([1, 2, 3, 4], n => n >= 3); // [3,4]
```


[Acesse a Referência original](http://github.com/30-seconds/)
