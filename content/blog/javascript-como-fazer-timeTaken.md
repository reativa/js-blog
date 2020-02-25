---
title: como usar o timeTaken no javascript es6
date: "2020-01-04"
description: ''
tags: utility,beginner
---

Measures the time taken by a function to execute.

Use `console.time()` and `console.timeEnd()` to measure the difference between the start and end times to determine how long the callback took to execute.

```js
const timeTaken = callback => {
  console.time('timeTaken');
  const r = callback();
  console.timeEnd('timeTaken');
  return r;
};
```

```js
timeTaken(() => Math.pow(2, 10)); // 1024, (logged): timeTaken: 0.02099609375ms
```


[Acesse a Referência original](http://github.com/30-seconds/)
