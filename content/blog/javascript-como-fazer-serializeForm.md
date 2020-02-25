---
title: como usar o serializeForm no javascript es6
date: "2020-01-04"
description: 'teste'
tags: browser,string,intermediate
---

Encode a set of form elements as a query string.

Use the `FormData` constructor to convert the HTML `form` to `FormData`, `Array.from()` to convert to an array, passing a map function as the second argument.
Use `Array.prototype.map()` and `window.encodeURIComponent()` to encode each field's value.
Use `Array.prototype.join()` with appropriate argumens to produce an appropriate query string.

```js
const serializeForm = form =>
  Array.from(new FormData(form), field => field.map(encodeURIComponent).join('=')).join('&');
```

```js
serializeForm(document.querySelector('#form')); // email=test%40email.com&name=Test%20Name
```


[Acesse a Referência original](http://github.com/30-seconds/)
