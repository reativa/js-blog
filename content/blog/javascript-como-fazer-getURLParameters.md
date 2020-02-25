---
title: como usar o getURLParameters no javascript es6
date: "2020-01-04"
description: ''
tags: utility,browser,string,url,intermediate
---

Returns an object containing the parameters of the current URL.

Use `String.match()` with an appropriate regular expression to get all key-value pairs, `Array.prototype.reduce()` to map and combine them into a single object.
Pass `location.search` as the argument to apply to the current `url`.

```js
const getURLParameters = url =>
  (url.match(/([^?=&]+)(=([^&]*))/g) || []).reduce(
    (a, v) => ((a[v.slice(0, v.indexOf('='))] = v.slice(v.indexOf('=') + 1)), a),
    {}
  );
```

```js
getURLParameters('http://url.com/page?name=Adam&surname=Smith'); // {name: 'Adam', surname: 'Smith'}
getURLParameters('google.com'); // {}
```


[Acesse a Referência original](http://github.com/30-seconds/)
