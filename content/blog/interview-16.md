---
date: "2020-02-16"
title: '16: O que "use strict" faz?'
description: "#PerguntasDeEntrevistas 16"
tags: es6,javascript,interview,entrevistas
---

`"use strict"` é um recurso do ES5 no **JavaScript** que transforma nosso código no **Modo Estrito** em *funções* ou *scripts inteiros* . **O Modo Estrito** nos ajuda a evitar **erros** no início de nosso código e adiciona restrições a ele.

Restrições que o **Modo Estrito** nos fornece.

-   Atribuindo ou acessando uma variável que não é declarada.

```js
 function returnY(){
    "use strict"
    y = 123
    return y
 }
```

-   Atribuir um valor a uma variável global somente leitura ou não gravável

```js
   "use strict"
   var NaN = NaN
   var undefined = undefined
   var Infinity = "and beyond"
```

-   Excluindo uma propriedade não excluída.

```js
   "use strict"
   const obj = {}

   Object.defineProperty(obj, 'x', {
      value : '1'
   })

   delete obj.x
```

-   Nomes de parâmetros duplicados.

```js
   "use strict"

   function someFunc(a, b, b, c){

   }
```

-   Criando variáveis ​​com o uso da função **eval** .

```js
 "use strict"

 eval("var x = 1")

 console.log(x) //Throws a Reference Error x is not defined
```

-   O valor padrão **disso** será `undefined`.

```js
  "use strict"

  function showMeThis(){
    return this
  }

  showMeThis() //returns undefined
```

Existem muito mais restrições no **modo estrito** que essas.


Baseado no excelente artigo: [70 Interview Questions](https://dev.to/macmacky/70-javascript-interview-questions-5gfi)
