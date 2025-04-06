---
created: 2025-03-28T15:30:50
status: 
source: 
updated: 2025-03-30T20:54
---
---


### Files

- `package.json`: file is for developers to see details around project + dependencies
- `package-lock.json`: is for system to lock the version of dependencies which are being used


### js import and export ways

1. old
```js
const <name> = require('<module_name>')
```
1. new ( for module js )

### modules that come by default with node
- `http`

---
> above stuff is like prerequisite
> below stuff is imp


### template engine

- ejs is the one we use. Simplest
- need to install as a package
- doen't need to require but declare in file that we are using ejs as template engine


### http

**http functions:**
- .createServer() : takes callback in parameter and creates a server
- .listen: start the server to listen for request

````tabs
--- req func + properties
- `req.url`: gives url

--- res func + properties
- `res.end`: ends the response ( can't send any response after this)
````


##### basic http server:
```js
const http = require('http');

const server = http.createServer((req, res) => {
    console.log(req.url);

    if(req.url === '/'){
        res.end("Home Page");
    }
    else if(req.url === '/about'){
        res.end("About Page");
    }
    else if(req.url === '/Contact'){
        res.end("Contact Page");
    }
    else{
        res.end("Hello")
    }
})

server.listen(3000, ()=>{
    console.log("Server started");
})
```




### middleware

there are mainly three types of middlewares:
- build-in middleware
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

### express

- first we need to install it
- then we need to require it to import it
- then it comes as a package and to make it start working we run it and store it in app

##### express functions

- `app.set()`: use to set something in express
	- ex: `app.set('view engine', 'ejs')`
- `app.use()`: use to set middleware, takes callback function
- `app.get()`: use to handle get requests in express, also takes callback
- `app.post()`: use to handle post requests in express, takes callback
- `app.listen()`: use to start the server

##### req and res functions and parameters

````tabs
--- req
Content for tab 1

--- res

- `res.send()`: just like .end() in http. 
	- can't send response after this
	- also sets status code while response
- `res.render()`: put file name inside it without extenstion as we would have already set ejs as template engine
	- renders ejs and show it to user
	- ends the response
````


##### get and post method

````tabs
--- get
- shows data in url
- we get data in middleware in express with req.query
- doesn't need to be parsed

--- post
- doesn't show data in url
- we get data in middlware in express with req.body
- need to be parsed 
````


# imp stuff


(confirmed)

- get is mostly used to send data from server to user
- post is used to send data from user to server

( what I think )
- when data send through get method then we don't need to use url encoded because it's in simple format
- when data is send through post method then we use url encoded to decode data that we got through post method 


# Reference
`related link(if any)`

