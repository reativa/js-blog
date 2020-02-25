---
title: como usar o getDaysDiffBetweenDates no javascript es6
date: "2020-01-04"
description: 'teste'
tags: date,intermediate
---

Returns the difference (in days) between two dates.

Calculate the difference (in days) between two `Date` objects.

```js
const getDaysDiffBetweenDates = (dateInitial, dateFinal) =>
  (dateFinal - dateInitial) / (1000 * 3600 * 24);
```

```js
getDaysDiffBetweenDates(new Date('2017-12-13'), new Date('2017-12-22')); // 9
```


[Acesse a Referência original](http://github.com/30-seconds/)
