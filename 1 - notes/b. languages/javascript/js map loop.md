---
status: newBorn
related-links: 
created: 2025-05-23T09:02
updated: 2025-06-09T17:38
---
---
##### .map() loop
- `<array>.map` : used to iterate arrays
- transforms (updates) the array 
👉 **Whatever you return becomes the new value in the array.**  
✔️ You _transform_ each item.

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