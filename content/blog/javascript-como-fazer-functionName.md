---
title: como usar o functionName no javascript es6
date: "2020-01-04"
description: ''
tags: function,utility,beginner
---

Logs the name of a function.

Use `console.debug()` and the `name` property of the passed method to log the method's name to the `debug` channel of the console.

```js
const functionName = fn => (console.debug(fn.name), fn);
```

```js
functionName(Math.max); // max (logged in debug channel of console)
```


[Acesse a Referência original](http://github.com/30-seconds/)
