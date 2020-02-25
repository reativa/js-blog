---
title: como usar o isUpperCase no javascript es6
date: "2020-01-04"
description: ''
tags: string,utility,beginner
---

Checks if a string is upper case.

Convert the given string to upper case, using `String.prototype.toUpperCase()` and compare it to the original.

```js
const isUpperCase = str => str === str.toUpperCase();
```

```js
isUpperCase('ABC'); // true
isUpperCase('A3@$'); // true
isUpperCase('aB4'); // false
```

[Acesse a Referência original](http://github.com/30-seconds/)
