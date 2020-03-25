---
date: "2020-02-09"
title: '9: Qual a diferença entre == e ===?'
description: "#PerguntasDeEntrevistas 9"
tags: es6,javascript,interview,entrevistas
---

https://www.instagram.com/tv/B9j_oeXF244/

Caso queira executar os exemplos, use o [codepen.io](http://codepen.io)

A diferença entre `==` **(abstrata)** e `===` **(estrita)** é que 0 `==` compara por **valor** APÓS a *coerção* e `===` por **valor** e **tipo** sem *coerção*.

Vamos nos aprofundar no `==`. Mas, primeiro vamos falar sobre *coerção* .

Javascript não tem tipagem forte, então ele sempre vai tentar fazer a conversão das variáveis pra fazer determinadas operações, isso é chamado de *coerção* que é o processo de converter um valor para outro tipo.

tá ligado quando você usa o `if(algumObjeto)`? por baixo dos panos o javascript converte esse maluco pra boolean e consegue dizer se ele existe ou não. 

Voltando ao `==` ele faz essa *coerção implícita* que acabei de explicar, e para fazer isso ele segue um monte de regra maluca que depende de várias situações, que até o [Brendan Eich](https://en.wikipedia.org/wiki/Brendan_Eich) tem dúvidas sobre isso então não se preocupe se você não entender de primeira.

![](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d1/Brendan_Eich_Mozilla_Foundation_official_photo.jpg/220px-Brendan_Eich_Mozilla_Foundation_official_photo.jpg)

SHOW ME THE CODE:

```js
console.log('true == \'true\': ', true == 'true')  // aqui vai dar true
console.log('true == \'1\': ', true == '1')     // aqui vai dar true
console.log('true == true): ', true == true)    // aqui vai dar true
console.log('[===] true === \'true\': ', true === 'true') // aqui vai dar false
console.log('[===]true === \'1\': ', true === '1')    // aqui vai dar false
console.log('[===]true === true): ', true === true)   // aqui vai dar true
```

Suponha que tenhamos que comparar `x == y`.

1.  Se `x` e `y` tiver o mesmo tipo. Em seguida, ele os compara com o operador `===`.
2.  Se `x` é `null` e `y` é `undefined`então retorne `true`.
3.  Se `x` é `undefined` e `y` é `null` então retorne `true`.
4.  Se `x` é do tipo `number` e `y` é do tipo `string` retorne `x == toNumber(y)`.
5.  Se `x` é do tipo `string`e `y` é do tipo `number` retorne `toNumber(x) == y`.
6.  Se `x` for do tipo `boolean` retorne `toNumber(x) == y`.
7.  Se `y` for do tipo `boolean` retorne `x == toNumber(y)`.
8.  Se `x` é um dos tipos (`string`, `symbol` ou `number`) e `y`é o tipo `object` então retorne `x == toPrimitive(y)`.
9.  Se `x` for um `object` e `x` for um `string`, `symbol` Então retorne `toPrimitive(x) == y`.
10. Senão, retorne `false`.

**Nota:** `toPrimitive` usa primeiro o `valueOf` e depois o `toString` nos objetos para obter o valor primitivo desse objeto.

Vamos dar exemplos.

| `x` | `y` | `x == y` |
| --- | --- | --- |
| `5` | `5` | `true` |
| `1` | `'1'` | `true` |
| `null` | `undefined` | `true` |
| `0` | `false` | `true` |
| `'1,2'` | `[1,2]` | `true` |
| `'[object Object]'` | `{}` | `true` |

Todos esses exemplos retornam `true`.

O **primeiro exemplo** vai para a **condição um** porque `x`e `y` tem o mesmo tipo e valor.

O **segundo exemplo** vai para a **condição quatro** `y` é convertida em `number` antes de comparar.

O **terceiro exemplo** vai para a **condição dois**.

O **quarto exemplo** vai para a **condição sete** porque `y` é `boolean`.

O **quinto exemplo** vai para a **condição oito** . O array é convertido em `string` usando o `toString()`que retorna `1,2`.

O **último exemplo** vai para a **condição dez** . O objeto é convertido em um `string` usando o `toString()` que retorna `[object Object]`.

| `x` | `y` | `x === y` |
| --- | --- | --- |
| `5` | `5` | `true` |
| `1` | `'1'` | `false` |
| `null` | `undefined` | `false` |
| `0` | `false` | `false` |
| `'1,2'` | `[1,2]` | `false` |
| `'[object Object]'` | `{}` | `false` |

Se usarmos o operador `===`, todas as comparações, com exceção do primeiro exemplo, retornarão `false`, porque não têm o mesmo tipo, enquanto o primeiro exemplo retornará `true` porque os dois têm o mesmo tipo e valor.

Ainda não entendeu? Calma, nem quem fez o JS entende isso direito (brinks) mas aqui estão alguns artigos legais pra tentar ao menos entender o básico disto:

-   Sempre olhe a [documentação oficial](https://www.ecma-international.org/ecma-262/6.0/index.html#sec-type-conversion).

-   Excelente artigo no [Medium](https://medium.com/trainingcenter/explicando-a-coer%C3%A7%C3%A3o-de-tipos-em-javascript-d6c9203c4e5), falando a respeito.

-   Consulte a [tabela de igualdade](https://dorey.github.io/JavaScript-Equality-Table/) do JS

-   Exemplos de [bizarrices](https://wtfjs.com/) no Javascript.

-   Outros [exemplos de bizarrice](https://github.com/denysdovhan/wtfjs#-is-equal-).

-   Artigo interessante do [Hackernoon](https://hackernoon.com/understanding-js-coercion-ff5684475bfc).

Baseado no excelente artigo: [70 Interview Questions](https://dev.to/macmacky/70-javascript-interview-questions-5gfi#14-whats-the-difference-between-and-)