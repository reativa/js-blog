---
title: como usar o unary no javascript es6
date: "2020-01-04"
description: ''
tags: function,beginner
---

Creates a function that accepts up to one argument, ignoring any additional arguments.

Call the provided function, `fn`, with just the first argument given.

```js
const unary = fn => val => fn(val);
```

```js
['6', '8', '10'].map(unary(parseInt)); // [6, 8, 10]
```

[Acesse a Referência original](http://github.com/30-seconds/)
