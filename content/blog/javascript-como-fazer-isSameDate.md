---
title: como usar o isSameDate no javascript es6
date: "2020-01-04"
description: ''
tags: date,utility,beginner
---

Check if a date is the same as another date.

Use `Date.prototype.toISOString()` and strict equality checking (`===`) to check if the first date is the same as the second one.

```js
const isSameDate = (dateA, dateB) => dateA.toISOString() === dateB.toISOString();
```

```js
isSameDate(new Date(2010, 10, 20), new Date(2010, 10, 20)); // true
```


[Acesse a Referência original](http://github.com/30-seconds/)
