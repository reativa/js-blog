---
title: como usar o isPrimitive no javascript es6
date: "2020-01-04"
description: ''
tags: type,function,array,string,intermediate
---

Returns a boolean determining if the passed value is primitive or not.

Create an object from `val` and compare it with `val` to determine if the passed value is primitive (i.e. not equal to the created object).

```js
const isPrimitive = val => Object(val) !== val;
```

```js
isPrimitive(null); // true
isPrimitive(50); // true
isPrimitive('Hello!'); // true
isPrimitive(false); // true
isPrimitive(Symbol()); // true
isPrimitive([]); // false
```


[Acesse a Referência original](http://github.com/30-seconds/)
