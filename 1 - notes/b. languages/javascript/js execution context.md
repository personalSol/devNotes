---
status: newBorn
related-links: "[[JS-MOC]]"
created: 2025-05-25T18:20
updated: 2025-05-26T08:51
---
---

GEC ( global exeution context): means the sequence in which code will execute

GEC have 2 phrases:
1. Variable phrase
	- in this phrase the stack gets created
		- he first stack is global which is for global variables
		- second is script stack which is for block for that script
		- third it creates block which gets created for every `curly braces or {}`
	- this phrase only initalises the variable and not declare it
	- the initialized variables gets inside Temporal dead zone under which that variable is not accessible
	- funny thing is that if there is a block of code and it need to access a variable then it looks for that variable in it's own scope and if it's not find then it will look at script level and then at global level
	- but but but, if you have declared that variable inside that block as well but you have accessed it before it got declared in execution phrase then it will produce an error
	- NOTE: during variable phrase, it creates a block/stack for that `block {}` only and only if that block have let or const initializations. 
	- like in code below:
```js
console.log("start");
let a=10;
{
    console.log(a)
    let a=10;
}
console.log(a);
console.log(b);
console.log("end")
```

---

actually during V.P if it sees a variable getting initialized then it creates a block and name it after that variable. which gets filled during execution phrase 

---

all the variables which are declared by var gets declared in global scope and it doesn't get temporal dead zone. but the variable doesn't get declared too. it stores undefined and then during Execution phrase it stores the value and until then it's undefined. 

2. Execution phrase

after variable phrase gets completed. It starts execution phrase in which it executes the code, process things, log things, and also all the temporal zones get removed and variables get declared. 

> imp: when a variable is not initialized with anything like var, let or const and directly declared. then that variable gets automatically declared in global scope for that program and it functions exactly like var. 

```js
let a = 10;
b = 20; // here b will get stored in global block with auto global
console.log(b)
```

now the question is:
```js
let a = 10;
b = 20;
var b = 20;
```

here b is declared again with var

```js
console.log("start");
var b = 20;
const c = 30;

{
	a = 100;
	console.log(a);
	console.log(b);
	console.log(c)
}

var a = 10;

console.log(a);
console.log(b);
console.log(c);
console.log("end");
```
