---
title: como usar o serializeCookie no javascript es6
date: "2020-01-04"
description: 'teste'
tags: utility,string,intermediate
---

Serialize a cookie name-value pair into a Set-Cookie header string.

Use template literals and `encodeURIComponent()` to create the appropriate string.

```js
const serializeCookie = (name, val) => `${encodeURIComponent(name)}=${encodeURIComponent(val)}`;
```

```js
serializeCookie('foo', 'bar'); // 'foo=bar'
```


[Acesse a Referência original](http://github.com/30-seconds/)
