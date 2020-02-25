---
title: como usar o isAbsoluteURL no javascript es6
date: "2020-01-04"
description: ''
tags: string,utility,browser,url,intermediate
---

Returns `true` if the given string is an absolute URL, `false` otherwise.

Use a regular expression to test if the string is an absolute URL.

```js
const isAbsoluteURL = str => /^[a-z][a-z0-9+.-]*:/.test(str);
```

```js
isAbsoluteURL('https://google.com'); // true
isAbsoluteURL('ftp://www.myserver.net'); // true
isAbsoluteURL('/foo/bar'); // false
```


[Acesse a Referência original](http://github.com/30-seconds/)
