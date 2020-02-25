---
title: como usar o sortCharactersInString no javascript es6
date: "2020-01-04"
description: 'teste'
tags: string,beginner
---

Alphabetically sorts the characters in a string.

Use the spread operator (`...`), `Array.prototype.sort()` and  `String.localeCompare()` to sort the characters in `str`, recombine using `String.prototype.join('')`.

```js
const sortCharactersInString = str => [...str].sort((a, b) => a.localeCompare(b)).join('');
```

```js
sortCharactersInString('cabbage'); // 'aabbceg'
```


[Acesse a Referência original](http://github.com/30-seconds/)
