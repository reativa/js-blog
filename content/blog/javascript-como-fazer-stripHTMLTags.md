---
title: como usar o stripHTMLTags no javascript es6
date: "2020-01-04"
description: ''
tags: string,utility,regexp,beginner
---

Removes HTML/XML tags from string.

Use a regular expression to remove HTML/XML tags from a string.

```js
const stripHTMLTags = str => str.replace(/<[^>]*>/g, '');
```

```js
stripHTMLTags('<p><em>lorem</em> <strong>ipsum</strong></p>'); // 'lorem ipsum'
```


[Acesse a Referência original](http://github.com/30-seconds/)
