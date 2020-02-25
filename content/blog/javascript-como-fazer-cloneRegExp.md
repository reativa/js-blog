---
title: como usar o cloneRegExp no javascript es6
date: "2020-01-04"
description: ''
tags: utility,regexp,intermediate
---

Clones a regular expression.

Use `new RegExp()`, `RegExp.source` and `RegExp.flags` to clone the given regular expression.

```js
const cloneRegExp = regExp => new RegExp(regExp.source, regExp.flags);
```

```js
const regExp = /lorem ipsum/gi;
const regExp2 = cloneRegExp(regExp); // /lorem ipsum/gi
```


[Acesse a Referência original](http://github.com/30-seconds/)
