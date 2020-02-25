---
title: como usar o sdbm no javascript es6
date: "2020-01-04"
description: ''
tags: math,utility,intermediate
---

Hashes the input string into a whole number.

Use `String.prototype.split('')` and `Array.prototype.reduce()` to create a hash of the input string, utilizing bit shifting.

```js
const sdbm = str => {
  let arr = str.split('');
  return arr.reduce(
    (hashCode, currentVal) =>
      (hashCode = currentVal.charCodeAt(0) + (hashCode << 6) + (hashCode << 16) - hashCode),
    0
  );
};
```

```js
sdbm('name'); // -3521204949
```


[Acesse a Referência original](http://github.com/30-seconds/)
