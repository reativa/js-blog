---
title: como usar o escapeHTML no javascript es6
date: "2020-01-04"
description: ''
tags: string,browser,regexp,intermediate
---

Escapes a string for use in HTML.

Use `String.prototype.replace()` with a regexp that matches the characters that need to be escaped, using a callback function to replace each character instance with its associated escaped character using a dictionary (object).

```js
const escapeHTML = str =>
  str.replace(
    /[&<>'"]/g,
    tag =>
      ({
        '&': '&amp;',
        '<': '&lt;',
        '>': '&gt;',
        "'": '&#39;',
        '"': '&quot;'
      }[tag] || tag)
  );
```

```js
escapeHTML('<a href="#">Me & you</a>'); // '&lt;a href=&quot;#&quot;&gt;Me &amp; you&lt;/a&gt;'
```


[Acesse a Referência original](http://github.com/30-seconds/)
