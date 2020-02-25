---
title: como usar o powerset no javascript es6
date: "2020-01-04"
description: ''
tags: math,beginner
---

Returns the powerset of a given array of numbers.

Use `Array.prototype.reduce()` combined with `Array.prototype.map()` to iterate over elements and combine into an array containing all combinations.

```js
const powerset = arr => arr.reduce((a, v) => a.concat(a.map(r => [v].concat(r))), [[]]);
```

```js
powerset([1, 2]); // [[], [1], [2], [2, 1]]
```


[Acesse a Referência original](http://github.com/30-seconds/)
