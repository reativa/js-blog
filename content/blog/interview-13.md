---
date: "2020-02-13"
title: '13: O que é javascript hoisting?'
description: "#PerguntasDeEntrevistas 13"
tags: es6,javascript,interview,entrevistas
---

**Hoisting** no Javascript é o termo usado para descrever a movimentação de *variáveis* e *funções* para o topo de seu escopo *(global ou função),* em relação ao local de onde a definimos.

Exemplo: 

```js
printName()
function printName() {
    console.log('Paulo Luan é bonitão pakarai')
}
```

Para entender **Hoist** , temos que entender o *contexto de execução*.

O **contexto de execução** é o "ambiente de código" atualmente em execução. O **contexto de execução** possui duas fases de *compilação* e *execução*.

**Compilação** - nesta fase esse maluco pega as `vars` e `functions` para cima, para que possamos referenciá-los mais tarde e receber os valores.

**Execução** - nesta fase, atribui valores às variáveis *içadas* anteriormente e *executa* ou *invoca* funções **(métodos em objetos)** .

**Nota:** só vale se for `function` ou `var` RAÍZ, os nutella do ES6 NÃO são HOIÇADOS (let, const, arrow function e o restante).

veja os exemplos:

```js
console.log(y)
var y = 1 // VAR BRABO DO RAÍZ DO RISCA FACA FUNCIONA
```

```js
console.log(y)
let y = 1 // NUTELLA NÃO FUNCIONA
```

```js
console.log(greet("Paulo Luan Bonitão"))
function greet(name){
  return 'Olá ' + name + '!'
}
```

```js
console.log(greet("Paulo Luan Bonitão"))
var greet = (name) => { // NUTTELA 
  return 'Olá ' + name + '!'
}
//console.log(greet("Paulo Luan Bonitão"))
```


Baseado no excelente artigo: [70 Interview Questions](https://dev.to/macmacky/70-javascript-interview-questions-5gfi#14-whats-the-difference-between-and-)