---
title: como usar o getImages no javascript es6
date: "2020-01-04"
description: 'teste'
tags: browser,beginner
---

Fetches all images from within an element and puts them into an array

Use `Element.prototype.getElementsByTagName()` to fetch all `<img>` elements inside the provided element, `Array.prototype.map()` to map every `src` attribute of their respective `<img>` element, then create a `Set` to eliminate duplicates and return the array.

```js
const getImages = (el, includeDuplicates = false) => {
  const images = [...el.getElementsByTagName('img')].map(img => img.getAttribute('src'));
  return includeDuplicates ? images : [...new Set(images)];
};
```

```js
getImages(document, true); // ['image1.jpg', 'image2.png', 'image1.png', '...']
getImages(document, false); // ['image1.jpg', 'image2.png', '...']
```


[Acesse a Referência original](http://github.com/30-seconds/)
