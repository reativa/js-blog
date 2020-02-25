---
title: como usar o untildify no javascript es6
date: "2020-01-04"
description: 'teste'
tags: node,string,beginner
---

Converts a tilde path to an absolute path.

Use `String.prototype.replace()` with a regular expression and `OS.homedir()` to replace the `~` in the start of the path with the home directory.

```js
const untildify = str => str.replace(/^~($|\/|\\)/, `${require('os').homedir()}$1`);
```

```js
untildify('~/node'); // '/Users/aUser/node'
```


[Acesse a Referência original](http://github.com/30-seconds/)
