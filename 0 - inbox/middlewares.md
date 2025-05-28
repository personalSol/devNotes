---
status: newBorn
related-links: 
created: 2025-05-28T10:37
updated: 2025-05-28T12:25
---
---

there are mainly three types of middlewares:
- [[build-in middleware]]
- user defined/custom middleware
- third party middleware ( eg. morgan )

**more info on middlewares**: it needs to be stopped by returning next() function ( next need to be added in callback parameters to work )
- only after the middleware stops that another one runs
- runs for every request
##### build-in middleware

```js

// these are used to parse data for post requests

app.use(express.json())
app.use(express.urlencoded({extended: true}))
```

###### **explaination of these middlewares:**

**What do these lines do?**

They help your Express app **understand data sent by users** in requests (like forms or JSON).

---

1. **`app.use(express.json())`**

- **What it does**:  
    If someone sends your app data in **JSON format** (like from an API or a tool like Postman), this line converts that JSON into a plain JavaScript object.
    - Example: Turns `{ "name": "Alice" }` into `req.body = { name: "Alice" }`.

---

2. **`app.use(express.urlencoded({ extended: true }))`**

- **What it does**:  
    If someone submits an **HTML form** (like a login page), this line converts the form data into a JavaScript object.
    
    - Example: Turns `name=Alice&age=30` into `req.body = { name: "Alice", age: "30" }`.
- **`extended: true`**:  
    Lets you send more complex data (like nested objects or arrays).
    - Example: `user[name]=Alice&hobbies[0]=coding` becomes:
```js
req.body = {
  user: { name: "Alice" },
  hobbies: ["coding"]
}
```

---

**Why do you need both?**

- **JSON**: For apps that talk to APIs or frontends like React/Angular.
- **URL-encoded**: For old-school HTML forms (like a contact form on a website).

Without these, your app won’t understand the data users send! 🔑

---

**Simple Example**

Imagine a pizza order form:

- If you send: `toppings=pepperoni&toppings=mushrooms`,  
    `express.urlencoded` turns it into:
- `{ toppings: ["pepperoni", "mushrooms"] }`
- If you send JSON: `{ "toppings": ["pepperoni", "mushrooms"] }`,  
    `express.json` turns it into the same object.

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

##### third party middleware morgan

- morgan is used for many purposes, server according to input argument
- needs to be installed and imported
- needs to be used inside `use()` middleware

code
```js
app.use(morgan('dev'))
// 'dev' logs the request type (get/post) and status code along with the time it took to fulfill the request
```

