---
title: como usar o objectToPairs no javascript es6
date: "2020-01-04"
description: ''
tags: object,array,beginner
---

Creates an array of key-value pair arrays from an object.

Use `Object.keys()` and `Array.prototype.map()` to iterate over the object's keys and produce an array with key-value pairs.

```js
const objectToPairs = obj => Object.keys(obj).map(k => [k, obj[k]]);
```

```js
objectToPairs({ a: 1, b: 2 }); // [ ['a', 1], ['b', 2] ]
```


[Acesse a Referência original](http://github.com/30-seconds/)
