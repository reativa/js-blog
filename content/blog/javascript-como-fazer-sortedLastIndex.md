---
title: como usar o sortedLastIndex no javascript es6
date: "2020-01-04"
description: ''
tags: array,math,intermediate
---

Returns the highest index at which value should be inserted into array in order to maintain its sort order.

Check if the array is sorted in descending order (loosely).
Use `Array.prototype.reverse()` and `Array.prototype.findIndex()` to find the appropriate last index where the element should be inserted.

```js
const sortedLastIndex = (arr, n) => {
  const isDescending = arr[0] > arr[arr.length - 1];
  const index = arr.reverse().findIndex(el => (isDescending ? n <= el : n >= el));
  return index === -1 ? 0 : arr.length - index;
};
```

```js
sortedLastIndex([10, 20, 30, 30, 40], 30); // 4
```


[Acesse a Referência original](http://github.com/30-seconds/)
