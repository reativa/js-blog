---
title: como usar o nodeListToArray no javascript es6
date: "2020-01-04"
description: 'teste'
tags: browser,array,beginner
---

Converts a `NodeList` to an array.

Use spread operator inside new array to convert a `NodeList` to an array.

```js
const nodeListToArray = nodeList => [...nodeList];
```

```js
nodeListToArray(document.childNodes); // [ <!DOCTYPE html>, html ]
```


[Acesse a Referência original](http://github.com/30-seconds/)
