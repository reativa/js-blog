---
title: como usar o getStyle no javascript es6
date: "2020-01-04"
description: 'teste'
tags: browser,css,beginner
---

Returns the value of a CSS rule for the specified element.

Use `Window.getComputedStyle()` to get the value of the CSS rule for the specified element.

```js
const getStyle = (el, ruleName) => getComputedStyle(el)[ruleName];
```

```js
getStyle(document.querySelector('p'), 'font-size'); // '16px'
```


[Acesse a Referência original](http://github.com/30-seconds/)
