---
title: como usar o getColonTimeFromDate no javascript es6
date: "2020-01-04"
description: 'teste'
tags: date,intermediate
---

Returns a string of the form `HH:MM:SS` from a `Date` object.

Use `Date.prototype.toTimeString()` and `String.prototype.slice()` to get the `HH:MM:SS` part of a given `Date` object.

```js
const getColonTimeFromDate = date => date.toTimeString().slice(0, 8);
```

```js
getColonTimeFromDate(new Date()); // "08:38:00"
```


[Acesse a Referência original](http://github.com/30-seconds/)
