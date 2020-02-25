---
title: como usar o compactWhitespace no javascript es6
date: "2020-01-04"
description: 'teste'
tags: string,regexp,beginner
---

Returns a string with whitespaces compacted.

Use `String.prototype.replace()` with a regular expression to replace all occurrences of 2 or more whitespace characters with a single space.

```js
const compactWhitespace = str => str.replace(/\s{2,}/g, ' ');
```

```js
compactWhitespace('Lorem    Ipsum'); // 'Lorem Ipsum'
compactWhitespace('Lorem \n Ipsum'); // 'Lorem Ipsum'
```


[Acesse a Referência original](http://github.com/30-seconds/)
