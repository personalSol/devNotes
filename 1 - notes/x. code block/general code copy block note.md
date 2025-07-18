---
status: newBorn
related-links: 
created: 2025-05-28T04:05
updated: 2025-06-15T15:26
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



##### app.on() method
```js
;(
    async ()=> {
        try{
            await mongoose.connect(`${process.env.MONGODB_URI}/${DB_NAME}`);
            app.on("error", (error)=> {
                console.log("ERR: ", error);
                throw error;
            }) 
        } catch (error) {
            console.error("error: ", error);
            throw error;
        }
    }
)()
```

##### grid code
```html
<!DOCTYPE html>

<html lang="en">

  

<head>

    <meta charset="UTF-8">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Document</title>

    <link rel="stylesheet" href="style.css">

    <style>

        .parent {

            border: solid black 2px;

            display: grid;

            grid-template-columns: repeat(3, 60px);

            grid-template-rows: repeat(4, 40px);

            gap: 5px

        }

  

        .child {

            border: dotted blue 3px

        }

  

        #Item-7 {

            grid-row-start: 1;

            grid-row-end: 4

        }

    </style>

</head>

  

<body>

    <div class="parent">

        <div class="child">Item 1</div>

        <div class="child" id="Item 2">Item 2</div>

        <div class="child">Item 3</div>

        <div class="child" id="Item 4">Item 4</div>

        <div class="child">Item 5</div>

        <div class="child">Item 6</div>

        <div class="child" id="Item-7">Item 7</div>

    </div>

</body>

<!-- <script src="script.js"></script> -->

  

</html>
```