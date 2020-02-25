---
title: como usar o last no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,beginner
---

Returns the last element in an array.

Check if `arr` is truthy and has a `length` property, use `arr.length - 1` to compute the index of the last element of the given array and return it, otherwise return `undefined`.

```js
const last = arr => (arr && arr.length ? arr[arr.length - 1] : undefined);
```

```js
last([1, 2, 3]); // 3
last([]); // undefined
last(null); // undefined
last(undefined); // undefined
```

[Acesse a Referência original](http://github.com/30-seconds/)
