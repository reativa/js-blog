---
title: como usar o splitLines no javascript es6
date: "2020-01-04"
description: ''
tags: string,beginner
---

Splits a multiline string into an array of lines.

Use `String.prototype.split()` and a regular expression to match line breaks and create an array.

```js
const splitLines = str => str.split(/\r?\n/);
```

```js
splitLines('This\nis a\nmultiline\nstring.\n'); // ['This', 'is a', 'multiline', 'string.' , '']
```


[Acesse a Referência original](http://github.com/30-seconds/)
