---
title: como usar o isWeekday no javascript es6
date: "2020-01-04"
description: ''
tags: date,beginner
---

Results in a boolean representation of a specific date.

Pass the specific date object firstly.
Use `Date.getDay()` to check weekday by using a modulo operator and then returning a boolean.

```js
const isWeekday = (t = new Date()) => {
  return t.getDay() % 6 !== 0;
};
```

```js
isWeekday(); // true (if current date is 2019-07-19)
```


[Acesse a Referência original](http://github.com/30-seconds/)
