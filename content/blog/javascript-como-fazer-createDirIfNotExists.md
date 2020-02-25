---
title: como usar o createDirIfNotExists no javascript es6
date: "2020-01-04"
description: 'teste'
tags: node,beginner
---

Creates a directory, if it does not exist.

Use `fs.existsSync()` to check if the directory exists, `fs.mkdirSync()` to create it.

```js
const fs = require('fs');
const createDirIfNotExists = dir => (!fs.existsSync(dir) ? fs.mkdirSync(dir) : undefined);
```

```js
createDirIfNotExists('test'); // creates the directory 'test', if it doesn't exist
```


[Acesse a Referência original](http://github.com/30-seconds/)
