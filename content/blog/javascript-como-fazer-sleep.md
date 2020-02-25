---
title: como usar o sleep no javascript es6
date: "2020-01-04"
description: ''
tags: function,promise,intermediate
---

Delays the execution of an asynchronous function.

Delay executing part of an `async` function, by putting it to sleep, returning a `Promise`.

```js
const sleep = ms => new Promise(resolve => setTimeout(resolve, ms));
```

```js
async function sleepyWork() {
  console.log("I'm going to sleep for 1 second.");
  await sleep(1000);
  console.log('I woke up after 1 second.');
}
```


[Acesse a Referência original](http://github.com/30-seconds/)
