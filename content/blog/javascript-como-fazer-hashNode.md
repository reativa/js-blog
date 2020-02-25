---
title: como usar o hashNode no javascript es6
date: "2020-01-04"
description: ''
tags: node,utility,promise,intermediate
---

Creates a hash for a value using the [SHA-256](https://en.wikipedia.org/wiki/SHA-2) algorithm. Returns a promise.

Use `crypto` API to create a hash for the given value, `setTimeout` to prevent blocking on a long operation, and a `Promise` to give it a familiar interface.

```js
const crypto = require('crypto');
const hashNode = val =>
  new Promise(resolve =>
    setTimeout(
      () =>
        resolve(
          crypto
            .createHash('sha256')
            .update(val)
            .digest('hex')
        ),
      0
    )
  );
```

```js
hashNode(JSON.stringify({ a: 'a', b: [1, 2, 3, 4], foo: { c: 'bar' } })).then(console.log); // '04aa106279f5977f59f9067fa9712afc4aedc6f5862a8defc34552d8c7206393'
```


[Acesse a Referência original](http://github.com/30-seconds/)
