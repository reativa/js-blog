---
title: como usar o createElement no javascript es6
date: "2020-01-04"
description: ''
tags: browser,utility,beginner
---

Creates an element from a string (without appending it to the document). 
If the given string contains multiple elements, only the first one will be returned.

Use `document.createElement()` to create a new element.
Set its `innerHTML` to the string supplied as the argument. 
Use `ParentNode.firstElementChild` to return the element version of the string.

```js
const createElement = str => {
  const el = document.createElement('div');
  el.innerHTML = str;
  return el.firstElementChild;
};
```

```js
const el = createElement(
  `<div class="container">
    <p>Hello!</p>
  </div>`
);
console.log(el.className); // 'container'
```


[Acesse a Referência original](http://github.com/30-seconds/)
