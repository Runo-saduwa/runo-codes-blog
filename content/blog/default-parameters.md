---
title: Default Function Parameters (ES6)
date: "2019-08-31"
description: Learn about the one of the ES6 feature that helps us to write better code.
---


In the ES5 days, to set default values you might write your code in this manner:


```javascript
function getSum(a, b){
 a = (a !== undefined) ? a:1;
 b = (b !== undefined) ? b:41;
 return a + b;
}
 getSum() //42
 getSum(1,2) //3
```
or

```javascript
function getSum(a, b){
 a = a || 1;
 b = b || 41;
 return a + b;
}
 getSum() //42
 getSum(1,2) //3
```
These are good solutions, but hey it's 2019, Modern JavaScript is here to rescue us from this long walk. Now, you can set default values to the parameters in the function declaration statement itself like so:

```javascript
function getSum(a = 1, b = 41){
 return a + b;
}
 getSum() //42
 getSum(1,2) //3
```
If you don't specify an argument, the default value of the parameters gets used. 

Compared to the older methods of setting default values, this new feature provided by ES6 is easier and much cleaner.

Happy Coding!❤

