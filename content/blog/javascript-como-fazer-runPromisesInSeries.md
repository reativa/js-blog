---
title: como usar o runPromisesInSeries no javascript es6
date: "2020-01-04"
description: 'teste'
tags: function,promise,intermediate
---

Runs an array of promises in series.

Use `Array.prototype.reduce()` to create a promise chain, where each promise returns the next promise when resolved.

```js
const runPromisesInSeries = ps => ps.reduce((p, next) => p.then(next), Promise.resolve());
```

```js
const delay = d => new Promise(r => setTimeout(r, d));
runPromisesInSeries([() => delay(1000), () => delay(2000)]); // Executes each promise sequentially, taking a total of 3 seconds to complete
```


[Acesse a Referência original](http://github.com/30-seconds/)
