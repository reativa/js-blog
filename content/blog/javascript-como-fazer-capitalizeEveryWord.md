---
title: como usar o capitalizeEveryWord no javascript es6
date: "2020-01-04"
description: 'teste'
tags: string,regexp,intermediate
---

Capitalizes the first letter of every word in a string.

Use `String.prototype.replace()` to match the first character of each word and `String.prototype.toUpperCase()` to capitalize it.

```js
const capitalizeEveryWord = str => str.replace(/\b[a-z]/g, char => char.toUpperCase());
```

```js
capitalizeEveryWord('hello world!'); // 'Hello World!'
```


[Acesse a Referência original](http://github.com/30-seconds/)
