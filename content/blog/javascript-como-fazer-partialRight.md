---
title: como usar o partialRight no javascript es6
date: "2020-01-04"
description: 'teste'
tags: function,intermediate
---

Creates a function that invokes `fn` with `partials` appended to the arguments it receives.

Use the spread operator (`...`) to append `partials` to the list of arguments of `fn`.

```js
const partialRight = (fn, ...partials) => (...args) => fn(...args, ...partials);
```

```js
const greet = (greeting, name) => greeting + ' ' + name + '!';
const greetJohn = partialRight(greet, 'John');
greetJohn('Hello'); // 'Hello John!'
```


[Acesse a Referência original](http://github.com/30-seconds/)
