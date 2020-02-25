---
title: como usar o deepClone no javascript es6
date: "2020-01-04"
description: 'teste'
tags: object,recursion,intermediate
---

Creates a deep clone of an object.

Use recursion.
Check if the passed object is `null` and, if so, return `null`.
Use `Object.assign()` and an empty object (`{}`) to create a shallow clone of the original.
Use `Object.keys()` and `Array.prototype.forEach()` to determine which key-value pairs need to be deep cloned.

```js
const deepClone = obj => {
  if (obj === null) return null;
  let clone = Object.assign({}, obj);
  Object.keys(clone).forEach(
    key => (clone[key] = typeof obj[key] === 'object' ? deepClone(obj[key]) : obj[key])
  );
  return Array.isArray(obj) && obj.length
    ? (clone.length = obj.length) && Array.from(clone)
    : Array.isArray(obj)
      ? Array.from(obj)
      : clone;
};
```

```js
const a = { foo: 'bar', obj: { a: 1, b: 2 } };
const b = deepClone(a); // a !== b, a.obj !== b.obj
```


[Acesse a Referência original](http://github.com/30-seconds/)
