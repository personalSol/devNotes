---
status: newBorn
related-links:
  - "[[Java-MOC]]"
created: 2025-02-21T10:55
updated: 2025-02-25T18:14
---
---

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

### a | connecting to html




### b | Variables

```javascript
var oldVariable = "function-scoped"; // Avoid in modern JS
let changeable = "block-scoped";
const constantVal = "block-scoped, cannot be reassigned";
```


### Comments:



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
 
