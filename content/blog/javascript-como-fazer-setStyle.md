---
title: como usar o setStyle no javascript es6
date: "2020-01-04"
description: 'teste'
tags: browser,beginner
---

Sets the value of a CSS rule for the specified element.

Use `element.style` to set the value of the CSS rule for the specified element to `val`.

```js
const setStyle = (el, ruleName, val) => (el.style[ruleName] = val);
```

```js
setStyle(document.querySelector('p'), 'font-size', '20px'); // The first <p> element on the page will have a font-size of 20px
```


[Acesse a Referência original](http://github.com/30-seconds/)
