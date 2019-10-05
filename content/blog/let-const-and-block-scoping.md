---
title: let, const & Block scoping
date: "2019-09-31"
description: Learn about the quirks and perks of major keywords used in declaring variables in JavaScript.
---

<img src="https://thepracticaldev.s3.amazonaws.com/i/y9zb6hktm7ndk6oi920x.png">
<h1>What is block scoping?!</h1>
Quite simply, this means a new scope is created between a pair of `{}`. Unlike the `var keyword`, the variables declared with `let` and `const` can only exist within the innermost block that surrounds them.

In the following example, what do you think will be printed to the console when the code is executed.
```javascript
    let name = 'Runo';
    {
     let name = 'Tega';
    }
   console.log(name)
```
  The value `Runo` is printed to the console because the second variable `name` is not visible outside the block, it simply doesn't exist outside the block.


<h2>let & const: Similarities</h2>

In this section, we'll look at the similarities between the `let` and `const` keywords in different use cases:

###Block Scoping
We know that the `var keyword` is bound to `function scope`, whereas `let` and `const` are
`block scoped` which means that if you have a set of curly braces `{}` you have a `block scope`.

###One declaration per scope
This means that `let` and  `const` can be used to declare a particular variable only once within its scope, lets see an example to level our understanding:

```javascript
    let name = "Runo";
    let name = "Tega";
    console.log(name); //error
``` 
Same goes for `const` 
```javascript
   const name = "Runo";
   const name = "Tega";
   console.log(name); //error
``` 

<strong>Note:</strong> the `var keyword` acts differently, it allows a variable to be declared twice and then it takes the value of the most recent declaration, see the code snippet below:

```javascript
   var name = "Runo";
   var name = "Tega";
   console.log(name) // Tega
``` 
<h2>Let & const: Differences</h2>

In this section we'll look at the differences between `let` and `const` and when to use them.
###Variable initialization
`const` variables <strong>must</strong> be initialized with a value, but  `let` variables don't always require an intialization variable.

```javascript

  const a; //Syntax error

  let a;
```


###Variable reassignment

 `let` variables can be reassigned to another value, whereas `const` variables cannot. See the following:

```javascript
   let name = "Runo";
       name = "Tega";
       console.log(name) // Tega
``` 
 `const` variables <strong>cannot</strong> be reassigned, see below:

```javascript
      const pi = 3.142;
            pi = 3.14; //uncaught typeError 
```

`const` should be used to hold variables whose values remain constant throughout the program. It can be used to create variables that hold references to the DOM. 

#Summary
The `const and let` keywords support block scoping (lexical binding) and the `const` key word is used to declare variables with constant values, whereas the `let` keyword is used to declare variables whose values can change in the course of programming. The `let` keyword is a good replacement for legacy ES5 `var` keyword. 
