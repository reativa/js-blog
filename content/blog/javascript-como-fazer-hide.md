---
title: como usar o hide no javascript es6
date: "2020-01-04"
description: 'teste'
tags: browser,css,beginner
---

Hides all the elements specified.

Use `NodeList.prototype.forEach()` to apply `display: none` to each element specified.

```js
const hide = (...el) => [...el].forEach(e => (e.style.display = 'none'));
```

```js
hide(document.querySelectorAll('img')); // Hides all <img> elements on the page
```


[Acesse a Referência original](http://github.com/30-seconds/)
