---
title: como usar o negate no javascript es6
date: "2020-01-04"
description: 'teste'
tags: function,beginner
---

Negates a predicate function.

Take a predicate function and apply the not operator (`!`) to it with its arguments.

```js
const negate = func => (...args) => !func(...args);
```

```js
[1, 2, 3, 4, 5, 6].filter(negate(n => n % 2 === 0)); // [ 1, 3, 5 ]
```


[Acesse a Referência original](http://github.com/30-seconds/)
