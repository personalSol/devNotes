---
status: newBorn
related-links:
  - "[[Express-MOC]]"
created: 2025-05-17T10:48
updated: 2025-05-21T13:08
---
---

- `express.static()` -- for more detail: [[express static method]]
    - The `static` method in Express is used to serve static files, like images, CSS files, JavaScript, and HTML files, directly from a specified folder
    - useful for web applications that need to serve frontend assets to clients.
    - basically helps us handle browser requests for static file
    ```jsx
    app.use(express.static(path.join(__dirname, "public")));
    ```
- app.on() 
	- Used to **listen for events** on an `EventEmitter` (like an Express app or HTTP server).
	- Syntax: `app.on('eventName', callback)`
	- the below one catches error and return them
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


# Reference
`related tags + notes + source + link(if any)`
 

- 