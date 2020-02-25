---
title: como usar o escapeRegExp no javascript es6
date: "2020-01-04"
description: ''
tags: string,regexp,intermediate
---

Escapes a string to use in a regular expression.

Use `String.prototype.replace()` to escape special characters.

```js
const escapeRegExp = str => str.replace(/[.*+?^${}()|[\]\\]/g, '\\$&');
```

```js
escapeRegExp('(test)'); // \\(test\\)
```


[Acesse a Referência original](http://github.com/30-seconds/)
