---
title: como usar o inRange no javascript es6
date: "2020-01-04"
description: 'teste'
tags: math,beginner
---

Checks if the given number falls within the given range.

Use arithmetic comparison to check if the given number is in the specified range.
If the second parameter, `end`, is not specified, the range is considered to be from `0` to `start`.

```js
const inRange = (n, start, end = null) => {
  if (end && start > end) [end, start] = [start, end];
  return end == null ? n >= 0 && n < start : n >= start && n < end;
};
```

```js
inRange(3, 2, 5); // true
inRange(3, 4); // true
inRange(2, 3, 5); // false
inRange(3, 2); // false
```


[Acesse a Referência original](http://github.com/30-seconds/)
