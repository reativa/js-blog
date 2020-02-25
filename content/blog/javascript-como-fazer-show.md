---
title: como usar o show no javascript es6
date: "2020-01-04"
description: ''
tags: browser,css,beginner
---

Shows all the elements specified.

Use the spread operator (`...`) and `Array.prototype.forEach()` to clear the `display` property for each element specified.

```js
const show = (...el) => [...el].forEach(e => (e.style.display = ''));
```

```js
show(...document.querySelectorAll('img')); // Shows all <img> elements on the page
```


[Acesse a Referência original](http://github.com/30-seconds/)
