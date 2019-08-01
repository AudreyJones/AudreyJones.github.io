---
layout: post
title:      "The Main Differences between JavaScript Functions: "Regular" vs "Arrow""
date:       2019-08-01 04:01:37 +0000
permalink:  the_main_differences_between_javascript_functions_regular_vs_arrow
---


So, as a student being welcomed into the wonderful world of JavaScript (as with any other language, I might add), you are re-introduced to functions, particularly the special syntax, quirks, and limitations that they come with when working in the language you are learning. In JavaScript, functions have the following basic syntax:

```
let x = function name_of_function(parameters) {
 function body, also know as a "block"
}
```

With the release of ES6 in 2015 came the new feature of Arrow Functions: a sleek and concise style of writing JavaScript functions that enables a developer to define a function as follows:

```
let x = (parameters) => {
 function body / "block"
}
```

With the "arrow" being the use of ```=>``` between the parameters and the arrow function's body. This is sometimes referred to online as a "fat arrow". 

Arrow functions do not have the usual bindings of the following keywords: ```this, arguments, super, or new```

* ```this & super keywords```: arrow functions do NOT have their own defined `this` within the enclosing lexical scope. In other words, a `this` used within the body of an arrow function refers to the same `this` as the entity carrying the arrow function itself. As for the ```super``` keyword, which is used to call functions of an object's parent, the same lexical scoping principle applies that is used with ```this```. Arrow functions with a ```super``` in their function body will apply that keyword's functionality to the parent of their enclosing lexical scope (the parent of the entity containing the arrow function itself). 

* ```arguments keyword```: arguments objects are not available in arrow functions, but are available in regular functions.



* ```new keyword```: 'Regular-style' functions are constructible, meaning that they can be called using the ```new``` keyword like so:

```
let x = function(parameters) {
       do something;
};

new x = (1,2,3);
```
Whereas arrow functions are not constructible, meaning they cannot be used as constructors and utilize the ```new``` keyword.
