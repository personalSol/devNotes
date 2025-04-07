---
status: newBorn
related-links: []
created: 2025-04-07T10:53
updated: 2025-04-07T11:16
---
---

in any function, when we return a function. Not only the function returns but also the lexical scope  ( means scope in which variables of it's parent function and grandparents ) gets transferred too.


a usecase scenario is when we want to pass a value on onclick, we give it an executable function and return the main function inside that function.

normal way is"
```js
//color to change bg

function runThis(color){
	return function bgChanger(){
		document.body.style.backgroundColor(`${color}`)
	}
}

document.getElementById("ID").onclick() = runThis("orange")
```

in this we know that return function will get the value of color because we know sirf function nhi jata uske saath uska lexical scope bhi jata hai. 



another thing that we can do is:
```js
onclick() = (num)=> {
	return function(){
		console.log(`${num}`);
	}
}
```


# Reference
`related tags + notes + source + link(if any)`
 
- [[tG not-tagged]]
- 