---
title: como usar o longestItem no javascript es6
date: "2020-01-04"
description: ''
tags: array,string,utility,intermediate
---

Takes any number of iterable objects or objects with a `length` property and returns the longest one.
If multiple objects have the same length, the first one will be returned.
Returns `undefined` if no arguments are provided.

Use `Array.prototype.reduce()`, comparing the `length` of objects to find the longest one.

```js
const longestItem = (...vals) => vals.reduce((a, x) => (x.length > a.length ? x : a));
```

```js
longestItem('this', 'is', 'a', 'testcase'); // 'testcase'
longestItem(...['a', 'ab', 'abc']); // 'abc'
longestItem(...['a', 'ab', 'abc'], 'abcd'); // 'abcd'
longestItem([1, 2, 3], [1, 2], [1, 2, 3, 4, 5]); // [1, 2, 3, 4, 5]
longestItem([1, 2, 3], 'foobar'); // 'foobar'
```


[Acesse a Referência original](http://github.com/30-seconds/)
