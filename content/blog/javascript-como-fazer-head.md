---
title: como usar o head no javascript es6
date: "2020-01-04"
description: ''
tags: array,beginner
---

Returns the head of a list.

Check if `arr` is truthy and has a `length` property, use `arr[0]` if possible to return the first element, otherwise return `undefined`.

```js
const head = arr => (arr && arr.length ? arr[0] : undefined);
```

```js
head([1, 2, 3]); // 1
head([]); // undefined
head(null); // undefined
head(undefined); // undefined
```

[Acesse a Referência original](http://github.com/30-seconds/)
