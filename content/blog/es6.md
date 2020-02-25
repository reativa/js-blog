---
title: Javascript para impacientes
date: "2020-01-06"
description: 'Resumo de 5 minutos: Fique por dentro de todas as features do ES6'
tags: es6,javascript
---

![Js para impacientes](../assets/js.png)

## Introdução

### Motivação

Esse documento é um conjunto de "cheatsheet" para javascript que você frequentemente encontrará em projetos modernos e na maioria de exemplos de códigos atuais.

Esse guia não tem a intenção de te ensinar Javascript do zero, mas sim ajudar desenvolvedores com conhecimentos básicos a se familiarizarem com códigos modernos.

> **Nota:** Muito dos conceitos apresentados aqui vem de uma atualização do Javascript (ES2015, chamada também de ES6). Você pode achar as novas funcionalidades adicionadas nessa atualização [aqui](http://es6-features.org).

Créditos do texto Original: [Manuel Beaudru ⚡️](https://github.com/mbeaudru)

### Material Complementar

Se você estiver com dificuldades em entender alguma coisa, eu sugiro que você procure por respostas nos seguintes lugares:

- [MDN (Mozilla Developer Network)](https://developer.mozilla.org/fr/search?q=)
- [You don't know JS (livro)](https://github.com/getify/You-Dont-Know-JS)
- [ES6 Funcionalidades e exemplos](http://es6-features.org)
- [WesBos blog (ES6)](http://wesbos.com/category/es6/)
- [Reddit (JavaScript)](https://www.reddit.com/r/javascript/)
- [Google](https://www.google.com/) para encontrar blogs e recursos específicos

## Sumário

- Modern JavaScript cheatsheet
  * Introdução
    + Motivação
    + Material Complementar
  * Tabela de Conteúdos
  * Noções
    + Declaração de variáveis: var, const, let
      - Breve explicação
      - Exemplo
      - Explicação Detalhada
      - Material Complementar
    + Função de Seta
      - Exemplo
      - Explicação Detalhada
        * Concisão
        * Referência *this*
      - Material Útil
    + Parametros padrão de uma Function
      - Material Complementar
    + Desestruturação de objetos e arrays
      - Explicação com exemplo de código
      - Material Útil
    + Metodos de lista - map / filter / reduce
      - Exemplo
      - Explicação
        * Array.prototype.ma
        * Array.prototype.filte
        * Array.prototype.reduc
      - Material Complementar
    + Spread operator "..."
      - Exemplo
      - Explicação
        * Em interações
        * Function rest parameter
        * Object properties spreading
      - Material Complementar
    + Object property shorthand
      - Explicação
      - Material Complementar
    + Promises
      - Exemplo
      - Explicação
        * Criando uma promise
        * Usando uma promise
      - External Resources
    + Template literals
      - Sample code
      - External resources
    + Imports / Exports
      - Explanation with sample code
      - External resources
    + JavaScript *this*
      - External resources
    + Class
      - Samples
      - External resources
    + Async Await
      - Sample code
      - Explanation
      - External resources
  * Glossary
    + Scope
    + Variable mutation

## Noções

### Declaração de variáveis: var, const, let

Em JavaScript, existem três palavras-chave disponíveis para declarar uma variável, e cada uma tem suas diferenças. São elas ```var```, ```let``` e ```const```.

#### Breve explicação

Variáveis declaradas com a palavra-chave ```const``` não podem ser reatribuídas, enquanto ```let``` e ```var``` podem.

Eu recomendo sempre declarar suas variáveis com ```const``` por padrão, e com ```let``` se você precisar *modifica-lo* ou reatribuí-lo mais tarde.

<table>
  <tr>
    <th></th>
    <th>Escopo</th>
    <th>Reatribuível</th>
    <th>Mutável</th>
   <th><a href="#tdz_sample">Zona Temporal Inoperante</a></th>
  </tr>
  <tr>
    <th>const</th>
    <td>Bloco</td>
    <td>Não</td>
    <td><a href="#const_mutable_sample">Sim</a></td>
    <td>Sim</td>
  </tr>
  <tr>
    <th>let</th>
    <td>Bloco</td>
    <td>Sim</td>
    <td>Sim</td>
    <td>Sim</td>
  </tr>
   <tr>
    <th>var</th>
    <td>Função</td>
    <td>Sim</td>
    <td>Sim</td>
    <td>Não</td>
  </tr>
</table>

#### Exemplo

```javascript
const person = "Nick";
person = "John" // Irá ocorrer um erro, person não pode ser reatribuída
```

```javascript
let person = "Nick";
person = "John";
console.log(person) // "John", a reatribuição é permitida com let
```

#### Explicação Detalhada

O [*escopo*](#scope_def) de uma variável grosseiramente significa "onde esta variável está disponível no código".

##### var

Variáveis declaradas com ```var``` são *função escopada*, significando que quando uma variável é criada em uma função, tudo naquela função pode acessar essa variável. Além disso, uma variável de *função escopada* criada em uma função não pode ser acessada fora desta função.

Eu recomendo que você imagine isso, como se uma variável *X escopada* significasse que essa variável era uma propriedade de X.

```javascript
function myFunction() {
  var myVar = "Nick";
  console.log(myVar); // "Nick" - myVar é acessível dentro da função.
}
console.log(myVar); // Lança um ReferenceError, myVar não está acessível fora da função.
```

Ainda focado na variável de escopo, aqui está um exemplo mais sutil:

```javascript
function myFunction() {
  var myVar = "Nick";
  if (true) {
    var myVar = "John";
    console.log(myVar); // "John"
    // na verdade, sendo myVar do escopo da função, nós simplesmente apagamos o valor anterior do myVar "Nick" para "John"
  }
  console.log(myVar); // "John" - veja como as instruções no bloco if afetaram esse valor
}
console.log(myVar); // Lança um ReferenceError, myVar não é acessível fora da função.
```

Além disso, variáveis declaradas *var* são movidas para o topo do escopo na execução. É o que chamamos de [içando a var](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var#var_hoisting).

Esta parte do código:

```js
console.log(myVar) // undefined -- sem erro lançado
var myVar = 2;
```

é entendido na execução como:

```js
var myVar;
console.log(myVar) // undefined -- sem erro lançado
myVar = 2;
```

##### let

```var``` e ```let ``` são quase os mesmos, mas variáveis declaradas com ```let```

- são *escopado em bloco*
- **não** são acessíveis antes de serem atribuídas
- não podem ser re-declaradas no mesmo escopo

Vamos ver o impacto do escopo em bloco em nosso exemplo anterior:

```javascript
function myFunction() {
  let myVar = "Nick";
  if (true) {
    let myVar = "John";
    console.log(myVar); // "John"
    // na verdade, myVar sendo escopada em bloco, nós criamos uma nova variável myVar.
    // essa variável não é acessível fora do bloco e é totalmente independente
    // da primeira myVar criada !
  }
  console.log(myVar); // "Nick", veja como as instruções no bloco IF NÃO afetou este valor
}
console.log(myVar); // lançado um ReferenceError, myVar não é acessível fora da fucnção.
```

<a name="tdz_sample"></a> Agora, o que significa para as variáveis *let* (e *const*) não estarem acessíveis antes de serem atribuídas:

```js
console.log(myVar) // lança um ReferenceError !
let myVar = 2;
```

Em contraste com as variáveis *var*, se você tentar ler ou escrever em uma variável *let* ou *const* antes de serem atribuídos, um erro será gerado. Esse fenômeno é freqüentemente chamado [*Zona Temporal Inoperante*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let#Temporal_Dead_Zone_and_errors_with_let) ou *TDZ*.

> **Nota:** Tecnicamente, as declarações de *let* e *const* também estão sendo içadas, mas não a sua atribuição. Uma vez que elas são feitas para que elas não possam ser usados antes da atribuição, ela intuitivamente parece que não há içamento, mas existe. Saiba mais sobre isso [explicação muito detalhada aqui](http://jsrocks.org/2015/01/temporal-dead-zone-tdz-demystified) se quiser saber mais.

Além disso, você não pode re-declarar uma variável *let*:

```js
let myVar = 2;
let myVar = 3; // Retorna um SyntaxError
```

##### const

Variáveis declaradas ```const``` agem como variáveis *let*, mas elas não podem ser reatribuídas.

Para resumir, variáveis *const*:

- são *escopado em bloco*
- não são acessíveis antes de serem atribuídos
- não podem ser re-declaradas no mesmo escopo
- não podem ser reatribuídas

```js
const myVar = "Nick";
myVar = "John" // lança um erro, reatribuição não é permitido
```

```js
const myVar = "Nick";
const myVar = "John" // lança um erro, re-declaração não é permitida
```

<a name="const_mutable_sample"></a> Mas há uma sutileza : variáveis ```const``` não são [**imutáveis**](#mutation_def) ! Concretamente, Isto significa que variáveis *objetos* e *arrays* declaradas com ```const``` **podem** ser mutadas.

Para objetos:
```js
const person = {
  name: 'Nick'
};
person.name = 'John' // isto irá funcionar! A variável objeto person não é completamente reatribuída, mas mutada
console.log(person.name) // "John"
person = "Sandra" // lança um erro, porque a reatribuição não é permitida com variáveis declaradas com const
```

Para arrays:
```js
const person = [];
person.push('John'); // isto irá funcionar! A variável array person não é completamente reatribuída, mas mutada
console.log(person[0]) // "John"
person = ["Nick"] // lança um erro, porque a reatribuição não é permitida com variáveis declaradas com array
```

#### Material Complementar

- [Como let e const são escopados em JavaScript - WesBos](http://wesbos.com/javascript-scoping/)
- [Zona temporal Inoperante (TDZ) desmistificada](http://jsrocks.org/2015/01/temporal-dead-zone-tdz-demystified)

### <a name="função-de-seta"></a> Função de seta

A atualização do JavaScript ES6 introduziu *funções de seta*, que é outra maneira de declarar e usar funções. Aqui estão os benefícios que elas trazem:

- Mais conciso
- *this* é retirado dos arredores
- retorno implícito

#### Exemplo de código

- Concisão e retorno implícito

```js
function double(x) { return x * 2; } // Forma tradicional
console.log(double(2)) // 4
```

```js
const double = x => x * 2; // A mesma função escrita como uma função de seta com retorno implícito
console.log(double(2)) // 4
```

- Referência *this*

Em uma função de seta, *this* é igual ao valor *this* do contexto de execução envolvente. Basicamente, com as funções de seta, você não precisa fazer o truque "that/self = this" antes de chamar uma função dentro de uma função.

```js
function myFunc() {
  this.myVar = 0;
  setTimeout(() => {
    this.myVar++;
    console.log(this.myVar) // 1
  }, 0);
}
```

#### Explicação detalhada

##### Concisão

As funções de seta são mais concisas do que as funções tradicionais em diversas maneiras. Vamos rever todos os casos possíveis:

- Retorno implícito VS explícito

Um **retorno explícito** é uma função em que a palavra-chave *return* é usada em seu corpo.

```js
  function double(x) {
    return x * 2; // esta função retorna explicitamente x * 2, a palavra-chave *retorno*  é usada
  }
```

Na maneira tradicional de escrever funções, o retorno sempre foi explícito. Mas com funções de seta, você pode fazer *retorno implícito*, o que significa que você não precisa usar a palavra-chave *return* para retornar um valor.

```js
  const double = (x) => {
    return x * 2; // um retorno explícito aqui
  }
```

Uma vez que esta função apenas retorna algo (sem instruções antes da palavra-chave *return*), podemos fazer um retorno implícito.

```js
  const double = (x) => x * 2; // Correto, retorna x*2
```

Para fazer isso, só precisamos **remover os colchetes** e a palavra-chave **return**. É por isso que é chamado de *retorno implícito*, a palavra-chave *return* não existe, mas essa função retornará ```x * 2```.

> **Nota:** Se sua função não retornar um valor (com *efeitos colaterais*), ele não faz um retorno explícito nem implícito.

Além disso, se você quiser retornar implicitamente um *objeto*, você **deve ter parênteses em torno dele**, pois isso entrará em conflito com as chaves do bloco:

```js
const getPerson = () => ({ name: "Nick", age: 24 })
console.log(getPerson()) // { name: "Nick", age: 24 } -- objeto implicitamente retornado pela função de seta
```

- Só um argumento

Se a sua função apenas tiver um parâmetro, você pode omitir os parênteses à sua volta. Se pegarmos o código *double* acima:

```js
  const double = (x) => x * 2; // esta função de seta apenas leva um parâmetro
```

Parênteses ao redor do parâmetro podem ser evitados:

```js
  const double = x => x * 2; // esta função de seta tem apenas um parâmetro
```

- Nenhum argumento

Quando não há argumento fornecido para uma função de seta, você precisa fornecer parênteses, ou não será uma sintaxe válida.

```js
  () => { // parênteses são fornecidos, tudo está ok
    const x = 2;
    return x;
  }
```

```js
  => { // Sem parênteses, isso não funcionará!
    const x = 2;
    return x;
  }
```

##### Referência *this*

Para entender essa sutileza introduzida com funções de seta, você deve saber como [this](#this_def) se comporta em JavaScript.

Em funções de seta, *this* é igual ao valor *this* do contexto de execução envolvente. O que significa que uma função de seta não cria um novo *this*, Ela pega do seu entorno em vez disso.

Sem uma função de seta, se você quisesse acessar uma variável de *this* em uma função dentro de outra função, você tinha que usar *that = this* ou *self = this*.

Por exemplo, usando a função setTimeout dentro de myFunc:

```js
function myFunc() {
  this.myVar = 0;
  var that = this; // that = this (truque)
  setTimeout(
    function() { // Um novo *this* é criado neste escopo de função
      that.myVar++;
      console.log(that.myVar) // 1

      console.log(this.myVar) // undefined -- veja a declaração da função acima
    },
    0
  );
}
```

Mas com função de seta, *this* é retirado do seu entorno:

```js
function myFunc() {
  this.myVar = 0;
  setTimeout(
    () => { // this é retirado do entorno, o que significa de myFunc aqui
      this.myVar++;
      console.log(this.myVar) // 1
    },
    0
  );
}
```

#### Material Útil

- [Arrow functions introduction (Introdução à Funções de Seta) - WesBos](http://wesbos.com/arrow-functions/)
- [JavaScript arrow function - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
- [Arrow function and lexical *this*](https://hackernoon.com/javascript-es6-arrow-functions-and-lexical-this-f2a3e2a5e8c4)

### Parametros padrão de uma Function

A partir da atualização do JavaScript ES2015, você pode definir um valor padrão para os parâmetros da função usando a seguinte sintaxe:

```js
function myFunc(x = 10) {
  return x;
}
console.log(myFunc()) // 10 -- nenhum valor é fornecido então o valor padrão de x que é 10 será atribuído a x em myFunc
console.log(myFunc(5)) // 5 -- um valor é fornecido então x é igual a 5 em myFunc

console.log(myFunc(undefined)) // 10 -- um valor undefined é fornecido então o valor padrão é atribuído para x
console.log(myFunc(null)) // null -- um valor (null) é fornecido, veja abaixo para mais detalhes neste caso
```

O valor de parâmetro padrão é aplicado em duas e somente duas situações:

- Nenhum parâmetro fornecido
- *undefined* parâmetro fornecido

Em outras palavras, se você passar um *null* o parâmetro padrão **não irá ser aplicado**.

> **Nota:** Atribuição de valor padrão também pode ser usada com parâmetros desestruturados (veja o próximo conceito para ver um exemplo)

#### Material Complementar

- [Default parameter value - ES6 Features](http://es6-features.org/#DefaultParameterValues)
- [Default parameters - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters)

### Desestruturação de objetos e arrays

*Desestruturação* é uma maneira conveniente de criar novas variáveis extraindo alguns valores de dados armazenados em objetos ou arrays (matrizes).

Para nomear alguns casos de uso, *desestruturação* pode ser usado para desestruturar parâmetros de função ou *this.props* em projetos React, por exemplo.

#### Explicação com exemplo de código

- Objeto

Vamos considerar o seguinte objeto para todos os exemplos:

```js
const person = {
  firstName: "Nick",
  lastName: "Anderson",
  age: 35,
  sex: "M"
}
```

Sem desestruturação

```js
const first = person.firstName;
const age = person.age;
const city = person.city || "Paris";
```

Com desestruturação, tudo em uma única linha:

```js
const { firstName: first, age, city = "Paris" } = person; // É isso ! :)

console.log(age) // 35 -- uma nova variável age é criada e é igual a person.age
console.log(first) // "Nick" -- uma nova variável first é criada e é igual person.firstName
console.log(firstName) // ReferenceError -- person.firstName existe MAS a nova variável criada é nomeada primeiro
console.log(city) // "Paris" -- uma nova variável city é criada e uma vez que person.city é indefinida, city é igual ao valor padrão fornecido "Paris".
```

**Nota :** Em ```const { age } = person;```, os colchetes depois da palavra-chave *const* não são usados para declarar um objeto nem um bloco, mas é a sintaxe da *desestruturação*.

- Parâmetros de função

*Desestruturação* é freqüentemente usado para desestruturar parâmetros de objetos em funções.

Sem desestruturação

```js
function joinFirstLastName(person) {
  const firstName = person.firstName;
  const lastName = person.lastName;
  return firstName + '-' + lastName;
}

joinFirstLastName(person); // "Nick-Anderson"
```

Ao desestruturar o parâmetro de objeto *person*, obtemos uma função mais concisa:

```js
function joinFirstLastName({ firstName, lastName }) { // criamos variáveis firstName e lastName por desestruturação person parameter
  return firstName + '-' + lastName;
}

joinFirstLastName(person); // "Nick-Anderson"
```

A desestruturação é ainda mais agradável para usar com [funções de seta] (#função-de-seta):

```js
const joinFirstLastName = ({ firstName, lastName }) => firstName + '-' + lastName;

joinFirstLastName(person); // "Nick-Anderson"
```

- Array (Matriz)

Vamos considerar a seguinte array:

```js
const myArray = ["a", "b", "c"];
```

Sem desestruturação

```js
const x = myArray[0];
const y = myArray[1];
```

Com desestruturação

```js
const [x, y] = myArray; // É isso !

console.log(x) // "a"
console.log(y) // "b"
```

#### Material Útil

- [ES6 Features - Destructuring Assignment (Funcionalidades ES6 - Atribuição de Destruturação)](http://es6-features.org/#ArrayMatching)
- [Destructuring Objects - WesBos](http://wesbos.com/destructuring-objects/)
- [ExploringJS - Destructuring](http://exploringjs.com/es6/ch_destructuring.html)

### Array methods - map / filter / reduce / find

*Map*, *filter*, *reduce* and *find* are array methods that are coming from a programming paradigm named [*functional programming*](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-functional-programming-7f218c68b3a0).

To sum it up:

- **Array.prototype.map()** takes an array, does something on its elements and returns an array with the transformed elements.
- **Array.prototype.filter()** takes an array, decides element by element if it should keep it or not and returns an array with the kept elements only
- **Array.prototype.reduce()** takes an array and aggregates the elements into a single value (which is returned)
- **Array.prototype.find()** takes an array, and returns the first element that satisfies the provided condition.

I recommend to use them as much as possible in following the principles of functional programming because they are composable, concise and elegant.

With those four methods, you can avoid the use of *for* and *forEach* loops in most situations. When you are tempted to do a *for* loop, try to do it with *map*, *filter*, *reduce* and *find* composed. You might struggle to do it at first because it requires you to learn a new way of thinking, but once you've got it things get easier.

#### Sample code

```js
const numbers = [0, 1, 2, 3, 4, 5, 6];
const doubledNumbers = numbers.map(n => n * 2); // [0, 2, 4, 6, 8, 10, 12]
const evenNumbers = numbers.filter(n => n % 2 === 0); // [0, 2, 4, 6]
const sum = numbers.reduce((prev, next) => prev + next, 0); // 21
const greaterThanFour = numbers.find((n) => n>4); // 5
```

Compute total grade sum for students with grades 10 or above by composing map, filter and reduce:

```js
const students = [
  { name: "Nick", grade: 10 },
  { name: "John", grade: 15 },
  { name: "Julia", grade: 19 },
  { name: "Nathalie", grade: 9 },
];

const aboveTenSum = students
  .map(student => student.grade) // we map the students array to an array of their grades
  .filter(grade => grade >= 10) // we filter the grades array to keep those 10 or above
  .reduce((prev, next) => prev + next, 0); // we sum all the grades 10 or above one by one

console.log(aboveTenSum) // 44 -- 10 (Nick) + 15 (John) + 19 (Julia), Nathalie below 10 is ignored
```

#### Explanation

Let's consider the following array of numbers for our examples:

```js
const numbers = [0, 1, 2, 3, 4, 5, 6];
```

##### Array.prototype.map()

```js
const doubledNumbers = numbers.map(function(n) {
  return n * 2;
});
console.log(doubledNumbers); // [0, 2, 4, 6, 8, 10, 12]
```

What's happening here? We are using .map on the *numbers* array, the map is iterating on each element of the array and passes it to our function. The goal of the function is to produce and return a new value from the one passed so that map can replace it.

Let's extract this function to make it more clear, just for this once:

```js
const doubleN = function(n) { return n * 2; };
const doubledNumbers = numbers.map(doubleN);
console.log(doubledNumbers); // [0, 2, 4, 6, 8, 10, 12]
```

**Note** : You will frequently encounter this method used in combination with [arrow functions](#-arrow-function)

```js
const doubledNumbers = numbers.map(n => n * 2);
console.log(doubledNumbers); // [0, 2, 4, 6, 8, 10, 12]
```

```numbers.map(doubleN)``` produces ```[doubleN(0), doubleN(1), doubleN(2), doubleN(3), doubleN(4), doubleN(5), doubleN(6)]``` which is equal to ```[0, 2, 4, 6, 8, 10, 12]```.

> **Note:** If you do not need to return a new array and just want to do a loop that has side effects, you might just want to use a for / forEach loop instead of a map.

##### Array.prototype.filter()

```js
const evenNumbers = numbers.filter(function(n) {
  return n % 2 === 0; // true if "n" is par, false if "n" isn't
});
console.log(evenNumbers); // [0, 2, 4, 6]
```

**Note** : You will frequently encounter this method used in combination with [arrow functions](#-arrow-function)

```js
const evenNumbers = numbers.filter(n => n % 2 === 0);
console.log(evenNumbers); // [0, 2, 4, 6]
```

We are using .filter on the *numbers* array, filter is iterating on each element of the array and passes it to our function. The goal of the function is to return a boolean that will determine whether the current value will be kept or not. Filter then returns the array with only the kept values.

##### Array.prototype.reduce()

The reduce method goal is to *reduce* all elements of the array it iterates on into a single value. How it aggregates those elements is up to you.

```js
const sum = numbers.reduce(
  function(acc, n) {
    return acc + n;
  },
  0 // accumulator variable value at first iteration step
);

console.log(sum) // 21
```

**Note** : You will frequently encounter this method used in combination with [arrow functions](#-arrow-function)

```js
const sum = numbers.reduce((acc, n) => acc + n, 0);
console.log(sum) // 21
```

Just like for .map and .filter methods, .reduce is applied on an array and takes a function as the first parameter.

This time though, there are changes:

- .reduce takes two parameters

The first parameter is a function that will be called at each iteration step.

The second parameter is the value of the accumulator variable (*acc* here) at the first iteration step (read next point to understand).

- Function parameters

The function you pass as the first parameter of .reduce takes two parameters. The first one (*acc* here) is the accumulator variable, whereas the second parameter (*n*) is the current element.

The accumulator variable is equal to the return value of your function at the **previous** iteration step. At the first step of the iteration, *acc* is equal to the value you passed as .reduce second parameter.

###### At first iteration step

```acc = 0``` because we passed in 0 as the second parameter for reduce

```n = 0``` first element of the *number* array

Function returns *acc* + *n* --> 0 + 0 --> 0

###### At second iteration step

```acc = 0``` because it's the value the function returned at the previous iteration step

```n = 1``` second element of the *number* array

Function returns *acc* + *n* --> 0 + 1 --> 1

###### At third iteration step

```acc = 1``` because it's the value the function returned at the previous iteration step

```n = 2``` third element of the *number* array

Function returns *acc* + *n* --> 1 + 2 --> 3

###### At fourth iteration step

```acc = 3``` because it's the value the function returned at the previous iteration step

```n = 3``` fourth element of the *number* array

Function returns *acc* + *n* --> 3 + 3 --> 6

###### [...] At last iteration step

```acc = 15``` because it's the value the function returned at the previous iteration step

```n = 6``` last element of the *number* array

Function returns *acc* + *n* --> 15 + 6 --> 21

As it is the last iteration step, **.reduce** returns 21.

##### Array.prototype.find()

```js
const greaterThanZero = numbers.find(function(n) {
  return n > 0; // return number just greater than 0 is present
});
console.log(greaterThanZero); // 1
```

**Note** : You will frequently encounter this method used in combination with [arrow functions](#-arrow-function)

We are using .find on the *numbers* array, .find is iterating on each element of the array and passes it to our function, until the condition is met. The goal of the function is to return the element that satisfies the current testing function. The .find method executes the callback function once for each index of the array until the callback returns a truthy value.

**Note** : It immediately returns the value of that element (that satisfies the condition) if found. Otherwise, returns undefined.

#### External Resource

- [Understanding map / filter / reduce in JS](https://hackernoon.com/understanding-map-filter-and-reduce-in-javascript-5df1c7eee464)

### Spread operator "..."

The spread operator ```...``` has been introduced with ES2015 and is used to expand elements of an iterable (like an array) into places where multiple elements can fit.

#### Sample code

```js
const arr1 = ["a", "b", "c"];
const arr2 = [...arr1, "d", "e", "f"]; // ["a", "b", "c", "d", "e", "f"]
```

```js
function myFunc(x, y, ...params) {
  console.log(x);
  console.log(y);
  console.log(params)
}

myFunc("a", "b", "c", "d", "e", "f")
// "a"
// "b"
// ["c", "d", "e", "f"]
```

```js
const { x, y, ...z } = { x: 1, y: 2, a: 3, b: 4 };
console.log(x); // 1
console.log(y); // 2
console.log(z); // { a: 3, b: 4 }

const n = { x, y, ...z };
console.log(n); // { x: 1, y: 2, a: 3, b: 4 }
```

#### Explanation

##### In iterables (like arrays)

If we have the two following arrays:

```js
const arr1 = ["a", "b", "c"];
const arr2 = [arr1, "d", "e", "f"]; // [["a", "b", "c"], "d", "e", "f"]
```

*arr2* the first element is an array because *arr1* is injected as is into *arr2*. But what we want is *arr2* to be an array of letters. To do so, we can *spread* the elements of *arr1* into *arr2*.

With spread operator

```js
const arr1 = ["a", "b", "c"];
const arr2 = [...arr1, "d", "e", "f"]; // ["a", "b", "c", "d", "e", "f"]
```

##### Function rest parameter

In function parameters, we can use the rest operator to inject parameters into an array we can loop in. There is already an **arguments** object bound to every function that is equal to an array of all the parameters passed into the function.

```js
function myFunc() {
  for (var i = 0; i < arguments.length; i++) {
    console.log(arguments[i]);
  }
}

myFunc("Nick", "Anderson", 10, 12, 6);
// "Nick"
// "Anderson"
// 10
// 12
// 6
```

But let's say that we want this function to create a new student with its grades and with its average grade. Wouldn't it be more convenient to extract the first two parameters into two separate variables, and then have all the grades in an array we can iterate over?

That's exactly what the rest operator allows us to do!

```js
function createStudent(firstName, lastName, ...grades) {
  // firstName = "Nick"
  // lastName = "Anderson"
  // [10, 12, 6] -- "..." takes all other parameters passed and creates a "grades" array variable that contains them

  const avgGrade = grades.reduce((acc, curr) => acc + curr, 0) / grades.length; // computes average grade from grades

  return {
    firstName: firstName,
    lastName: lastName,
    grades: grades,
    avgGrade: avgGrade
  }
}

const student = createStudent("Nick", "Anderson", 10, 12, 6);
console.log(student);
// {
//   firstName: "Nick",
//   lastName: "Anderson",
//   grades: [10, 12, 6],
//   avgGrade: 9,33
// }
```

> **Note:** createStudent function is bad because we don't check if grades.length exists or is different from 0. But it's easier to read this way, so I didn't handle this case.

##### Object properties spreading

For this one, I recommend you read previous explanations about the rest operator on iterables and function parameters.

```js
const myObj = { x: 1, y: 2, a: 3, b: 4 };
const { x, y, ...z } = myObj; // object destructuring here
console.log(x); // 1
console.log(y); // 2
console.log(z); // { a: 3, b: 4 }

// z is the rest of the object destructured: myObj object minus x and y properties destructured

const n = { x, y, ...z };
console.log(n); // { x: 1, y: 2, a: 3, b: 4 }

// Here z object properties are spread into n
```

#### External resources

- [TC39 - Object rest/spread](https://github.com/tc39/proposal-object-rest-spread)
- [Spread operator introduction - WesBos](https://github.com/wesbos/es6-articles/blob/master/28%20-%20Spread%20Operator%20Introduction.md)
- [JavaScript & the spread operator](https://codeburst.io/javascript-the-spread-operator-a867a71668ca)
- [6 Great uses of the spread operator](https://davidwalsh.name/spread-operator)

### Object property shorthand

When assigning a variable to an object property, if the variable name is equal to the property name, you can do the following:

```js
const x = 10;
const myObj = { x };
console.log(myObj.x) // 10
```

#### Explanation

Usually (pre-ES2015) when you declare a new *object literal* and want to use variables as object properties values, you would write this kind of code:

```js
const x = 10;
const y = 20;

const myObj = {
  x: x, // assigning x variable value to myObj.x
  y: y // assigning y variable value to myObj.y
};

console.log(myObj.x) // 10
console.log(myObj.y) // 20
```

As you can see, this is quite repetitive because the properties name of myObj are the same as the variable names you want to assign to those properties.

With ES2015, when the variable name is the same as the property name, you can do this shorthand:

```js
const x = 10;
const y = 20;

const myObj = {
  x,
  y
};

console.log(myObj.x) // 10
console.log(myObj.y) // 20
```

#### External resources

- [Property shorthand - ES6 Features](http://es6-features.org/#PropertyShorthand)

### Promises

A promise is an object which can be returned synchronously from an asynchronous function ([ref](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261#3cd0)).

Promises can be used to avoid [callback hell](http://callbackhell.com/), and they are more and more frequently encountered in modern JavaScript projects.

#### Sample code

```js
const fetchingPosts = new Promise((res, rej) => {
  $.get("/posts")
    .done(posts => res(posts))
    .fail(err => rej(err));
});

fetchingPosts
  .then(posts => console.log(posts))
  .catch(err => console.log(err));
```

#### Explanation

When you do an *Ajax request* the response is not synchronous because you want a resource that takes some time to come. It even may never come if the resource you have requested is unavailable for some reason (404).

To handle that kind of situation, ES2015 has given us *promises*. Promises can have three different states:

- Pending
- Fulfilled
- Rejected

Let's say we want to use promises to handle an Ajax request to fetch the resource X.

##### Create the promise

We firstly are going to create a promise. We will use the jQuery get method to do our Ajax request to X.

```js
const xFetcherPromise = new Promise( // Create promise using "new" keyword and store it into a variable
  function(resolve, reject) { // Promise constructor takes a function parameter which has resolve and reject parameters itself
    $.get("X") // Launch the Ajax request
      .done(function(X) { // Once the request is done...
        resolve(X); // ... resolve the promise with the X value as parameter
      })
      .fail(function(error) { // If the request has failed...
        reject(error); // ... reject the promise with the error as parameter
      });
  }
)
```

As seen in the above sample, the Promise object takes an *executor* function which takes two parameters **resolve** and **reject**. Those parameters are functions which when called are going to move the promise *pending* state to respectively a *fulfilled* and *rejected* state.

The promise is in pending state after instance creation and its *executor* function is executed immediately. Once one of the function *resolve* or *reject* is called in the *executor* function, the promise will call its associated handlers.

##### Promise handlers usage

To get the promise result (or error), we must attach to it handlers by doing the following:

```js
xFetcherPromise
  .then(function(X) {
    console.log(X);
  })
  .catch(function(err) {
    console.log(err)
  })
```

If the promise succeeds, *resolve* is executed and the function passed as ```.then``` parameter is executed.

If it fails, *reject* is executed and the function passed as ```.catch``` parameter is executed.

> **Note :** If the promise has already been fulfilled or rejected when a corresponding handler is attached, the handler will be called, so there is no race condition between an asynchronous operation completing and its handlers being attached. [(Ref: MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise#Description)

#### External Resources

- [JavaScript Promises for dummies - Jecelyn Yeen](https://scotch.io/tutorials/javascript-promises-for-dummies)
- [JavaScript Promise API - David Walsh](https://davidwalsh.name/promises)
- [Using promises - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises)
- [What is a promise - Eric Elliott](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261)
- [JavaScript Promises: an Introduction - Jake Archibald](https://developers.google.com/web/fundamentals/getting-started/primers/promises)
- [Promise documentation - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

### Template literals

Template literals is an [*expression interpolation*](https://en.wikipedia.org/wiki/String_interpolation) for single and multiple-line strings.

In other words, it is a new string syntax in which you can conveniently use any JavaScript expressions (variables for instance).

#### Sample code

```js
const name = "Nick";
`Hello ${name}, the following expression is equal to four : ${2+2}`;

// Hello Nick, the following expression is equal to four: 4
```

#### External resources

- [String interpolation - ES6 Features](http://es6-features.org/#StringInterpolation)
- [ES6 Template Strings - Addy Osmani](https://developers.google.com/web/updates/2015/01/ES6-Template-Strings)

### Tagged template literals

Template tags are *functions that can be prefixed to a [template literal](#template-literals)*. When a function is called this way, the first parameter is an array of the *strings* that appear between the template's interpolated variables, and the subsequent parameters are the interpolated values. Use a spread operator `...` to capture all of them. [(Ref: MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals#Tagged_template_literals).

> **Note :** A famous library named [styled-components](https://www.styled-components.com/) heavily relies on this feature.

Below is a toy example on how they work.
```js
function highlight(strings, ...values) {
  const interpolation = strings.reduce((prev, current) => {
    return prev + current + (values.length ? "<mark>" + values.shift() + "</mark>" : "");
  }, "");

  return interpolation;
}

const condiment = "jam";
const meal = "toast";

highlight`I like ${condiment} on ${meal}.`;
// "I like <mark>jam</mark> on <mark>toast</mark>."
```

A more interesting example:
```js
function comma(strings, ...values) {
  return strings.reduce((prev, next) => {
    let value = values.shift() || [];
    value = value.join(", ");
    return prev + next + value;
  }, "");
}

const snacks = ['apples', 'bananas', 'cherries'];
comma`I like ${snacks} to snack on.`;
// "I like apples, bananas, cherries to snack on."
```

#### External resources
- [Wes Bos on Tagged Template Literals](http://wesbos.com/tagged-template-literals/)
- [Library of common template tags](https://github.com/declandewet/common-tags)

### Imports / Exports

ES6 modules are used to access variables or functions in a module explicitly exported by the modules it imports.

I highly recommend to take a look at MDN resources on import/export (see external resources below), it is both straightforward and complete.

#### Explanation with sample code

##### Named exports

Named exports are used to export several values from a module.

> **Note :** You can only name-export [first-class citizens](https://en.wikipedia.org/wiki/First-class_citizen) that have a name.

```js
// mathConstants.js
export const pi = 3.14;
export const exp = 2.7;
export const alpha = 0.35;

// -------------

// myFile.js
import { pi, exp } from './mathConstants.js'; // Named import -- destructuring-like syntax
console.log(pi) // 3.14
console.log(exp) // 2.7

// -------------

// mySecondFile.js
import * as constants from './mathConstants.js'; // Inject all exported values into constants variable
console.log(constants.pi) // 3.14
console.log(constants.exp) // 2.7
```

While named imports looks like *destructuring*, they have a different syntax and are not the same. They don't support default values nor *deep* destructuring.

Besides, you can do aliases but the syntax is different from the one used in destructuring:

```js
import { foo as bar } from 'myFile.js'; // foo is imported and injected into a new bar variable
```

##### Default import / export

Concerning the default export, there is only a single default export per module. A default export can be a function, a class, an object or anything else. This value is considered the "main" exported value since it will be the simplest to import. [Ref: MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export#Description)

```js
// coolNumber.js
const ultimateNumber = 42;
export default ultimateNumber;

// ------------

// myFile.js
import number from './coolNumber.js';
// Default export, independently from its name, is automatically injected into number variable;
console.log(number) // 42
```

Function exporting:

```js
// sum.js
export default function sum(x, y) {
  return x + y;
}
// -------------

// myFile.js
import sum from './sum.js';
const result = sum(1, 2);
console.log(result) // 3
```

#### External resources

- [ES6 Modules in bulletpoints](https://ponyfoo.com/articles/es6#modules)
- [Export - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export)
- [Import - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import)
- [Understanding ES6 Modules](https://www.sitepoint.com/understanding-es6-modules/)
- [Destructuring special case - import statements](https://ponyfoo.com/articles/es6-destructuring-in-depth#special-case-import-statements)
- [Misunderstanding ES6 Modules - Kent C. Dodds](https://medium.com/@kentcdodds/misunderstanding-es6-modules-upgrading-babel-tears-and-a-solution-ad2d5ab93ce0)
- [Modules in JavaScript](http://exploringjs.com/es6/ch_modules.html#sec_modules-in-javascript)

### <a name="this_def"></a> JavaScript *this*

*this* operator behaves differently than in other languages and is in most cases determined by how a function is called. ([Ref: MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)).

This notion is having many subtleties and being quite hard, I highly suggest you to deep dive in the external resources below. Thus, I will provide what I personally have in mind to determine what *this* is equal to. I have learned this tip from [this article written by Yehuda Katz](http://yehudakatz.com/2011/08/11/understanding-javascript-function-invocation-and-this/).

```js
function myFunc() {
  ...
}

// After each statement, you find the value of *this* in myFunc

myFunc.call("myString", "hello") // "myString" -- first .call parameter value is injected into *this*

// In non-strict-mode
myFunc("hello") // window -- myFunc() is syntax sugar for myFunc.call(window, "hello")

// In strict-mode
myFunc("hello") // undefined -- myFunc() is syntax sugar for myFunc.call(undefined, "hello")
```

```js
var person = {
  myFunc: function() { ... }
}

person.myFunc.call(person, "test") // person Object -- first call parameter is injected into *this*
person.myFunc("test") // person Object -- person.myFunc() is syntax sugar for person.myFunc.call(person, "test")

var myBoundFunc = person.myFunc.bind("hello") // Creates a new function in which we inject "hello" in *this* value
person.myFunc("test") // person Object -- The bind method has no effect on the original method
myBoundFunc("test") // "hello" -- myBoundFunc is person.myFunc with "hello" bound to *this*
```

#### External resources

- [Understanding JavaScript Function Invocation and "this" - Yehuda Katz](http://yehudakatz.com/2011/08/11/understanding-javascript-function-invocation-and-this/)
- [JavaScript this - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)

### Class

JavaScript is a [prototype-based](https://en.wikipedia.org/wiki/Prototype-based_programming) language (whereas Java is [class-based](https://en.wikipedia.org/wiki/Class-based_programming) language, for instance). ES6 has introduced JavaScript classes which are meant to be a syntactic sugar for prototype-based inheritance and **not** a new class-based inheritance model ([ref](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)).

The word *class* is indeed error prone if you are familiar with classes in other languages. If you do, avoid assuming how JavaScript classes work on this basis and consider it an entirely different notion.

Since this document is not an attempt to teach you the language from the ground up, I will assume you know what prototypes are and how they behave. If you do not, see the external resources listed below the sample code.

#### Samples

Before ES6, prototype syntax:

```js
var Person = function(name, age) {
  this.name = name;
  this.age = age;
}
Person.prototype.stringSentence = function() {
  return "Hello, my name is " + this.name + " and I'm " + this.age;
}
```

With ES6 class syntax:

```js
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  stringSentence() {
    return `Hello, my name is ${this.name} and I am ${this.age}`;
  }
}

const myPerson = new Person("Manu", 23);
console.log(myPerson.age) // 23
console.log(myPerson.stringSentence()) // "Hello, my name is Manu and I'm 23
```

#### External resources

For prototype understanding:

- [Understanding Prototypes in JS - Yehuda Katz](http://yehudakatz.com/2011/08/12/understanding-prototypes-in-javascript/)
- [A plain English guide to JS prototypes - Sebastian Porto](http://sporto.github.io/blog/2013/02/22/a-plain-english-guide-to-javascript-prototypes/)
- [Inheritance and the prototype chain - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)

For classes understanding:

- [ES6 Classes in Depth - Nicolas Bevacqua](https://ponyfoo.com/articles/es6-classes-in-depth)
- [ES6 Features - Classes](http://es6-features.org/#ClassDefinition)
- [JavaScript Classes - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)

### `Extends` and `super` keywords

The `extends` keyword is used in class declarations or class expressions to create a class which is a child of another class ([Ref: MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/extends)). The subclass inherits all the properties of the superclass and additionally can add new properties or modify the inherited ones.

The `super` keyword is used to call functions on an object's parent, including its constructor.

- `super` keyword must be used before the `this` keyword is used in constructor
- Invoking `super()` calls the parent class constructor. If you want to pass some arguments in a class's constructor to its parent's constructor, you call it with `super(arguments)`.
- If the parent class have a method (even static) called `X`, you can use `super.X()` to call it in a child class.

#### Sample Code

```js
class Polygon {
  constructor(height, width) {
    this.name = 'Polygon';
    this.height = height;
    this.width = width;
  }

  getHelloPhrase() {
    return `Hi, I am a ${this.name}`;
  }
}

class Square extends Polygon {
  constructor(length) {
    // Here, it calls the parent class' constructor with lengths
    // provided for the Polygon's width and height
    super(length, length);
    // Note: In derived classes, super() must be called before you
    // can use 'this'. Leaving this out will cause a reference error.
    this.name = 'Square';
    this.length = length;
  }

  getCustomHelloPhrase() {
    const polygonPhrase = super.getHelloPhrase(); // accessing parent method with super.X() syntax
    return `${polygonPhrase} with a length of ${this.length}`;
  }

  get area() {
    return this.height * this.width;
  }
}

const mySquare = new Square(10);
console.log(mySquare.area) // 100
console.log(mySquare.getHelloPhrase()) // 'Hi, I am a Square' -- Square inherits from Polygon and has access to its methods
console.log(mySquare.getCustomHelloPhrase()) // 'Hi, I am a Square with a length of 10'
```

**Note :** If we had tried to use `this` before calling `super()` in Square class, a ReferenceError would have been raised:

```js
class Square extends Polygon {
  constructor(length) {
    this.height; // ReferenceError, super needs to be called first!

    // Here, it calls the parent class' constructor with lengths
    // provided for the Polygon's width and height
    super(length, length);

    // Note: In derived classes, super() must be called before you
    // can use 'this'. Leaving this out will cause a reference error.
    this.name = 'Square';
  }
}
```

#### External Resources

- [Extends - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/extends)
- [Super operator - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/super)
- [Inheritance - MDN](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Inheritance)

### Async Await

In addition to [Promises](#promises), there is a new syntax you might encounter to handle asynchronous code named *async / await*.

The purpose of async/await functions is to simplify the behavior of using promises synchronously and to perform some behavior on a group of Promises. Just as Promises are similar to structured callbacks, async/await is similar to combining generators and promises. Async functions *always* return a Promise. ([Ref: MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function))

> **Note :** You must understand what promises are and how they work before trying to understand async / await since they rely on it.

> **Note 2:** [*await* must be used in an *async* function](https://hackernoon.com/6-reasons-why-javascripts-async-await-blows-promises-away-tutorial-c7ec10518dd9#f3f0), which means that you can't use await in the top level of our code since that is not inside an async function.

#### Sample code

```js
async function getGithubUser(username) { // async keyword allows usage of await in the function and means function returns a promise
  const response = await fetch(`https://api.github.com/users/${username}`); // Execution is paused here until the Promise returned by fetch is resolved
  return response.json();
}

getGithubUser('mbeaudru')
  .then(user => console.log(user)) // logging user response - cannot use await syntax since this code isn't in async function
  .catch(err => console.log(err)); // if an error is thrown in our async function, we will catch it here
```

#### Explanation with sample code

*Async / Await* is built on promises but they allow a more imperative style of code.

The *async* operator marks a function as asynchronous and will always return a *Promise*. You can use the *await* operator in an *async* function to pause execution on that line until the returned Promise from the expression either resolves or rejects.

```js
async function myFunc() {
  // we can use await operator because this function is async
  return "hello world";
}

myFunc().then(msg => console.log(msg)) // "hello world" -- myFunc's return value is turned into a promise because of async operator
```

When the *return* statement of an async function is reached, the Promise is fulfilled with the value returned. If an error is thrown inside an async function, the Promise state will turn to *rejected*. If no value is returned from an async function, a Promise is still returned and resolves with no value when execution of the async function is complete.

*await* operator is used to wait for a *Promise* to be fulfilled and can only be used inside an *async* function body. When encountered, the code execution is paused until the promise is fulfilled.

> **Note :** *fetch* is a function that returns a Promise that allows to do an AJAX request

Let's see how we could fetch a github user with promises first:

```js
function getGithubUser(username) {
  return fetch(`https://api.github.com/users/${username}`).then(response => response.json());
}

getGithubUser('mbeaudru')
  .then(user => console.log(user))
  .catch(err => console.log(err));
```

Here's the *async / await* equivalent:

```js
async function getGithubUser(username) { // promise + await keyword usage allowed
  const response = await fetch(`https://api.github.com/users/${username}`); // Execution stops here until fetch promise is fulfilled
  return response.json();
}

getGithubUser('mbeaudru')
  .then(user => console.log(user))
  .catch(err => console.log(err));
```

*async / await* syntax is particularly convenient when you need to chain promises that are interdependent.

For instance, if you need to get a token in order to be able to fetch a blog post on a database and then the author informations:

> **Note :** *await* expressions needs to be wrapped in parentheses to call its resolved value's methods and properties on the same line.

```js
async function fetchPostById(postId) {
  const token = (await fetch('token_url')).json().token;
  const post = (await fetch(`/posts/${postId}?token=${token}`)).json();
  const author = (await fetch(`/users/${post.authorId}`)).json();

  post.author = author;
  return post;
}

fetchPostById('gzIrzeo64')
  .then(post => console.log(post))
  .catch(err => console.log(err));
```

##### Error handling

Unless we add *try / catch* blocks around *await* expressions, uncaught exceptions – regardless of whether they were thrown in the body of your *async* function or while it’s suspended during *await* – will reject the promise returned by the *async* function. Using the `throw` statement in an async function is the same as returning a Promise that rejects. [(Ref: PonyFoo)](https://ponyfoo.com/articles/understanding-javascript-async-await#error-handling).

> **Note :** Promises behave the same!

With promises, here is how you would handle the error chain:

```js
function getUser() { // This promise will be rejected!
  return new Promise((res, rej) => rej("User not found !"));
}

function getAvatarByUsername(userId) {
  return getUser(userId).then(user => user.avatar);
}

function getUserAvatar(username) {
  return getAvatarByUsername(username).then(avatar => ({ username, avatar }));
}

getUserAvatar('mbeaudru')
  .then(res => console.log(res))
  .catch(err => console.log(err)); // "User not found !"
```

The equivalent with *async / await*:

```js
async function getUser() { // The returned promise will be rejected!
  throw "User not found !";
}

async function getAvatarByUsername(userId) => {
  const user = await getUser(userId);
  return user.avatar;
}

async function getUserAvatar(username) {
  var avatar = await getAvatarByUsername(username);
  return { username, avatar };
}

getUserAvatar('mbeaudru')
  .then(res => console.log(res))
  .catch(err => console.log(err)); // "User not found !"
```

#### External resources

- [Async/Await - JavaScript.Info](https://javascript.info/async-await)
- [ES7 Async/Await](http://rossboucher.com/await/#/)
- [6 Reasons Why JavaScript’s Async/Await Blows Promises Away](https://hackernoon.com/6-reasons-why-javascripts-async-await-blows-promises-away-tutorial-c7ec10518dd9)
- [JavaScript awaits](https://dev.to/kayis/javascript-awaits)
- [Using Async Await in Express with Node 8](https://medium.com/@Abazhenov/using-async-await-in-express-with-node-8-b8af872c0016)
- [Async Function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
- [Await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await)
- [Using async / await in express with node 8](https://medium.com/@Abazhenov/using-async-await-in-express-with-node-8-b8af872c0016)

### Truthy / Falsy

In JavaScript, a truthy or falsy value is a value that is being casted into a boolean when evaluated in a boolean context. An example of boolean context would be the evaluation of an ```if``` condition:

Every value will be casted to ```true``` unless they are equal to:

- ```false```
- ```0```
- ```""``` (empty string)
- ```null```
- ```undefined```
- ```NaN```

Here are examples of *boolean context*:

- ```if``` condition evaluation

```js
if (myVar) {}
```

```myVar``` can be any [first-class citizen](https://en.wikipedia.org/wiki/First-class_citizen) (variable, function, boolean) but it will be casted into a boolean because it's evaluated in a boolean context.

- After logical **NOT** ```!``` operator

This operator returns false if its single operand can be converted to true; otherwise, returns true.

```js
!0 // true -- 0 is falsy so it returns true
!!0 // false -- 0 is falsy so !0 returns true so !(!0) returns false
!!"" // false -- empty string is falsy so NOT (NOT false) equals false
```

- With the *Boolean* object constructor

```js
new Boolean(0) // false
new Boolean(1) // true
```

- In a ternary evaluation

```js
myVar ? "truthy" : "falsy"
```

myVar is evaluated in a boolean context.

Be careful when comparing 2 values. The object values (that should be cast to true) is **not** being casted to Boolean but it forced to convert into a primitive value one using [ToPrimitives specification](http://javascript.info/object-toprimitive). Internally, when an object is compared to Boolean value like `[] == true`, it does `[].toString() == true` so...

```js
let a = [] == true // a is false since [].toString() give "" back.
let b = [1] == true // b is true since [1].toString() give "1" back.
let c = [2] == true // c is false since [2].toString() give "2" back.
```

#### External resources

- [Truthy (MDN)](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
- [Falsy (MDN)](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)
- [Truthy and Falsy values in JS - Josh Clanton](http://adripofjavascript.com/blog/drips/truthy-and-falsy-values-in-javascript.html)

### Anamorphisms and Catamorphisms

#### Anamorphisms

Anamorphisms are functions that map from some object to a more complex structure containing the type of the object. It is the process of *unfolding* a simple structure into a more complex one. Consider unfolding an integer to a list of integers. The integer is our initial object and the list of integers is the more complex structure.

**Sample code**

```js
function downToOne(n) {
  const list = [];

  for (let i = n; i > 0; --i) {
    list.push(i);
  }

  return list;
}

downToOne(5)
  //=> [ 5, 4, 3, 2, 1 ]
```

#### Catamorphisms

Catamorphisms are the opposite of Anamorphisms, in that they take objects of more complex structure and *fold* them into simpler structures. Take the following example `product` which take a list of integers and returns a single integer.

**Sample code**

```js
function product(list) {
  let product = 1;

  for (const n of list) {
    product = product * n;
  }

  return product;
}

product(downToOne(5)) // 120
```

#### External resources

* [Anamorphisms in JavaScript](http://raganwald.com/2016/11/30/anamorphisms-in-javascript.html)
* [Anamorphism](https://en.wikipedia.org/wiki/Anamorphism)
* [Catamorphism](https://en.wikipedia.org/wiki/Catamorphism)

### Generators

Another way to write the `downToOne` function is to use a Generator. To instantiate a `Generator` object, one must use the `function *` declaration. Generators are functions that can be exited and later re-entered with its context (variable bindings) saved across re-entrances.

For example, the `downToOne` function above can be rewritten as:

```js
function * downToOne(n) {
  for (let i = n; i > 0; --i) {
    yield i;
  }
}

[...downToOne(5)] // [ 5, 4, 3, 2, 1 ]
```

Generators return an iterable object. When the iterator's `next()` function is called, it is executed until the first `yield` expression, which specifies the value to be returned from the iterator or with `yield*`, which delegates to another generator function. When a `return` expression is called in the generator, it will mark the generator as done and pass back as the return value. Further calls to `next()` will not return any new values.

**Sample code**

```js
// Yield Example
function * idMaker() {
  var index = 0;
  while (index < 2) {
    yield index;
    index = index + 1;
  }
}

var gen = idMaker();

gen.next().value; // 0
gen.next().value; // 1
gen.next().value; // undefined
```

The `yield*` expression enables a generator to call another generator function during iteration.

```js
// Yield * Example
function * genB(i) {
  yield i + 1;
  yield i + 2;
  yield i + 3;
}

function * genA(i) {
  yield i;
  yield* genB(i);
  yield i + 10;
}

var gen = genA(10);

gen.next().value; // 10
gen.next().value; // 11
gen.next().value; // 12
gen.next().value; // 13
gen.next().value; // 20
```

```js
// Generator Return Example
function* yieldAndReturn() {
  yield "Y";
  return "R";
  yield "unreachable";
}

var gen = yieldAndReturn()
gen.next(); // { value: "Y", done: false }
gen.next(); // { value: "R", done: true }
gen.next(); // { value: undefined, done: true }
```

#### External resources

* [Mozilla MDN Web Docs, Iterators and Generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators#Generators)

### Static Methods

#### Short explanation

The `static` keyword is used in classes to declare static methods. Static methods are functions in a class that belongs to the class object and are not available to any instance of that class.

#### Sample code

```js
class Repo {
  static getName() {
    return "Repo name is modern-js-cheatsheet"
  }
}

// Note that we did not have to create an instance of the Repo class
console.log(Repo.getName()) // Repo name is modern-js-cheatsheet

let r = new Repo();
console.log(r.getName()) // Uncaught TypeError: r.getName is not a function
```

#### Detailed explanation

Static methods can be called within another static method by using the `this` keyword, this doesn't work for non-static methods though. Non-static methods cannot directly access static methods using the `this` keyword.

##### Calling other static methods from a static method.

To call a static method from another static method, the `this` keyword can be used like so;

```js
class Repo {
  static getName() {
    return "Repo name is modern-js-cheatsheet"
  }

  static modifyName() {
    return this.getName() + '-added-this'
  }
}

console.log(Repo.modifyName()) // Repo name is modern-js-cheatsheet-added-this
```

##### Calling static methods from non-static methods.

Non-static methods can call static methods in 2 ways;
1. ###### Using the class name.

To get access to a static method from a non-static method we use the class name and call the static method like a property. e.g `ClassName.StaticMethodName`

```js
class Repo {
  static getName() {
    return "Repo name is modern-js-cheatsheet"
  }

  useName() {
    return Repo.getName() + ' and it contains some really important stuff'
  }
}

// we need to instantiate the class to use non-static methods
let r = new Repo()
console.log(r.useName()) // Repo name is modern-js-cheatsheet and it contains some really important stuff
```

2. ###### Using the constructor

Static methods can be called as properties on the constructor object.

```js
class Repo {
  static getName() {
    return "Repo name is modern-js-cheatsheet"
  }

  useName() {
    // Calls the static method as a property of the constructor
    return this.constructor.getName() + ' and it contains some really important stuff'
  }
}

// we need to instantiate the class to use non-static methods
let r = new Repo()
console.log(r.useName()) // Repo name is modern-js-cheatsheet and it contains some really important stuff
```

#### External resources
- [static keyword- MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/static)
- [Static Methods- Javascript.info](https://javascript.info/class#static-methods)
- [Static Members in ES6- OdeToCode](http://odetocode.com/blogs/scott/archive/2015/02/02/static-members-in-es6.aspx)

## Glossary

### <a name="scope_def"></a> Scope

The context in which values and expressions are "visible," or can be referenced. If a variable or other expression is not "in the current scope," then it is unavailable for use.

Source: [MDN](https://developer.mozilla.org/en-US/docs/Glossary/Scope)

### <a name="mutation_def"></a> Variable mutation

A variable is said to have been mutated when its initial value has changed afterward.

```js
var myArray = [];
myArray.push("firstEl") // myArray is being mutated
```

A variable is said to be *immutable* if it can't be mutated.

[Check MDN Mutable article](https://developer.mozilla.org/en-US/docs/Glossary/Mutable) for more details.

Créditos do texto Original: [Manuel Beaudru ⚡️](https://github.com/mbeaudru)
