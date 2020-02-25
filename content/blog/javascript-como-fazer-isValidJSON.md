---
title: como usar o isValidJSON no javascript es6
date: "2020-01-04"
description: ''
tags: type,json,intermediate
---

Checks if the provided string is a valid JSON.

Use `JSON.parse()` and a `try... catch` block to check if the provided string is a valid JSON.

```js
const isValidJSON = str => {
  try {
    JSON.parse(str);
    return true;
  } catch (e) {
    return false;
  }
};
```

```js
isValidJSON('{"name":"Adam","age":20}'); // true
isValidJSON('{"name":"Adam",age:"20"}'); // false
isValidJSON(null); // true
```


[Acesse a Referência original](http://github.com/30-seconds/)
