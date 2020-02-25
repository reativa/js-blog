---
title: como usar o isStream no javascript es6
date: "2020-01-04"
description: 'teste'
tags: node,type,intermediate
---

Checks if the given argument is a stream.

Check if the value is different from `null`, use `typeof` to check if the value is of type `object` and the `pipe` property is of type `function`.

```js
const isStream = val => val !== null && typeof val === 'object' && typeof val.pipe === 'function';
```

```js
const fs = require('fs');
isStream(fs.createReadStream('test.txt')); // true
```


[Acesse a Referência original](http://github.com/30-seconds/)
