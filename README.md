

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

https://www.w3schools.com/jsref/jsref_sort.asp

https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array/sort
