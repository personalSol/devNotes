---
status: newBorn
related-links: []
created: 2025-04-25T16:00
updated: 2025-06-03T12:32
---
---
	

#### array methods
---
- `<array>.map` : used to iterate arrays 
**Syntax:**
```js
array.map(function(currentValue, index, array) {
  // return the new value
});
```

```js
const myNumers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

// const newNums = myNumers.map( (num) => { return num + 10})

const newNums = myNumers
                .map((num) => num * 10 )
                .map( (num) => num + 1)
                .filter( (num) => num >= 40)

console.log(newNums);
```

- [[js array .some()]]
- 


# Reference
`related tags + notes + source + link(if any)`
 

- 