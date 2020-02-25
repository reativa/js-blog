---
title: como usar o matches no javascript es6
date: "2020-01-04"
description: ''
tags: object,type,intermediate
---

Compares two objects to determine if the first one contains equivalent property values to the second one.

Use `Object.keys(source)` to get all the keys of the second object, then `Array.prototype.every()`, `Object.hasOwnProperty()` and strict comparison to determine if all keys exist in the first object and have the same values.

```js
const matches = (obj, source) =>
  Object.keys(source).every(key => obj.hasOwnProperty(key) && obj[key] === source[key]);
```

```js
matches({ age: 25, hair: 'long', beard: true }, { hair: 'long', beard: true }); // true
matches({ hair: 'long', beard: true }, { age: 25, hair: 'long', beard: true }); // false
```


[Acesse a Referência original](http://github.com/30-seconds/)
