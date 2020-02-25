---
title: como usar o reverseString no javascript es6
date: "2020-01-04"
description: ''
tags: string,array,beginner
---

Reverses a string.

Use the spread operator (`...`) and `Array.prototype.reverse()` to reverse the order of the characters in the string.
Combine characters to get a string using `String.prototype.join('')`.

```js
const reverseString = str => [...str].reverse().join('');
```

```js
reverseString('foobar'); // 'raboof'
```


[Acesse a Referência original](http://github.com/30-seconds/)
