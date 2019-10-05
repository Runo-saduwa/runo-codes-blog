---
title: The var keyword
date: "2019-10-03"
description: Learn about the legacy way of declaring variables and also the pros and cons of using it.
---

<img src="https://thepracticaldev.s3.amazonaws.com/i/j29y0qb9yuq0koky66zs.png" >

Before ES6, all variables in JavaScript were declared with the var keyword. This keyword causes our variables to have a function scope.

Lets understand this better with the following code snippet:
 ```javascript
  function SayName(){
   var name = "Tega";
   }

console.log(name)//Undefined
 ```
The console prints out `undefined` because the variable `name` inside the `SayName` function is <strong>not</strong> visible outside the `SayName`function.

The behaviour is quite different in another block that is not a function block. For example, see what happens in an if block.

```javascript
  if(true){
   var name = "Tega";
   }

console.log(name)//Tega
 ```
The console prints `Tega`.

Considering the results from the two examples, it is evident that variables declared with the `var` keyword have a local scope <strong>only</strong> when they are found within a function block.

<strong>It's a bad behaviour</strong>
This is a bad behaviour that has caused a lot of frustration amongst JavaScript programmers. Prior to ES6, JavaScript had function scope, but <em>block scoping</em> is more common in most programming languages. With ES6, `let` and `const` keywords were introduced to allow us to declare variables that are block scoped which is a safe behaviour.


Thank you for reading!
Happy Coding!❤