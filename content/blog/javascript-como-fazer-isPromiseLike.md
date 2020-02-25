---
title: como usar o isPromiseLike no javascript es6
date: "2020-01-04"
description: 'teste'
tags: type,function,promise,intermediate
---

Returns `true` if an object looks like a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise), `false` otherwise.

Check if the object is not `null`, its `typeof` matches either `object` or `function` and if it has a `.then` property, which is also a `function`.

```js
const isPromiseLike = obj =>
  obj !== null &&
  (typeof obj === 'object' || typeof obj === 'function') &&
  typeof obj.then === 'function';
```

```js
isPromiseLike({
  then: function() {
    return '';
  }
}); // true
isPromiseLike(null); // false
isPromiseLike({}); // false
```


[Acesse a Referência original](http://github.com/30-seconds/)
