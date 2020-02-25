---
title: como usar o uniqueElementsByRight no javascript es6
date: "2020-01-04"
description: 'teste'
tags: array,function,intermediate
---

Returns all unique values of an array, based on a provided comparator function, starting from the right.

Use `Array.prototype.reduceRight()` and `Array.prototype.some()` for an array containing only the last unique occurrence of each value, based on the comparator function, `fn`.
The comparator function takes two arguments: the values of the two elements being compared.

```js
const uniqueElementsByRight = (arr, fn) =>
  arr.reduceRight((acc, v) => {
    if (!acc.some(x => fn(v, x))) acc.push(v);
    return acc;
  }, []);
```

```js
uniqueElementsByRight(
  [
    { id: 0, value: 'a' },
    { id: 1, value: 'b' },
    { id: 2, value: 'c' },
    { id: 1, value: 'd' },
    { id: 0, value: 'e' }
  ],
  (a, b) => a.id == b.id
); // [ { id: 0, value: 'e' }, { id: 1, value: 'd' }, { id: 2, value: 'c' } ]
```


[Acesse a Referência original](http://github.com/30-seconds/)
