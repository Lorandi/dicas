---
---
# 09/02/2021
# .sbstr()
O método substr() retorna uma parte da string, começando no índice especificado e estendendo-se por um determinado número de caracteres posteriormente.

```javascript
const str = 'Mozilla';
console.log(str.substr(1, 2)); //"oz"
console.log(str.substr(2)); //"zilla"
```
**Sintaxe:** `str.substr(start[, length])`

```javascript
const solution = (a,b) => b === a.substr(a.length - b.length);   
console.log(solution('abcde', 'cde'))//true
console.log(solution('abcde', 'abc'))//false
console.log(solution('abc', 'c'))//true
console.log(solution('abc', 'd'))//false
```




https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/String/substr



---
---
# 08/02/2021
# toString()
O método `toString()` retorna uma string representando o objeto.

Decimal para binário
```javascript
const addBinary = value => value.toString(2)     
console.log(addBinary(3)) //11
console.log(addBinary(12)) //1100
console.log(addBinary(45)) //101101
```

Decimal para hexadecimal
```javascript
const addBinary = value => value.toString(16)     
console.log(addBinary(3))  //3
console.log(addBinary(12)) //c
console.log(addBinary(45)) //2d
```



#
# parseInt()
A função parseInt() analisa um argumento string e retorna um inteiro na base especificada.

`parseInt(string, base);`
## string
O valor a analisar. Se o argumento string não for uma string, então o valor é convertido para uma string (utilizando a operação abstrata ToString). Os espaços em branco na string são ignorados.

## base
Um inteiro entre 2 e 36 que representa a base da string (sistemas numéricos matemáticos) mencionada no parâmetro anterior. Base `2` para sistema numérico binário e `10` para decimal.


Binário para decimal
```javascript
const binaryArrayToNumber = arr => parseInt(arr, 2)
console.log(binaryArrayToNumber('0010'))     //2
console.log(binaryArrayToNumber('1111'))     //15
console.log(binaryArrayToNumber('0110'))     //6
```
https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/parseInt

---
---
# 05/02/2021
# Regex

Uma expressão regular é um método formal de se especificar um padrão de texto.
Com ela podemos lidar com as seguintes situações:
 - procura;
 - substituição;
 - validação de formatos;
 - filtragem de informações
 
 Pode ser feito com construtor `const regex = new RegExp('dog','gi')` ou de forma literal `const regex = /dog/gi`
 
### Flags
Elas adicionam comportamentos adicionais a nossas regras, como:
 - `g` - indicar achar todas as ocorrências da regex
 - `i` - ignora case sensitive
 - `m` - multilinha, lida com caracteres de inicio e fim (`^` e `$`) ao operar em múltiplas linhas.
 
 ### Conjuntos “ [ ] ”
 Com os conjuntos dizemos a regex que uma determinada casa pode ter diversos valores para dar match.
 `[/[em²]/gi]` ,  `/[a-z]/` (adiciona range - intervalos) ,  `/[0-9]/`
 Range obedece a mesma ordem da tabela Unicode, sendo assim regex como [a-Z] ou [4-1] produziram erro.
 
 Temos também os conjuntos negados, que como o nome sugere, dar match em tudo que não faça parte do conjunto. Para definí-lo iniciamos a regra do conjunto com `^` , por exemplo `[^a-z]` que aceita tudo que não seja entre a à z. `/[^aeiouí]/gi` aceita tudo que não são as vogais
 
 ## Métodos
 ### test
 Um método RegExp que testa uma correspondência em uma string. Retorna true ou false.
  ```javascript
 const validatePIN = s => /^(\d{4}|\d{6})$/.test(s)
 console.log(validatePIN("0000"))    //true
 console.log(validatePIN("12345"))   //false
 console.log(validatePIN("000000"))  //true
 console.log(validatePIN(".00000"))  //false
 ```
 
 ### match
 Um método String que executa uma pesquisa por uma correspondência em uma string. Retorna uma array de informações ou null caso não haja uma correspondência.
 
 ```javascript
 const validatePIN = s => s.match("^\\d{4}$") ? true : s.match("^\\d{6}$") ? true : false
 console.log(validatePIN("1234"))  //true
 console.log(validatePIN("1"))     //false
 console.log(validatePIN("123"))   //false
 console.log(validatePIN("a234"))  //false
 console.log(validatePIN("0000"))  //true
 ```
 
 
 ### replace
 Um método String que executa uma pesquisa por uma correspondência em uma string, e substitui a substring correspondênte por uma substring de substituição.
 
 ### exec
 Um método RegExp  que execute uma pesquisa por uma correspondência em uma string. Retorna um array de informações.
 

 ### search
 Um método String que testa uma correspondência em uma string. Retorna o indice da correspondência ou -1 se o teste falhar.
 
 ### split
 Um método String  que usa uma expressão regular ou uma string fixa para quebrar uma string dentro de um array de substrings.
 
 
 ### Significado dos caracteres especiais nas expressões regulares 
 
 https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/RegExp
 
 # 
 
 https://github.com/alexandreservian/regex-cheat-sheet
 
https://medium.com/@alexandreservian/regex-um-guia-pratico-para-express%C3%B5es-regulares-1ac5fa4dd39f

https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Regular_Expressions

---
---
# 01/02/2021
# match()
O método `match()` retorna uma correspondência entre uma string com uma expressão regular.


```javascript
var str = "The rain in SPAIN stays mainly in the plain"; 
console.log(str.match(/ain/g).length) //3
console.log(str.match(/ain/g)) //[ 'ain', 'ain', 'ain' ]
console.log(str.match(/ain/gi)) //[ 'ain', 'AIN', 'ain', 'ain' ]
```

https://www.w3schools.com/jsref/jsref_match.asp
https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/String/match
#


# isFiniete(), isInteger(), isNaN()

### isFinite()
The `Number.isFinite()` method determines whether a value is a finite number. Retorna um Bollean
```javascript
Number.isFinite(-1.23) //true
Number.isFinite(5-2) //true
Number.isFinite(0) //true
Number.isFinite('123') //false
Number.isFinite('Hello') //false
```

### isInteger()
O método Number.isInteger() determina se o valor passado é um inteiro. Retorna um Bollean
`Number.isInteger(value)`

```javascript
Number.isInteger(1);         // true
Number.isInteger(-100000);   // true
Number.isInteger(0.1);       // false
Number.isInteger(Math.PI);   // false
```

### isNaN()
The `Number.isNaN()` method determines whether a value is NaN (Not-A-Number).
This method returns true if the value is of the type Number, and equates to NaN. Otherwise it returns false.

```javascript
Number.isNaN(123) //false
Number.isNaN(-1.23) //false
Number.isNaN(5-2) //false
Number.isNaN(0) //false
Number.isNaN('123') //false
Number.isNaN('Hello') //false
Number.isNaN('2005/12/12') //false
Number.isNaN('') //false
Number.isNaN(true) //false
Number.isNaN(undefined) //false
Number.isNaN('NaN') //false
Number.isNaN(NaN) //true
Number.isNaN(0 / 0) //true
```

https://www.w3schools.com/jsref/jsref_obj_number.asp
https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Number/isInteger


---
---
# 30/01/2021
# Transformar um número em string e ao contrário

### number => string
```javascript
var numbers = 4568;
console.log(String(numbers))
console.log(numbers.toString())
console.log(('' + numbers))
```
#
### string => number
```javascript
var string = '4568';
console.log(Number(string))
console.log(+string)
console.log(string = +string)
```


---
---
# 29/01/2021
# apply()
O método `apply()` chama uma função com um dado valor this e arguments providos como uma array (ou um objeto parecido com um array).
Nota: A sintaxe desta função é quase idêntica a essa da call(), a diferença é que call() aceita uma  lista de argumentos, enquanto apply() aceita um array de argumentos.

```javascript
function highAndLow(numbers){
  numbers = numbers.split(' ').map(Number);
  return Math.max.apply(0, numbers) + ' ' + Math.min.apply(0, numbers);
}
console.log(highAndLow("1 2 3 4 5"))     // "5 1"
console.log(highAndLow("1 2 -3 4 5"))    // "5 -3"
console.log(highAndLow("1 9 3 4 -5"))    // "9 -5"
```
https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Function/Apply

---
---
# 28/01/2021
# startsWith() e endsWith()
O método `startsWith()` determina se uma string começa e o método `endsWith()` se termina com determinados caracteres, retornando true ou false.

```javascript
const str1 = (string) => string.startsWith(["c"])
console.log(str1("chocolate")) //true
console.log(str1("bala")) //false
```

```javascript
const str2 = (string) => string.endsWith(["a"])
console.log(str2("chocolate")) //false
console.log(str2("bala")) //true
```



---
---
## 25/01/2021
# Math.min() e Math.max()
Essas funções retornam os valores mínimos e máximos passados como parametro.

```javascript

var list = [4,6,2,1,9,63,-134,566]
console.log(Math.min(...list)); //-134
console.log(Math.max(...list)); //566

console.log(Math.min(3,2,9,7)); //2
console.log(Math.max(3,2,9,7)); //9

var array = ["cachorro","gato","macaco"]
console.log(Math.min(...array)); //Nan
console.log(Math.max(...array)); //Nan
```

#

# replace()
The replace() method searches a string for a specified value, or a regular expression, and returns a new string where the specified values are replaced.

Note: If you are replacing a value (and not a regular expression), only the first instance of the value will be replaced. To replace all occurrences of a specified value, use the global (g) modifier 

**Sintaxe:** `str.replace(exp, newExp)`

`g` Combinação global.

`i` Ignora diferenças entre maiúsculas e minúsculas.

`m` Combinação em várias linhas.

`y` Sticky

Este método não muda o objeto String. Ele simplesmente retorna uma nova string.

Para realizar uma pesquisa global e substituir, inclua a flag g na expressão regular ou se o primeiro parâmetro for uma string, inclua g no parâmetro flags.

```javascript
var frase = "O carro preto foi avistado";
console.log(frase.replace(/preto/,"azul")); //O carro azul foi avistado
```
```javascript
const DNAtoRNA = dna => dna.split("").map(x => x.replace("T","U")).join("")
console.log(DNAtoRNA("TTTT"))       //"UUUU")
console.log(DNAtoRNA("GCAT"))       //"GCAU")
```

```javascript
const DNAtoRNA = dna => dna.replace(/T/g, 'U')
console.log(DNAtoRNA("TTTT"))       //"UUUU")
console.log(DNAtoRNA("GCAT"))       //"GCAU")
```

```javascript
const trocarNumeroComG = numero => numero.replace(/3/g, 7)
console.log(trocarNumeroComG("133331")) //177771 com /g trocou todos

const trocarNumeroSemG = numero => numero.replace(/3/, 7)
console.log(trocarNumeroSemG("133331")) //173331 sem /g trocou só o primeiro
```



https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/String/replace

https://www.w3schools.com/jsref/jsref_replace.asp

#

# includes()
O método `includes()` determina se um array contém um determinado elemento, retornando true ou false apropriadamente.

**Sintaxe**  `array.includes(searchElement[, fromIndex])`

```javascript
const check = (a,x) => a.includes(x);

console.log(check([66, 101], 66))//true);
console.log(check([80, 117, 115, 104, 45, 85, 112, 115], 45))//true);
console.log(check(['t', 'e', 's', 't'], 'e'))//true);
console.log(check(['what', 'a', 'great', 'kata'], 'kat'))//false);
```





#
# Array.from()

O método `Array.from()` cria uma nova instância de um Array quando for passado um array-like ou um iterable object como argumento.

**Sintaxe** `Array.from(arrayLike[, mapFn[, thisArg]])`

```javascript
function f() {
    return Array.from(arguments);
  }  
  console.log(f(1, 2, 3)); // [1, 2, 3]
  
  var s = new Set(["foo"]);
  console.log( Array.from(s));// ["foo"]  
  
  console.log( Array.from("foo")); // ["f", "o", "o"]
  
  console.log(Array.from([1, 2, 3], x => x + x));// [2, 4, 6]  
  
  // Gerando uma sequência de números
  console.log(Array.from({length: 5}, (x, k) => k + 1));// [ 1, 2, 3, 4, 5]
  ```
  https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array/from

#

# fill()

O método fill() preenche todos os valores do array a partir do índice inicial a um índice final com um valor estático.

**Sintaxe:** `arr.fill(valor[, ínicio = 0[, fim = this.length]])`

O método **fill** pode receber até três argumentos valor, ínicio e fim. Os argumentos ínicio e fim são opcionais com valor padrão 0 (valor) e o tamanho do objeto (fim).

O método **fill** é um método mutável, ele irá mudar o objeto em si, e retorná-lo, não somente uma cópia do objeto.

```javascript
[1, 2, 3].fill(4);               // [4, 4, 4]
[1, 2, 3].fill(4, 1);            // [1, 4, 4]
[1, 2, 3].fill(4, 1, 2);         // [1, 4, 3]
[1, 2, 3].fill(4, 1, 1);         // [1, 2, 3]
[1, 2, 3].fill(4, -3, -2);       // [4, 2, 3]
[1, 2, 3].fill(4, NaN, NaN);     // [1, 2, 3]
Array(3).fill(4);                // [4, 4, 4]
[].fill.call({ length: 3 }, 4);  // {0: 4, 1: 4, 2: 4, length: 3}
```
https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array/fill

#

# concat()

O método `concat()` retorna um novo array contendo todos os arrays ou valores passados como parâmetro

**Sintaxe:** `array1.concat(array2, valor3, ..., valorN)`

`concat()` cria um novo array unindo todos os elementos que foram passados como parâmetro, na ordem dada, para cada argumento e seus elementos (se o elemento passado for um array).


```javascript
var a = ["a"];
var b = ["casa,carro"];
var c = [3];
var d = [8,7]
const concatenados = (a,b,c,d) => a.concat(b,c,d);
console.log(concatenados(a,b,c,d)); //[ 'a', 'casa,carro', 3, 8, 7 ]
```

```javascript
const arrayPlusArray = (arr1, arr2) => arr1.concat(arr2).reduce((a,b)=>a+b)
console.log(arrayPlusArray([1, 2, 3], [4, 5, 6]));    // 21
console.log(arrayPlusArray([0, 0, 0], [4, 5, 6]));    // 15
```
https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array/concat



---
---
## 23/01/2021
# `continue` e `break`
The `break` statement terminates the current loop, switch, or label statement and transfers program control to the statement following the terminated statement.

A palavra chave `continue` termina a atual iteração do laço em que ele se encontra ou de um laço rotulado, e continua a execução deste laço com a próxima iteração.

Diferentemente do  `break`, o `continue` não termina a execução do laço. 


---
---

## 22/01/2021
# indexOf()
O método indexOf() retorna o primeiro índice em que o elemento pode ser encontrado no array, retorna -1 caso o mesmo não esteja presente.

**Sintaxe** `array.indexOf(elementoDePesquisa, [pontoInicial = 0])`

**indexOf()** compara o  elementoDePesquisa com os elementos do Array usando igualdade estrita (o mesmo método usado pelo ===, ou triple-equals operator). 

```javascript
const findNeedle = haystack =>  haystack.indexOf('needle')
console.log(findNeedle(['hay', 'junk', 'hay', 'hay', 'moreJunk', 'needle', 'randomJunk'])) //5
```

#
# map()
O método **map()** chama a função `callback` recebida por parâmetro para cada elemento do Array original, em ordem, e constrói um novo array com base nos retornos de cada chamada.

```javascript
const maps = array => array.map(x => x * 2) 
console.log(maps([1, 2, 3]))  //[2, 4, 6]);
```

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
https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array/map

https://medium.com/@viniciusdacal/javascript-array-map-filter-e-reduce-tr%C3%AAs-m%C3%A9todos-para-manipula%C3%A7%C3%A3o-de-arrays-3fa9aebaf7fe

#
# eval() 
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

# .filter()
O método `filter()` cria um novo array com todos os elementos que passaram no teste implementado pela função fornecida.

```javascript
const friend = friends => friends.filter(friend => friend.length == 4);
console.log(friend(["Ryan", "Kieran", "Mark"]))     //["Ryan", "Mark"]);
console.log(friend(["Ryan", "Jimmy", "123", "4", "Cool Man"]))      //["Ryan"]);
```

```javascript
function isBigEnough(value) {
  return value >= 10;
}
var filtered = [12, 5, 8, 130, 44].filter(isBigEnough);
// filtered is [12, 130, 44]
```

```javascript
const removeEveryOther = arr => arr.filter((elem, index) => index % 2 === 0);
console.log(removeEveryOther([1, 2, 3, 4, 5, 6, 7, 8, 9, 10]))//[1, 3, 5, 7, 9]);
```


## .filter(Boolean)
Retira de uma lista os elementos que são falsy como empty string, undefined, null ou false.
O método filter() cria um novo array com todos os elementos que passaram no teste implementado pela função fornecida.
**Sintaxe:** `var newArray = arr.filter(callback[, thisArg])`
```javascript
var arrayBugado = [undefined, "bom", null, 5, true, "certo", "errado", false,NaN ];
var arrayArrumado = arrayBugado.filter(Boolean);
console.log(arrayArrumado) //[ 'bom', 5, true, 'certo', 'errado' ]
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
