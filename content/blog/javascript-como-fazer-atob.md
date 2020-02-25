---
title: como usar o atob no javascript es6
date: "2020-01-04"
description: 'teste'
tags: node,string,utility,beginner
---

Decodes a string of data which has been encoded using base-64 encoding.

Create a `Buffer` for the given string with base-64 encoding and use `Buffer.toString('binary')` to return the decoded string.

```js
const atob = str => Buffer.from(str, 'base64').toString('binary');
```

```js
atob('Zm9vYmFy'); // 'foobar'
```


[Acesse a Referência original](http://github.com/30-seconds/)
