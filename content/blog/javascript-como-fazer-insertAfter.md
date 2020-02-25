---
title: como usar o insertAfter no javascript es6
date: "2020-01-04"
description: ''
tags: browser,beginner
---

Inserts an HTML string after the end of the specified element.

Use `el.insertAdjacentHTML()` with a position of `'afterend'` to parse `htmlString` and insert it after the end of `el`.

```js
const insertAfter = (el, htmlString) => el.insertAdjacentHTML('afterend', htmlString);
```

```js
insertAfter(document.getElementById('myId'), '<p>after</p>'); // <div id="myId">...</div> <p>after</p>
```


[Acesse a Referência original](http://github.com/30-seconds/)
