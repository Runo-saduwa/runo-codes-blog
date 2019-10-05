---
title: 4 Ways To Return Multiple Elements From A React Component 
date: "2019-09-07"
description: 

---

We can return multiple elements from a react component in 4 different ways. In this tutorial we’ll look at each of the ways this can be done and choose the cleanest and most convenient way(s) of doing this. 


### 1 - Using The traditional div element
We can easily return multiple elements from a React component by wrapping all the elements within the **div** element like so:


This works, but it adds a redundant/unwanted node to the DOM, in most cases we don’t need this, so using the div isn’t really the best option and should be avoided.

### 2 - Using An Auxiliary Higher Order Component 

> An ***Auxilliary Component*** is simply a higher order component which provides supplementary features and support to another component

An **Auxilliary Component** takes a Component and returns a new one (a modified component)

We can create a simple Auxiliary Component like this: 
> export default const Aux = props => props.children
And use it like this: 
```javascript
const customComponent = (props) => {
return (
    <Aux>
    <div>🥧</div>
    </Aux>
)
}
```
Viola!, Just by doing this we’ve successfully met the requirements of returning a single direct child from a component.

### 3 - Using Arrays To Return Multiple Elements  
We can use an array to return multiple elements from a React component, but we must ensure that we assign a unique ***key*** to each element like the following 

```javascript
const customComponent = (props) => {
return (
     [
      <div key="key1">🥧</div>,
      <div key="key2”>🍗</div>
     ]
    )
}
```

### 4 - Using React Fragments 

With the release of React v16.2.0, ***Fragments*** was introduced to React to help tackle the problem of adding extra nodes to the DOM.

***Fragments*** are just empty jsx tags, they serve as a wrapper to help return multiple `JSX` elements from a component.

To use ***Fragments***, all you have to do is to import it from ***React*** and use it.

```javascript
 import React, {Fragment} from  'react'

 const randomComponent = (props) => {
     return (
         <Fragment>
         <h2>A list of random emojis</h2>
         <div></div>
         <div></div>
         <div></div>
         </Fragment>
     )
 }
```
