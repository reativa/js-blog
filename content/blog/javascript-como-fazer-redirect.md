---
title: como usar o redirect no javascript es6
date: "2020-01-04"
description: 'teste'
tags: browser,url,beginner
---

Redirects to a specified URL.

Use `window.location.href` or `window.location.replace()` to redirect to `url`.
Pass a second argument to simulate a link click (`true` - default) or an HTTP redirect (`false`).

```js
const redirect = (url, asLink = true) =>
  asLink ? (window.location.href = url) : window.location.replace(url);
```

```js
redirect('https://google.com');
```


[Acesse a Referência original](http://github.com/30-seconds/)
