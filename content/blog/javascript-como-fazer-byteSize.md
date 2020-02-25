---
title: como usar o byteSize no javascript es6
date: "2020-01-04"
description: 'teste'
tags: string,beginner
---

Returns the length of a string in bytes.

Convert a given string to a [`Blob` Object](https://developer.mozilla.org/en-US/docs/Web/API/Blob) and find its `size`.

```js
const byteSize = str => new Blob([str]).size;
```

```js
byteSize('😀'); // 4
byteSize('Hello World'); // 11
```


[Acesse a Referência original](http://github.com/30-seconds/)
