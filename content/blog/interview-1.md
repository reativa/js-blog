---
date: "2020-02-01"
title: '1: Qual é a diferença entre undefined e null?'
description: "#PerguntasDeEntrevistas 1"
tags: es6,javascript,interview,entrevistas
---

### 1. Qual é a diferença entre `undefined` e `null`?

> **undefined**: valor primitivo utilizado quando uma variável não teve valor atribuído

> **null**: valor primitivo que representa a ausência intencional de um valor de objeto

Antes de entender as diferenças entre `undefined` e `null` devemos entender as semelhanças entre eles.

- Eles pertencem aos 7 tipos primitivos **do JavaScript** .

```js
 let primitiveTypes = [
    'string',
    'number',
    'null',
    'undefined',
    'boolean',
    'symbol', 
    'bigint'
]
```

-   Eles são valores **falsos**. Valores avaliados como `falso` ao convertê-lo em booleano, usando: `Boolean(value)` ou `!!value`.

```js
   console.log('!!null: ',!!null) //logs false
   console.log('!!undefined: ',!!undefined) //logs false

   console.log('Boolean(null): ',Boolean(null)) //logs false
   console.log('Boolean(undefined): ',Boolean(undefined)) //logs false

```

Ok, vamos falar sobre as diferenças:

- `undefined` é o valor padrão de uma variável que não recebeu um valor específico. Ou uma função que não tem valor de retorno **explícito** ex. `console.log(1)`. Ou uma propriedade que não existe em um objeto. Exemplo:

```js
  let _thisIsUndefined
  console.log('_thisIsUndefined', _thisIsUndefined) //logs undefined

  const doNothing = () => {}
  console.log(doNothing()) //logs undefined

  const someObj = {
    a : "ay",
    b : "bee",
    c : "si"
  }
  console.log(someObj["d"]) //logs undefined
```

- `null` é **"um valor que não representa nada"**, mas que teve uma atribuição! `null` é um valor que foi definido **explicitamente** para uma variável. 
  
Neste exemplo, obtemos um valor de `null` quando o método `fs.readFile` não gera um erro (por baixo dos panos, alguém atribuiu o valor null a variável).

```js
  fs.readFile('path/to/file', (e,data) => {
     console.log(e) //it logs null when no error occurred
     if(e){
       console.log(e)
     }
     console.log(data)
   })
```

Ao compararmos `null` e `undefined` obtermos `true` ao usar `==` (estranho né?) 

e obtemos `false` ao usar `===`. Vou explicar a diferença em breve.

```js
   console.log(null == undefined) // logs true
   console.log(null === undefined) // logs false
```

Baseado no excelente artigo: [70 Interview Questions](https://dev.to/macmacky/70-javascript-interview-questions-5gfi#14-whats-the-difference-between-and-)