---
title: como usar o bottomVisible no javascript es6
date: "2020-01-04"
description: ''
tags: browser,intermediate
---

Returns `true` if the bottom of the page is visible, `false` otherwise.

Use `scrollY`, `scrollHeight` and `clientHeight` to determine if the bottom of the page is visible.

```js
const bottomVisible = () =>
  document.documentElement.clientHeight + window.scrollY >=
  (document.documentElement.scrollHeight || document.documentElement.clientHeight);
```

```js
bottomVisible(); // true
```


[Acesse a Referência original](http://github.com/30-seconds/)
