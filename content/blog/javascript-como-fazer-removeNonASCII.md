---
title: como usar o removeNonASCII no javascript es6
date: "2020-01-04"
description: ''
tags: string,regexp,intermediate
---

Removes non-printable ASCII characters.

Use a regular expression to remove non-printable ASCII characters.

```js
const removeNonASCII = str => str.replace(/[^\x20-\x7E]/g, '');
```

```js
removeNonASCII('äÄçÇéÉêlorem-ipsumöÖÐþúÚ'); // 'lorem-ipsum'
```


[Acesse a Referência original](http://github.com/30-seconds/)
