---
title: como usar o yesNo no javascript es6
date: "2020-01-04"
description: 'teste'
tags: utility,regexp,intermediate
---

Returns `true` if the string is `y`/`yes` or `false` if the string is `n`/`no`.

Use `RegExp.test()` to check if the string evaluates to `y/yes` or `n/no`.
Omit the second argument, `def` to set the default answer as `no`.

```js
const yesNo = (val, def = false) =>
  /^(y|yes)$/i.test(val) ? true : /^(n|no)$/i.test(val) ? false : def;
```

```js
yesNo('Y'); // true
yesNo('yes'); // true
yesNo('No'); // false
yesNo('Foo', true); // true
```


[Acesse a Referência original](http://github.com/30-seconds/)
