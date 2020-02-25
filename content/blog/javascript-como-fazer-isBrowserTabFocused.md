---
title: como usar o isBrowserTabFocused no javascript es6
date: "2020-01-04"
description: ''
tags: browser,beginner
---

Returns `true` if the browser tab of the page is focused, `false` otherwise.

Use the `Document.hidden` property, introduced by the Page Visibility API to check if the browser tab of the page is visible or hidden.

```js
const isBrowserTabFocused = () => !document.hidden;
```

```js
isBrowserTabFocused(); // true
```


[Acesse a Referência original](http://github.com/30-seconds/)
