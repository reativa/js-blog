---
title: como usar o isTravisCI no javascript es6
date: "2020-01-04"
description: ''
tags: node,intermediate
---

Checks if the current environment is [Travis CI](https://travis-ci.org/).

Checks if the current environment has the `TRAVIS` and `CI` environment variables ([reference](https://docs.travis-ci.com/user/environment-variables/#Default-Environment-Variables)).

```js
const isTravisCI = () => 'TRAVIS' in process.env && 'CI' in process.env;
```

```js
isTravisCI(); // true (if code is running on Travis CI)
```


[Acesse a Referência original](http://github.com/30-seconds/)
