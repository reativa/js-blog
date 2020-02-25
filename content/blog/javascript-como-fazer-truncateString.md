---
title: como usar o truncateString no javascript es6
date: "2020-01-04"
description: ''
tags: string,beginner
---

Truncates a string up to a specified length.

Determine if the string's `length` is greater than `num`.
Return the string truncated to the desired length, with `'...'` appended to the end or the original string.

```js
const truncateString = (str, num) =>
  str.length > num ? str.slice(0, num > 3 ? num - 3 : num) + '...' : str;
```

```js
truncateString('boomerang', 7); // 'boom...'
```


[Acesse a Referência original](http://github.com/30-seconds/)
