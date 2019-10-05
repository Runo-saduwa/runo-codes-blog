---
title: ES6 Rest and Spread Operators
published: true
description: Introduction to rest and spread operators in modern JavaScript.
---

<img src="https://thepracticaldev.s3.amazonaws.com/i/wwnx9xpy59s885qq1a72.png">

ES6 added a lot of cool features to JavaScript. The `Rest` and `Spread` operators are powerful new features that allow us to access and manipulate data easily.

The word `Rest` here simply means <em>gathering up parameters and putting them all into a <strong>single array</strong></em>.


Also, the word `Spread` refers to <em><strong>spreading</strong> out the elements of an iterable (arrays, objects and strings).</em>

They both make use of the <em>three dots</em> `...` but apply it differently to suit their purpose. 


In this post, we'll learn about the `Rest` and `Spread`  operators, how to use them and when to use them.


<h3>Table of Content:</h3>
<ul>
<li>Rest Operators</li>
<li>Spread Operators</li>
<li>Summary</li>

</ul>

#Rest Operators

As we stated earlier, The `Rest` operators gather up parameters and put them all in a single array.

It makes use of the `...` symbol which precedes a named parameter that will become an array that will just gather up the <em>remaining</em> parameters passed to a function. See the following example: 

```javascript
  function showNames(...names){
   console.log(names);
}

 showNames("Runo","Tega","Ejiro") // ["Runo","Tega","Ejiro"]
```
In the example above, the `rest parameter` is `names` which is preceded by a `...` to denote that `names` is indeed a `rest parameter`. When the function is invoked the console prints the value of `names` as `["Runo","Tega","Ejiro"]` which is an array created by <em>gathering</em> all the arguments passed into the, into the `showNames` functions. 

####When You Should Use the <em>Rest Operators </em>

The `rest operators` can be very useful when you need to create function definitons that can accept unlimited number of parameters, let's see an example: 

```javascript 
 function add(a, b){
   return console.log(a + b);
}
add(1,2); // 3
add(1, 2, 3, 4, 5); //3
```
The first function call, `add(1,2)` returns 3. This is quite normal and straight forward, but what if you needed to pass in more arguments to your function to help you add more than 2 parameters?

After invoking the next `add` function which is `add(1, 2, 3, 4, 5)` we'll still get `3` because in JavaScript you can call a function with any number of arguments but the number of arguments that will be used depends on the number of parameters specified in the function definition.

In this case, only 2 parameters are specified. Hence, Javascript picks up the first 2 arguments.

####Rest parameters to the rescue

With the `rest parameters` we can gather any number of arguments into an array and do whatever you want with them. We can use array methods like higher-order functions like `forEach(), map(), reduce()`. 

 
Using rest parameters, we can rewrite the add function like this:

```javascript
function add(...rest){
  let total = 0;
  rest.forEach(num => total += num);

return console.log(total);
}

add(1,2); //3
add(1, 2, 3); //6
add(1, 2, 3, 4, 5, 6);//21

```
By doing so, we have succeeded in making our function flexible and adaptable to accept as much arguments as possible because the rest parameter will gather them up in an array and we make good use of the `forEach()` method to iterate over each element in the array add it to the `total` variable.

<strong>Note:</strong> If you need to specify a parameter (or parameters) alongside a `rest parameter`, ensure that the rest parameter is <strong>last</strong> in your function definition.

```javascript
function allNames(name1, ...name2, name3){
console.log(name2); // Error!
}

allNames("Runo", "Tega", "Ejiro", "Simi", "Gare");
```
Please DON'T DO this, it doesn't make any sense to JavaScript. The `rest parameters` job is to gather the excess arguments that will be passed into a function. This function should be rewritten like so: 

```javascript
function allNames(name1, name2, ...name3){
console.log(name2); // Tega
console.log(name3); // ["Ejiro", "Simi", "Gare"];
console.log(name3.length); // 3
}

allNames("Runo", "Tega", "Ejiro", "Simi", "Gare");
```
It's also important to know that the `length property` of functions ignores the `rest parameters`, lets see what we'll get if we try to find the length of the `allNames` function: 

```javascript
function allNames(name1, name2, ...name3){
console.log(name2); // Tega
}

console.log(allNames.length) // 2
```

#Spread Operators

The `spread operator` simply does the opposite of what the rest operator does, it <em>unpacks</em> an array.

The `spread operator` can be used with other iterable data types like strings and objects.

The `spread operator` is applied in the following scenarios:

###When you need to copy an array

```javascript
 let arr = ["a", "b", "c"];
 let newArr = [...arr];

 console.log(newArr) // ["a", "b", "c"]
```
Its that's easy, all you need to do is to add a preceding  `...` to an existing array and it simply removes all the values from the array.

###Adding array elements to another array

```javascript
const arr = ["a", "b"];
const newArr = [...arr, "c", "d"];
console.log(newArr) //["a", "b", "c", "d"]
```
The values of `arr` is transferred to `newArr`.

###Splitting Strings

```javascript
 let name = 'Runo';
 console.log(...name) // 'R' 'u' 'n' 'o'
```

###Merge Objects

```javascript
 const obj1 = {
       name: "Runo"
}

const obj2 = {
       age: 19
}

const obj3 = {
     ...obj1,
     ...obj2
}

console.log(obj3) // {name: "Runo", age: 19}
```

#Summary

The `rest operator`stores the remaining data passed into a function in an array. In other words, it creates a new array. On the other hand, The `spread operator` simply works with an <strong>existing</strong> array or iterable like strings and objects, It's commonly used in modern frameworks like `ReactJs`to copy data from `state`. 

I hope this helps someone, H