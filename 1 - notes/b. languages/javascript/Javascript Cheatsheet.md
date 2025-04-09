---
status: newBorn
related-links:
  - "[[Java-MOC]]"
created: 2025-02-21T10:55
updated: 2025-04-07T15:41
---
---

# -1 | remember

- variable
	- variable functions can't be accessed or called before they are initialized but normal function can be
		- variable functions will return ReferenceError if tried to access before initialization
	- in gec, first creation phrase ( aka variable phrase or memory phrase ) first declares all the variable 
	- let variable can be initialized and delcared in differnt places
	- const variable must be declared when initialized ( as it's value can't be changed )
	- let and var after initialization until declaration have undefined as value
	- var can be declared again 
- typeof
	- we can check by `console. log(typeof <variable>)`
	- null is a type of object


# 0 | Basics

- comments
	`/* Multi line comment */
	// One line`
- connecting to html
	- inside the body at the very end
		`<script src="filename.js"></script>`
	- in head tag but will have to use the `defer` or `async` attributes
		`<script type="text/javascript"> .... </script>`
- strict mode
	- "use strict"; // Use strict mode to write secure code
	- x = 1; // Throws an error because variable is not declared
- No direct support for negative indexing, but methods like `slice()` and `at()` allow negative indices to access elements from the end.




### a | Variables

```javascript
var oldVariable = "function-scoped"; // Avoid in modern JS
let changeable = "block-scoped";
const constantVal = "block-scoped, cannot be reassigned";
```

- var
    - can be declared again
    - doesn’t follow block scope
- `let` makes the variable dynamic, which can change datatype and value both.
- const: any variable initialized using this can’t change it’s value and it’s constant now

```jsx
const a = 1000;
let b = "Sanskar";
var c = "trash";
name1 = "deep";

name1 = "Harkirat"; // here name1 is declared in global form.

var c = "Sakura is trash" // [var variables] can be declared with same name again

// let b = 456; let variable can't be declared with same name again.

console.log(c);

```



# functions

```javascript

function addNumbers(a, b) {
return a + b; ;
}
x = addNumbers(1, 2);

function classicFunc(a, b = 0) { return a + b; }
const arrowFunc = (a, b) => a + b;
const IIFE = (function() { /* ... */ })();

```


# Objects

```javascript
const obj = { 
  key: "value",
  method() { /* ... */ }
};
const arr = [1, "two", false];
```


# DOM

### a | fetching element

- first we catch element using it
- then we perform operation on that element

```javascript
const a = document.querySelector("Input"); // fetches the first input element it gets
const a = document.querySelector("#Input"); // fetched element with 'Input' ID
const a = document.querySelector(".class"); // fetches first element of that class
const a = document.querySelectorAll(".class"); // fetches all elememts of that class
```

```javascript



document.getElementById("elementID").innerHTML = "Hello World!";

```

### b | delete element


### c | updating element


### d | adding element


# [[JS Events]]


![[JS Events#^j3wtkf]]
# Reference
`related notes + source + link(if any)`
 
