---
title: como usar o bind no javascript es6
date: "2020-01-04"
description: 'teste'
tags: function,object,intermediate
---

Creates a function that invokes `fn` with a given context, optionally adding any additional supplied parameters to the beginning of the arguments.

Return a `function` that uses `Function.prototype.apply()` to apply the given `context` to `fn`.
Use `Array.prototype.concat()` to prepend any additional supplied parameters to the arguments.

```js
const bind = (fn, context, ...boundArgs) => (...args) => fn.apply(context, [...boundArgs, ...args]);
```

```js
function greet(greeting, punctuation) {
  return greeting + ' ' + this.user + punctuation;
}
const freddy = { user: 'fred' };
const freddyBound = bind(greet, freddy);
console.log(freddyBound('hi', '!')); // 'hi fred!'
```


[Acesse a Referência original](http://github.com/30-seconds/)
