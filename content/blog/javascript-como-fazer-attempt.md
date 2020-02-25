---
title: como usar o attempt no javascript es6
date: "2020-01-04"
description: ''
tags: function,intermediate
---

Attempts to invoke a function with the provided arguments, returning either the result or the caught error object.

Use a `try... catch` block to return either the result of the function or an appropriate error.

```js
const attempt = (fn, ...args) => {
  try {
    return fn(...args);
  } catch (e) {
    return e instanceof Error ? e : new Error(e);
  }
};
```

```js
var elements = attempt(function(selector) {
  return document.querySelectorAll(selector);
}, '>_>');
if (elements instanceof Error) elements = []; // elements = []
```


[Acesse a Referência original](http://github.com/30-seconds/)
