---
title: Introduction to CSS
date: "2019-10-02"
description: 
---

## What is CSS?

***CSS*** stands for ***Cascading Stylesheets*** and not ***Cannot Stand Shit***, Okay now i know that wasn't necessary but i bet it will help you remember (i hope).  

***CSS*** is used for **presentation**. It's a style sheet language used for describing the presentation of a document written in a markup language like ***HTML***. ***CSS3*** is the latest specification of ***CSS***, It is made up of different modules for different features added to the language. 

At its simplest, CSS is what developers use to make websites beautiful or presentable. A website like [Scotch](http://scotch.io) will not be as beautiful as it looks now without ***CSS***. 

## Why we need to learn CSS

To become an exceptional Frontend developer or Fullstack developer, you need to learn ***CSS***. 
With a good understanding of ***CSS***, you will be capable of implementing any design and bring any awesome User Interfaces (UIs) to life.

The rise of JavaScript and its cool frameworks has made alot of developers to neglect learning ***CSS*** properly. ***CSS*** is easy to get started with and also very easy to get frustrated with if you lack a solid understanding.

You need to spend quality time to learn ***CSS*** to avoid mediocrity.


## Tools used to write CSS

You don't need a spaceship to write ***CSS***, all you need is a text editor or IDE like ***Sublime Text or Atom or Visual Studio Code (VsCode)***
 
I love ***Visual Studio Code*** because i think its the best.

## What you need to learn before CSS

You need to know ***HTML***. It will be pointless to learn  ***CSS*** without the knowledge of ***HTML*** because ***CSS*** is used to style ***HTML***.


## How to include CSS to a HTML file


* ***External Style Sheet*** - You can include ***CSS*** to a ***HTML*** document with the `link` element. Create a seperate file with `.css` extention and add the file path as the `href` value.
```html
<!DOCTYPE html>
<html>
<head>
 <title>Intro to CSS</title>
<link href="style.css" rel="stylesheet">
<!-- always include the rel attribute!!! -->
</head>
   <body>
      <!-- HTML ELEMENTS -->
   </body>
</html>
```

* ***Embedded Style*** - You can style any element in the ***HTML*** document with the `style` attribute.

```html
<!DOCTYPE html>
<html>
<head>
 <title>Intro to CSS</title>
 <style>

 </style>
</head>
   <body>
      <p style="color: black">Lorem Ipsum</p>
   </body>
</html>
```


* ***Inline Styles*** - You can also include ***CSS*** to an ***HTML*** Document with the `style` element.
```html
<!DOCTYPE html>
<html>
<head>
 <title>Intro to CSS</title>
 <style>
    /*CSS code goes here**/
 </style>
</head>
   <body>
      <!-- HTML ELEMENTS -->
   </body>
</html>
```

***Note:*** *Using external style sheets is a best practice.*










