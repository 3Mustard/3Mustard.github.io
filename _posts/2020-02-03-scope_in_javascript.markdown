---
layout: post
title:      "Scope in JavaScript"
date:       2020-02-03 15:37:47 -0500
permalink:  scope_in_javascript
---


**Global Scope **

Contains variables declared outside of any functions 

```
let myCat = "Akira"

function feedCat(){
  console.log(`${myCat} was fed.`) //Akira was fed
}
```

the function feedCat has access to the variable myCat because it was declared in global scope.

**Local Scope**

Variables defined within a function

```
function printName(){
  let name = "Matt"
	console.log(name) //Matt 
}

console.log(name) //Uncaught ReferenceError: name is not defined
```

name is declared in the function printName and cannot be accessed outside of it.

**Block Statements**

let and const declared in blocks(if,switch,for,while) support the declaration of local scope
vars do not.

```
function myFunction() {
    var a = "first Value"
    let b = "first Value"
    const c = "first Value"
    d = "first Value"
    if (true) {
      var a = "second Value"
      let b = "second Value"
      const c = "second Value"
      d = "second Value"
    }
    // what will each statement log to the console?
    console.log(a) //second value
    console.log(b) //first value
    console.log(c) //first value
    console.log(d) //second value
}
```

let and const support local scope in block statements, console.log is called outside of the if block so it has no idea what the values of b and c are within that block. 

var does not support local scope in a block statement so when if (true) is evaluated and var a is assigned "second value" it overwrites var a = "first value"

d is a global variable and so it can be accessed and changed anywhere in our code.



