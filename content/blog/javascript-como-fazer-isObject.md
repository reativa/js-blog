---
title: como usar o isObject no javascript es6
date: "2020-01-04"
description: 'teste'
tags: type,object,beginner
---

Returns a boolean determining if the passed value is an object or not.

Uses the  `Object` constructor to create an object wrapper for the given value. 
If the value is `null` or `undefined`, create and return an empty object. Οtherwise, return an object of a type that corresponds to the given value.

```js
const isObject = obj => obj === Object(obj);
```

```js
isObject([1, 2, 3, 4]); // true
isObject([]); // true
isObject(['Hello!']); // true
isObject({ a: 1 }); // true
isObject({}); // true
isObject(true); // false
```


[Acesse a Referência original](http://github.com/30-seconds/)
