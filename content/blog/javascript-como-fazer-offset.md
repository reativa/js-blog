---
title: como usar o offset no javascript es6
date: "2020-01-04"
description: ''
tags: array,beginner
---

Moves the specified amount of elements to the end of the array.

Use `Array.prototype.slice()` twice to get the elements after the specified index and the elements before that.
Use the spread operator(`...`) to combine the two into one array.
If `offset` is negative, the elements will be moved from end to start.

```js
const offset = (arr, offset) => [...arr.slice(offset), ...arr.slice(0, offset)];
```

```js
offset([1, 2, 3, 4, 5], 2); // [3, 4, 5, 1, 2]
offset([1, 2, 3, 4, 5], -2); // [4, 5, 1, 2, 3]
```


[Acesse a Referência original](http://github.com/30-seconds/)
