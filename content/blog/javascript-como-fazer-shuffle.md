---
title: como usar o shuffle no javascript es6
date: "2020-01-04"
description: ''
tags: array,random,intermediate
---

Randomizes the order of the values of an array, returning a new array.

Use the [Fisher-Yates algorithm](https://en.wikipedia.org/wiki/Fisher%E2%80%93Yates_shuffle#Fisher_and_Yates'_original_method) to reorder the elements of the array.

```js
const shuffle = ([...arr]) => {
  let m = arr.length;
  while (m) {
    const i = Math.floor(Math.random() * m--);
    [arr[m], arr[i]] = [arr[i], arr[m]];
  }
  return arr;
};
```

```js
const foo = [1, 2, 3];
shuffle(foo); // [2, 3, 1], foo = [1, 2, 3]
```

[Acesse a Referência original](http://github.com/30-seconds/)
