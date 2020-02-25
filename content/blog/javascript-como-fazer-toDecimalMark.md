---
title: como usar o toDecimalMark no javascript es6
date: "2020-01-04"
description: ''
tags: utility,math,beginner
---

Use `toLocaleString()` to convert a float-point arithmetic to the [Decimal mark](https://en.wikipedia.org/wiki/Decimal_mark) form. It makes a comma separated string from a number.

```js
const toDecimalMark = num => num.toLocaleString('en-US');
```

```js
toDecimalMark(12305030388.9087); // "12,305,030,388.909"
```


[Acesse a Referência original](http://github.com/30-seconds/)
