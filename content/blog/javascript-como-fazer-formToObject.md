---
title: como usar o formToObject no javascript es6
date: "2020-01-04"
description: ''
tags: browser,object,intermediate
---

Encode a set of form elements as an `object`.

Use the `FormData` constructor to convert the HTML `form` to `FormData`, `Array.from()` to convert to an array.
Collect the object from the array, using `Array.prototype.reduce()`.

```js
const formToObject = form =>
  Array.from(new FormData(form)).reduce(
    (acc, [key, value]) => ({
      ...acc,
      [key]: value
    }),
    {}
  );
```

```js
formToObject(document.querySelector('#form')); // { email: 'test@email.com', name: 'Test Name' }
```


[Acesse a Referência original](http://github.com/30-seconds/)
