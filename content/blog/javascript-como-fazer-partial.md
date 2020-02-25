---
title: como usar o partial no javascript es6
date: "2020-01-04"
description: 'teste'
tags: function,intermediate
---

Creates a function that invokes `fn` with `partials` prepended to the arguments it receives.

Use the spread operator (`...`) to prepend `partials` to the list of arguments of `fn`.

```js
const partial = (fn, ...partials) => (...args) => fn(...partials, ...args);
```

```js
const greet = (greeting, name) => greeting + ' ' + name + '!';
const greetHello = partial(greet, 'Hello');
greetHello('John'); // 'Hello John!'
```


[Acesse a Referência original](http://github.com/30-seconds/)
