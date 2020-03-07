---
date: "2020-02-05"
title: '5: O que é o DOM?'
description: "#PerguntasDeEntrevistas 5"
tags: es6,javascript,interview,entrevistas
---

https://instagram.com/p/B9aZcBFHZ7W/

[O **DOM (Document Object Model)** é uma API](https://developer.mozilla.org/pt-BR/docs/DOM) para documentos HTML e XML . Ele fornece uma representação estrutural do documento, permitindo modificar o conteúdo e a apresentação visual usando uma linguagem de script como JavaScript.

Quando o navegador lê ( *analisa* ) nosso documento HTML pela primeira vez, ele cria um objetão de vários nós, uma estrutura de árvore que é modelada a partir do documento HTML que você escreveu, este é o **DOM**:

https://youtu.be/EE0Zcs0yBoQ?t=25

O DOM ele facilita e organiza a ordem dos elementos visuais na árvore, isso permite com que a gente modifique exatamente qualquer carinha que a gente quiser que esteja dentro dessa árvore.

Imagina que temos esse HTML simplão aqui:

```html
<!DOCTYPE html>
<html lang="en">

<head>
   <meta charset="UTF-8">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <meta http-equiv="X-UA-Compatible" content="ie=edge">
   <title>Document Object Model</title>
</head>

<body>
   <div>
      <p>
         <span></span>
      </p>
      <label></label>
      <input>
   </div>
</body>

</html>

```

O equivalente **DOM** seria essa bagaça aqui:

[![Equivalente DOM](../assets/dom.png)](../assets/dom.png)

No `Javascript` a gente tem acesso a essa árvore através do objeto `document`. Ele nos fornece muitos métodos que podemos selecionar e usar elementos para atualizar o seu conteúdo e algumas outras funcionalidades.


Baseado no excelente artigo: [70 Interview Questions](https://dev.to/macmacky/70-javascript-interview-questions-5gfi#14-whats-the-difference-between-and-)