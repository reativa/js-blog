---
title: como usar o truthCheckCollection no javascript es6
date: "2020-01-04"
description: 'teste'
tags: object,logic,array,intermediate
---

Checks if the predicate (second argument) is truthy on all elements of a collection (first argument).

Use `Array.prototype.every()` to check if each passed object has the specified property and if it returns a truthy value.

```js
const truthCheckCollection = (collection, pre) => collection.every(obj => obj[pre]);
```

```js
truthCheckCollection([{ user: 'Tinky-Winky', sex: 'male' }, { user: 'Dipsy', sex: 'male' }], 'sex'); // true
```


[Acesse a Referência original](http://github.com/30-seconds/)
