
---
---
## 20/01/2021
# Split(), reverse (), join() e slice()
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

https://www.w3schools.com/js/js_arrow_function.asp

https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Functions/Arrow_functions


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
