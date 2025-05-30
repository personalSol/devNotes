---
status: newBorn
related-links: 
created: 2025-05-28T19:36
updated: 2025-05-30T09:45
---
---

##### Simple middleware Code

```js
// custom middleware

app.use((req, res, next)=> {
    console.log("I am a middleware");
    console.log("to run the next middleware we need to use next function");
    return next()
})
```

##### custom middleware for specific route
- we do that by including middlware just after route inside request handlers like get, post, etc

```js
app.get('/aboutus', // this is route
	(req, res, next)=> { // this is a middleware specifically for '/aboutus' route
		const a = 10, b = 5;
		console.log(a+b)
		next();
	},
	(req, res)=> {
		res.send("middleware worked successfully")
	}
)
```

