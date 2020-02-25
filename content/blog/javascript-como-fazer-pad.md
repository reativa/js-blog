---
title: como usar o pad no javascript es6
date: "2020-01-04"
description: ''
tags: string,beginner
---

Pads a string on both sides with the specified character, if it's shorter than the specified length.

Use `String.padStart()` and `String.padEnd()` to pad both sides of the given string.
Omit the third argument, `char`, to use the whitespace character as the default padding character.

```js
const pad = (str, length, char = ' ') =>
  str.padStart((str.length + length) / 2, char).padEnd(length, char);
```

```js
pad('cat', 8); // '  cat   '
pad(String(42), 6, '0'); // '004200'
pad('foobar', 3); // 'foobar'
```


[Acesse a Referência original](http://github.com/30-seconds/)
