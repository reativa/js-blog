---
title: como usar o takeRightWhile no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,function,intermediate
---

Removes elements from the end of an array until the passed function returns `true`. Returns the removed elements.

Loop through the array, using a `Array.prototype.reduceRight()` and accumulating elements while the function returns falsy value.

```js
const takeRightWhile = (arr, func) =>
  arr.reduceRight((acc, el) => (func(el) ? acc : [el, ...acc]), []);
```

```js
takeRightWhile([1, 2, 3, 4], n => n < 3); // [3, 4]
```


[Acesse a Referência original](http://github.com/30-seconds/)
