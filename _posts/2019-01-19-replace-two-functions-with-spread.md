---
layout: post
title: "Replace two functions with spread Operator"
categories: javascript
---



There is a relatively new operator  called spread, and it is sybolized by three persiods such as ... [the docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax "mdn" target="_blank")
It separates out arrays, strings, and objects and allows you to manipulate them in ways that could be have been a pain in the past. The code below is just one example where the spread operator replaces two functions that would have been used before. 

``` javascript
// this is the old way
var myOldArray = ['a', 'b','c','d'];
myOldArray.push('end');
myOldArray.unshift('start');
console.log(myOldArray);

// and this is the new cool kids way
let myES6Array = ['a', 'b','c','d'];
myES6Array = ['start',...myES6Array, 'end'];
console.log(myES6Array);
```

create for this goes to [Joshua Fluke](https://www.youtube.com/watch?v=6Wzj7kxfRdI) for showing this neat trick. 


