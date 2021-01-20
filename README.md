
---
---
## 20/01/2021
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
    console.log(a);                                     //[ 'constituição', 'anel', 'músculo', 'oi', 'pedra', 'zumb', 'casa' ]
    console.log(a.sort());                              //[ 'anel', 'casa', 'constituição', 'músculo', 'oi', 'pedra', 'zumb' ]
    console.log(a.sort((a, b) => a.length - b.length)); //[ 'oi', 'anel', 'casa', 'zumb', 'pedra', 'músculo', 'constituição' ]
}
ordenado([ "constituição", "anel", "músculo", "oi", "pedra", "zumb", "casa"])

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
