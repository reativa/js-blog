---
title: como usar o delay no javascript es6
date: "2020-01-04"
description: ''
tags: function,intermediate
---

Invokes the provided function after `wait` milliseconds.

Use `setTimeout()` to delay execution of `fn`.
Use the spread (`...`) operator to supply the function with an arbitrary number of arguments.

```js
const delay = (fn, wait, ...args) => setTimeout(fn, wait, ...args);
```

```js
delay(
  function(text) {
    console.log(text);
  },
  1000,
  'later'
); // Logs 'later' after one second.
```


[Acesse a Referência original](http://github.com/30-seconds/)
