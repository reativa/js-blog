---
title: como usar o isFunction no javascript es6
date: "2020-01-04"
description: ''
tags: type,function,beginner
---

Checks if the given argument is a function.

Use `typeof` to check if a value is classified as a function primitive.

```js
const isFunction = val => typeof val === 'function';
```

```js
isFunction('x'); // false
isFunction(x => x); // true
```


[Acesse a Referência original](http://github.com/30-seconds/)
