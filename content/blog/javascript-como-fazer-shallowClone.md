---
title: como usar o shallowClone no javascript es6
date: "2020-01-04"
description: 'teste'
tags: object,beginner
---

Creates a shallow clone of an object.

Use `Object.assign()` and an empty object (`{}`) to create a shallow clone of the original.

```js
const shallowClone = obj => Object.assign({}, obj);
```

```js
const a = { x: true, y: 1 };
const b = shallowClone(a); // a !== b
```


[Acesse a Referência original](http://github.com/30-seconds/)
