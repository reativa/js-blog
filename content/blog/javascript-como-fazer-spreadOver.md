---
title: como usar o spreadOver no javascript es6
date: "2020-01-04"
description: ''
tags: function,intermediate
---

Takes a variadic function and returns a closure that accepts an array of arguments to map to the inputs of the function.

Use closures and the spread operator (`...`) to map the array of arguments to the inputs of the function.

```js
const spreadOver = fn => argsArr => fn(...argsArr);
```

```js
const arrayMax = spreadOver(Math.max);
arrayMax([1, 2, 3]); // 3
```

[Acesse a Referência original](http://github.com/30-seconds/)
