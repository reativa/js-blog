---
title: como usar o UUIDGeneratorBrowser no javascript es6
date: "2020-01-04"
description: 'teste'
tags: browser,utility,random,intermediate
---

Generates a UUID in a browser.

Use `crypto` API to generate a UUID, compliant with [RFC4122](https://www.ietf.org/rfc/rfc4122.txt) version 4.

```js
const UUIDGeneratorBrowser = () =>
  ([1e7] + -1e3 + -4e3 + -8e3 + -1e11).replace(/[018]/g, c =>
    (c ^ (crypto.getRandomValues(new Uint8Array(1))[0] & (15 >> (c / 4)))).toString(16)
  );
```

```js
UUIDGeneratorBrowser(); // '7982fcfe-5721-4632-bede-6000885be57d'
```


[Acesse a Referência original](http://github.com/30-seconds/)
