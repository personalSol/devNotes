---
status: newBorn
related-links: 
created: 2025-05-28T04:05
updated: 2025-05-28T04:05
---
---

##### export in cjs
```js
function wait1(t) {
    
}

function wait2(t) {
    
}

function wait3(t) {
    
}

function calculateTime(t1, t2, t3) {
    
}

module.exports = calculateTime;
```

##### to export multiple things in cjs
```js
// Option 1: Export multiple properties as an object
module.exports = { first: a, second: b };

// Option 2: Export an object with more descriptive keys
module.exports = {
    handler: requestHandler, // requestHandler is a function
    someText: "Here is some hard coded text",
};

// Option 3: Add properties to module.exports one by one
module.exports.handler = requestHandler;
module.exports.someText = "Here is some hard coded text";

// Option 4: Using `exports` as a shortcut (only works with dot notation)
exports.handler = requestHandler;
exports.someText = "Here is some hard coded text";
```