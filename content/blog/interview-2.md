---
date: "2020-01-08"
title: '2: O que o operador AND && faz?'
description: "#PerguntasDeEntrevistas 2"
tags: es6,javascript,interview,entrevistas
---

### 2: O que o `&&` operador faz?

O operador `&&` ou **Logical AND** encontra a primeira expressão *falsa* em seus operandos e a retorna e, se não encontrar nenhuma expressão *falsa*, retorna a última expressão. 

```js
   console.log(false && 1 && []) //logs false
   console.log(" " && true && 5) //logs 5
```


Outra forma de usar é a `verificação de curto-circuito`, para evitar trabalho desnecessário, ele automaticamente `NÃO` executa as próximas instruções caso o resultado da primeira seja falso. Exemplo:

Repare no `catch`, ele fecha a conexão do banco:

Usando **if**:

```js
  const router: Router = Router()

  router.get('/endpoint', (req: Request, res: Response) => {
     let conMobile: PoolConnection
     try {
        //do some db operations
     } catch (e) {
     if (conMobile) {
      conMobile.release()
     }
  }
})

```

Usando o operador **&&** (mais elegante):

```js
const router: Router = Router()

router.get('/endpoint', (req: Request, res: Response) => {
  let conMobile: PoolConnection
  try {
     //do some db operations
  } catch (e) {
    conMobile && conMobile.release()
  }
})

```

Baseado no excelente artigo: [70 Interview Questions](https://dev.to/macmacky/70-javascript-interview-questions-5gfi#14-whats-the-difference-between-and-)