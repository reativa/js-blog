---
title: como usar o isEmpty no javascript es6
date: "2020-01-04"
description: 'teste'
tags: type,array,object,string,beginner
---

Returns true if the a value is an empty object, collection, has no enumerable properties or is any type that is not considered a collection.

Check if the provided value is `null` or if its `length` is equal to `0`.

```js
const isEmpty = val => val == null || !(Object.keys(val) || val).length;
```

```js
isEmpty([]); // true
isEmpty({}); // true
isEmpty(''); // true
isEmpty([1, 2]); // false
isEmpty({ a: 1, b: 2 }); // false
isEmpty('text'); // false
isEmpty(123); // true - type is not considered a collection
isEmpty(true); // true - type is not considered a collection
```


[Acesse a Referência original](http://github.com/30-seconds/)