---
title: como usar o JSONToFile no javascript es6
date: "2020-01-04"
description: 'teste'
tags: node,json,intermediate
---

Writes a JSON object to a file.

Use `fs.writeFile()`, template literals and `JSON.stringify()` to write a `json` object to a `.json` file.

```js
const fs = require('fs');
const JSONToFile = (obj, filename) =>
  fs.writeFile(`${filename}.json`, JSON.stringify(obj, null, 2));
```

```js
JSONToFile({ test: 'is passed' }, 'testJsonFile'); // writes the object to 'testJsonFile.json'
```


[Acesse a Referência original](http://github.com/30-seconds/)
