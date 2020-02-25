---
title: como usar o hasClass no javascript es6
date: "2020-01-04"
description: ''
tags: browser,css,beginner
---

Returns `true` if the element has the specified class, `false` otherwise.

Use `element.classList.contains()` to check if the element has the specified class.

```js
const hasClass = (el, className) => el.classList.contains(className);
```

```js
hasClass(document.querySelector('p.special'), 'special'); // true
```


[Acesse a Referência original](http://github.com/30-seconds/)
