---
title: como usar o off no javascript es6
date: "2020-01-04"
description: 'teste'
tags: browser,event,intermediate
---

Removes an event listener from an element.

Use `EventTarget.removeEventListener()` to remove an event listener from an element. 
Omit the fourth argument `opts` to use `false` or specify it based on the options used when the event listener was added.

```js
const off = (el, evt, fn, opts = false) => el.removeEventListener(evt, fn, opts);
```

```js
const fn = () => console.log('!');
document.body.addEventListener('click', fn);
off(document.body, 'click', fn); // no longer logs '!' upon clicking on the page
```


[Acesse a Referência original](http://github.com/30-seconds/)
