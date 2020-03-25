---
date: "2020-02-14"
title: '14: O que é escopo em Javascript?'
description: "#PerguntasDeEntrevistas 14"
tags: es6,javascript,interview,entrevistas
---

https://www.instagram.com/tv/B9w3lg6nzt4/

**Escopo** em JavaScript é a **área** em que temos acesso válido a variáveis ​​ou funções. 

JavaScript tem três tipos de escopos: **Escopo Global** , **Escopo da Função** e **Escopo do Bloco (ES6)**.

-   **Escopo Global** - variáveis ​​ou funções declaradas no espaço de nomes global estão no escopo global e, portanto, estão acessíveis em qualquer lugar em nosso código.

```js
//global namespace
var g = "global"

function globalFunc(){
    function innerFunc(){
        console.log(g) // G é global, então é acessível aqui
    }
    innerFunc()
}
```

-   **Escopo da Função** - variáveis, funções e parâmetros declarados em uma função são acessíveis dentro dessa função, mas não fora dela.

```js
function myFavoriteFunc(a) {
    if (true) {
        var b = "Hello " + a
    }
    return b
}
myFavoriteFunc("World")

console.log(a) // Throws a ReferenceError "a" is not defined
console.log(b) // does not continue here
```

-   **Escopo do bloco** - variáveis **( `let`, `const`)** declaradas em um bloco `{}`só podem ter acesso dentro dele.

```js
 function testBlock(){
   if(true) {
     let z = 5
   }
   console.log(z)
 }

 testBlock() // Throws a ReferenceError "z" is not defined

```

**Escopo** também é um conjunto de regras para encontrar variáveis. Se uma variável não existe no **escopo atual** ele sai olhando nos escopos acima no **escopo externo**, e se não existe mais uma vez, **olha para cima** novamente até atingir o **escopo global** se a variável existe ele usa, senão manda aquele errão brabo na tela e para de procurar. Isso é chamado de **cadeia de escopo**.

```js
   /* Scope Chain
   Inside inner function perspective

   inner's scope -> outer's scope -> global's scope
  */

  //Global Scope
  var variable1 = "Comrades"
  var variable2 = "Sayonara"

  function outer(){
  //outer's scope
    var variable1 = "World"
    function inner(){
    //inner's scope
      var variable2 = "Hello"
      console.log(variable2 + " " + variable1)
    }
    inner()
  }
  outer()
// logs Hello World
// because (variable2 = "Hello") and (variable1 = "World") are the nearest
// variables inside inner's scope.

```

[![Escopo](https://res.cloudinary.com/practicaldev/image/fetch/s--dJFL2g1k--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/l81b3nmdonimex0qsgyr.png)](https://res.cloudinary.com/practicaldev/image/fetch/s--dJFL2g1k--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/l81b3nmdonimex0qsgyr.png)


Baseado no excelente artigo: [70 Interview Questions](https://dev.to/macmacky/70-javascript-interview-questions-5gfi#14-whats-the-difference-between-and-)