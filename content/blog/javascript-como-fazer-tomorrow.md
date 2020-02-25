---
title: como usar o tomorrow no javascript es6
date: "2020-01-04"
description: ''
tags: date,intermediate
---

Results in a string representation of tomorrow's date.

Use `new Date()` to get the current date, increment by one using `Date.getDate()` and set the value to the result using `Date.setDate()`. 
Use `Date.prototype.toISOString()` to return a string in `yyyy-mm-dd` format.

```js
const tomorrow = () => {
  let t = new Date();
  t.setDate(t.getDate() + 1);
  return t.toISOString().split('T')[0];
};
```

```js
tomorrow(); // 2018-10-19 (if current date is 2018-10-18)
```


[Acesse a Referência original](http://github.com/30-seconds/)
