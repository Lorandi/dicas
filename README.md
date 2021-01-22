---
---

## 22/01/2021
# map()
O método **map()** chama a função `callback` recebida por parâmetro para cada elemento do Array original, em ordem, e constrói um novo array com base nos retornos de cada chamada.

```javascript
const array = [ '1', '3', '2', '5', '3' ]
const toNum = array.map(Number)
console.log(toNum) //[1,3,2,5,3]
```

```javascript
var numbers = [1, 4, 9];
var roots = numbers.map(Math.sqrt);
// roots é [1, 2, 3], numbers ainda é [1, 4, 9]
```

```javascript
const array = [1,3,2,5,3]
const toStr = array.map(String)
console.log(toStr) //[ '1', '3', '2', '5', '3' ]
```

```javascript
const digitize = n => n.toString().split('').map(Number).reverse();
console.log(digitize(35231)) //[1,3,2,5,3]
```

#
# reval() 
A função eval() computa um código JavaScript representado como uma string.
Se você construir uma expressão aritmética como uma string, você pode usar eval() para calcular o resultado depois.
Se o argumento de eval() não é uma string, eval() retorna o argumento inalterado. No exemplo a seguir, o construtor String é especificado, e eval() retorna um objeto String em vez de avaliar a string.

```javascript
eval(new String("2 + 2")); //[String: '2 + 2']
eval("2 + 2");             //4
```

```javascript
const basicOp = (operation, value1, value2) => eval(value1+operation+value2)
console.log(basicOp('+', 4, 7))     //11
console.log(basicOp('-', 15, 18))   // -3)
console.log(basicOp('*', 5, 5))     //25
console.log(basicOp('/', 49, 7))    // 7
```
https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/eval
---
---
## 21/01/2021
# reduce() 
**Syntax** `array.reduce(function(total, currentValue, currentIndex, arr), initialValue)`

Sendo os dois primeiros necessários e os dois outros opcionais.

O método reduce() executa uma função reducer (fornecida por você) para cada elemento do array, resultando num único valor de retorno.

```javascript
const array1 = [1, 2, 3, 4];
const reducer = (accumulator, currentValue) => accumulator + currentValue;

console.log(array1.reduce(reducer)); //10

console.log(array1.reduce(reducer, 5)); //esse 5 que aparece é o valor inicial que será somado ao acumulador
// expected output: 15
```
https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce

https://www.w3schools.com/jsref/jsref_reduce.asp

https://www.lewagon.com/pt-BR/blog/array-reduce-aprenda-usar-metodo-javascript

#
# .filter(Boolean)
Retira de uma lista os elementos que são falsy como empty string, undefined, null ou false.
O método filter() cria um novo array com todos os elementos que passaram no teste implementado pela função fornecida.
**Sintaxe:** `var newArray = arr.filter(callback[, thisArg])`
```javascript
var arrayBugado = [undefined, "bom", null, 5, true, "certo", "errado", false,NaN ];
var arrayArrumado = arrayBugado.filter(Boolean);
console.log(arrayArrumado) //[ 'bom', 5, true, 'certo', 'errado' ]
```

```javascript
function isBigEnough(value) {
  return value >= 10;
}
var filtered = [12, 5, 8, 130, 44].filter(isBigEnough);
// filtered is [12, 130, 44]
```
https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array/filtro

https://www.michaeluloth.com/filter-boolean

#

# typeof
O operador typeof retorna uma string indicando o tipo de um operando
`"undefined", "object", "boolean", "number", "string", "function"`

```javascript
typeof 3.14 === 'number';
typeof true === 'boolean';
typeof "bla" === 'string';
```

```javascript
function problem(x){
    return typeof x == 'string' ? 'Error' : (x * 50 + 6);
}
  console.log(problem(1));       //56
  console.log(problem(5));       //256  
  console.log(problem("Olá"));   //'Error'
```

#

# Set() constructor
The **Set** constructor lets you create `set()` objects that store ***unique*** values of any
type, whether primitive values or object references.

**Syntax**
`new Set([iterable])`

```javascript
function newArray(array){
    return set = [...new Set(array)];  //usa [... Set()] para retornar só o array.
                                       //Se não usar aparece Set{elementos do array}  
}
console.log(newArray([0, 1,1,1 ,2, 3,4,4,4, 5])) //[ 0, 1, 2, 3, 4, 5 ]
console.log(newArray(["cavalo","cavalo","pato", "galinha", "cão","cão"])); //[ 'cavalo', 'pato', 'galinha', 'cão' ]
```


---
---
## 20/01/2021
# Slice() e repeat()

### JavaScript String repeat() method
The repeat() method returns a new string with a specified number of copies of the string it was called on.
```javascript
function repeatStr (n, s) {
  return s.repeat(n);
}
console.log(repeatStr(6, "I")) // "IIIIII"
console.log(repeatStr(5, "Hello")) // "HelloHelloHelloHelloHello"
```
https://www.w3schools.com/jsref/jsref_repeat.asp

#
### String.prototype.slice()
The slice() method extracts a section of a string and returns it as a new string, without modifying the original string.
Quando só tem um parametro, exclui apenas aquela section. Quando tem dois, a section é um intervalo: slice(inicio,fim).

```javascript
function removeChar(inicio,fim){
    str = '1234567890'        
    return str.slice(inicio,fim);
};
console.log(removeChar(0));     //1234567890
console.log(removeChar(-3,-1)); //89
console.log(removeChar(2));     //34567890
console.log(removeChar(1,-1));  //23456789
console.log(removeChar(0,3));   //123
```
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/slice




# Split(), reverse () e join()
```javascript
function solution(str){    
    reverse = str.split('')     //separa letras da string em  um array com vírgulas
    console.log(reverse);       //[ 'W', 'o', 'r', 'l', 'd' ]
    
    reverse =reverse.reverse(); //inverte a ordem dos elementos do array
    console.log(reverse);       //[ 'd', 'l', 'r', 'o', 'W' ]
    
    reverse =reverse.join('');  //junta os elementos, retirando as vírgulas. Poderia por qualquer coisa entre as ''. 
    console.log(reverse);       //dlroW
    return reverse;             //dlroW
    
    //return str.split('').reverse().join('');  //dlroW
}

console.log(solution("World"))
```
#
### String.prototype.split()
O método split() divide uma String em uma lista ordenada de substrings, coloca essas substrings em um array e retorna o array. A divisão é feita procurando um padrão, onde o padrão é fornecido como o primeiro parâmetro na chamada do método.

```javascript
const string= 'João'
const split1 = string.split()
const split2 = string.split("")

console.log(string); //João
console.log(split1); //[ 'João' ]
console.log(split2); //[ 'J', 'o', 'ã', 'o' ]
```
https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/String/split
#
### Array.prototype.reverse()
O método reverse() inverte os itens de um array. O primeiro elemento do array se torna o último e o último torna-se o primeiro.
```javascript
var myArray = ['one', 'two', 'three'];
myArray.reverse();

console.log(myArray) // ['three', 'two', 'one']
```
https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse
#
### Array.prototype.join()
O método join() junta todos os elementos de um array (ou um array-like object) em uma string e retorna esta string.

**Separador:** Específica uma string para separar cada elemento adjacente do array. O separador é convertido em uma string se necessário. Se omitido, os elementos do array são separados com uma vírgula (","). Se o separador for uma string vazia, todos os elementos são juntados sem nenhum caracter entre eles.

```javascript
const elements = ['Fire', 'Air', 'Water'];

console.log(elements.join());     //"Fire,Air,Water"

console.log(elements.join(''));   //"FireAirWater"

console.log(elements.join('-'));  //"Fire-Air-Water"

```
https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array/join


---
# Arrow functions
```javascript
hello = () => {
  return "Hello World!";
  }
  console.log(hello()); //Hello World!
}
```

```javascript
hello = () => "Hello World!"; // Return value by default
console.log(hello()); //Hello World!
```

```javascript
hello = (a,b) => a + b; //parâmetros vão dentro do parênteses
console.log(hello ("Hello"," World")); //Hello World!
```

```javascript
hello = a => a + " World"; //se tive apenas um parâmetro, não precisa parênteses
console.log(hello ("Hello")); //Hello World!
```

Na **Arow Function**, ela ira retornar o que está após o **=>** sem necessidade de usar **{}** ou return. Pode botar o bloco entre **()**. Se usar **{}**, necessário usar **return**.
```javascript
const isDivisible = (n, x, y) => (n % x == 0) && (n % y == 0)? true : false
const isDivisible = (n, x, y) => ((n % x == 0) && (n % y == 0)? true : false)
const isDivisible = (n, x, y) => {return (n % x == 0) && (n % y == 0)? true : false}
```

https://www.w3schools.com/js/js_arrow_function.asp

https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Functions/Arrow_functions
#
# Ternary Operator
**Syntax**
`variablename = (condition) ? value1:value2 `
O operador condicional (ternário) é o único operador JavaScript que possui três operandos. Este operador é frequentemente usado como um atalho para a instrução if.
```javascript
const even_or_odd = number => number % 2 == 0 ? "Even" : "Odd";
console.log(even_or_odd(33)) // - 1 - Odd
console.log(even_or_odd(2))  // - 0 - Even
console.log(even_or_odd(0))  // - 0 - Even
```
https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Operators/Operador_Condicional

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator

---
---

## 19/01/2021

# JavaScript Array sort() Method

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.sort(); //["Apple","Banana", "Mango","Orange"];
```  

```javascript
var points = [40, 100, 1, 5, 25, 10];
points.sort(); //[ 1, 10, 100, 25, 40, 5 ]

points.sort((a, b)=>a-b); // [ 1, 5, 10, 25, 40, 100 ]
//points.sort(function(a, b){return b-a});
            
points.sort((a, b)=>b-a);// [ 100, 40, 25, 10, 5, 1 ]
//points.sort(function(a, b){return b-a});
``` 

```javascript
const ordenado = (a) => {
    console.log(a);                                     //[ 'constituição', 'anel', 'músculo', 'oi',  'zumb', 'casa' ]
    console.log(a.sort());                              //[ 'anel', 'casa', 'constituição', 'músculo', 'oi', 'zumb' ]
    console.log(a.sort((a, b) => a.length - b.length)); //[ 'oi', 'anel', 'casa', 'zumb', 'músculo', 'constituição' ]
}
ordenado([ "constituição", "anel", "músculo", "oi", "zumb", "casa"])

```

```javascript
const flip=(d, a)=>{
    if(d === 'R') return console.log(a.sort((a,b)=>a-b));
    if(d === 'L') return console.log(a.sort((a,b)=>b-a));
}

flip('R', [95,43,1,23,100,13,200,55]); //[1, 13,  23,  43, 55, 95, 100, 200]
flip('L', [95,43,1,23,100,13,200,55])  //[200, 100, 95, 55, 43,  23, 13,  1]
```

https://www.w3schools.com/jsref/jsref_sort.asp

https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array/sort
