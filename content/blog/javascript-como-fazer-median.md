---
title: como usar o median no javascript es6
date: "2020-01-04"
description: 'teste'
tags: math,array,intermediate
---

Returns the median of an array of numbers.

Find the middle of the array, use `Array.prototype.sort()` to sort the values.
Return the number at the midpoint if `length` is odd, otherwise the average of the two middle numbers.

```js
const median = arr => {
  const mid = Math.floor(arr.length / 2),
    nums = [...arr].sort((a, b) => a - b);
  return arr.length % 2 !== 0 ? nums[mid] : (nums[mid - 1] + nums[mid]) / 2;
};
```

```js
median([5, 6, 50, 1, -5]); // 5
```


[Acesse a Referência original](http://github.com/30-seconds/)
