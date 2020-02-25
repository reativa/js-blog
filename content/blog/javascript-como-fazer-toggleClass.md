---
title: como usar o toggleClass no javascript es6
date: "2020-01-04"
description: ''
tags: browser,beginner
---

Toggle a class for an element.

Use `element.classList.toggle()` to toggle the specified class for the element.

```js
const toggleClass = (el, className) => el.classList.toggle(className);
```

```js
toggleClass(document.querySelector('p.special'), 'special'); // The paragraph will not have the 'special' class anymore
```


[Acesse a Referência original](http://github.com/30-seconds/)
