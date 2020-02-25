---
title: como usar o bindKey no javascript es6
date: "2020-01-04"
description: ''
tags: function,object,intermediate
---

Creates a function that invokes the method at a given key of an object, optionally adding any additional supplied parameters to the beginning of the arguments.

Return a `function` that uses `Function.prototype.apply()` to bind `context[fn]` to `context`.
Use the spread operator (`...`) to prepend any additional supplied parameters to the arguments.

```js
const bindKey = (context, fn, ...boundArgs) => (...args) =>
  context[fn].apply(context, [...boundArgs, ...args]);
```

```js
const freddy = {
  user: 'fred',
  greet: function(greeting, punctuation) {
    return greeting + ' ' + this.user + punctuation;
  }
};
const freddyBound = bindKey(freddy, 'greet');
console.log(freddyBound('hi', '!')); // 'hi fred!'
```


[Acesse a Referência original](http://github.com/30-seconds/)
