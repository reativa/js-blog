---
title: como usar o arrayToHtmlList no javascript es6
date: "2020-01-04"
description: 'teste'
tags: browser,array,intermediate
---

Converts the given array elements into `<li>` tags and appends them to the list of the given id.

Use `Array.prototype.map()`, `document.querySelector()`, and an anonymous inner closure to create a list of html tags.

```js
const arrayToHtmlList = (arr, listID) =>
  (el => (
    (el = document.querySelector('#' + listID)),
    (el.innerHTML += arr.map(item => `<li>${item}</li>`).join(''))
  ))();
```

```js
arrayToHtmlList(['item 1', 'item 2'], 'myListID');
```


[Acesse a Referência original](http://github.com/30-seconds/)
