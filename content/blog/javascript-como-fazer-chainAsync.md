---
title: como usar o chainAsync no javascript es6
date: "2020-01-04"
description: 'teste'
tags: function,intermediate
---

Chains asynchronous functions.

Loop through an array of functions containing asynchronous events, calling `next` when each asynchronous event has completed.

```js
const chainAsync = fns => {
  let curr = 0;
  const last = fns[fns.length - 1];
  const next = () => {
    const fn = fns[curr++];
    fn === last ? fn() : fn(next);
  };
  next();
};
```

```js
chainAsync([
  next => {
    console.log('0 seconds');
    setTimeout(next, 1000);
  },
  next => {
    console.log('1 second');
    setTimeout(next, 1000);
  },
  () => {
    console.log('2 second');
  }
]);
```


[Acesse a Referência original](http://github.com/30-seconds/)
