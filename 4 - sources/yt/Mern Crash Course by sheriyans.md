---
created: 2025-03-28T15:30:50
status: 
source: 
updated: 2025-05-28T10:37
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

