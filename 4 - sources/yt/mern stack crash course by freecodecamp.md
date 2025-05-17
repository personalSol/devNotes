---
created: 2025-02-28T19:25:59
status: newBorn
source: youtube video
updated: 2025-05-17T14:46
---
---

- to use modern import methods instead of require.
	![[Pasted image 20250228193905.png]]
- schema in mongoose:
	- are basically like columns
	- here we specify input field name, datatype, rules ( like required: true )
	- model in mongoose:
		- we store the schema here and it will create the model/collection
- save in mongoose: 
	- when we successfully get the correct data around product and we create a document of it using `const <variable> = new <imported function name>(req.body)` then we can save it using .save() method on that new product variable and send status 'res.status(201).json(any data here that we want to send)' 
- req.params
	- when we use dynamic routing, using ` url/:something` then we can access that data in url using req.params
- Methods like `findById()`, `findByIdAndDelete()`, and `findByIdAndRemove()` are Mongoose methods for MongoDB operations, not Express functions.
- .patch() & .put() http method:
	- `.patch()` http method is used when we want to change some fields and not all
	- `.put()` http method is used when we want to change all the data in fields/ means changing all the data
- HTTP response codes: 
	- 404: not found


#### get vs post

**GET Method:**

- Appends data to the URL as query parameters
- Data is visible in the URL (less secure)
- Limited data capacity (URL length restrictions)
- Requests can be bookmarked and cached
- Ideal for retrieving data
- Idempotent (repeated requests produce the same result)
- Example URL: `example.com/search?query=term&page=2`
- the search query we give on google is also a get request

**POST Method:**

- Sends data in the request body
- Data is not visible in the URL (more secure)
- Can send larger amounts of data
- Requests cannot be bookmarked and are not cached by default
- Ideal for submitting data (forms, file uploads)
- Not idempotent (repeated requests may create multiple records)
- Example URL: `example.com/submit` (with data in request body)



#### methods

**req.body** method:
- used in express post request to get the data send by user
- cannot be used in get request as it's designed in express to get datafrom post, put and other methods


#### **POSTMAN**:

- postman is actually to pass data to server when there is no front end to input data from
- so we create dummy data here which we directly send to server without any frontend

#### COmmands
- to create an app like veet in same folder ( normally it asks for project name and then create folder of that ): use `npm create vite@latest .` here . means on same folder


#### Chakra UI
---

##### snippets
---

**What are snippets?**  
Snippets are like pre-made code shortcuts. Instead of typing out a full component (like a button or form) from scratch, snippets let you insert ready-to-use code with just a few keystrokes. It saves you time!

**What does this command do?**  
When you run `npx @chakra-ui/cli snippet add`, it:

1. **Adds pre-built Chakra UI code shortcuts** to your project.
2. These shortcuts work in your code editor (like VS Code) – you type a short keyword (e.g., `Button`), and it auto-fills the full code for a Chakra UI component.

**Example:**  
Without snippets: You type out all the code for a Chakra button manually.  
With snippets: You type `cbutton` (or a similar shortcut), and it instantly gives you a styled button component.

**Why is this helpful?**

- Great for beginners: You don’t need to memorize all the component code.
- Speeds up development: Less typing, fewer errors.


##### Flex
---

to make flex responsive we use

```js-chakraUI
flexDir={{
            base: "column",
            sm: "row",
        }}
```
this makes whatever is inside appear in column format in smaller screen and in row format in bigger screens

### routing in Jsx

- for routing we use a library called `"react-router-dom"`
- also we use routes >> route tags
- we also have to wrap our app with `<BrowserRouter>` tag 
	- if there is any UI library we are using then we have to wrap it too
- attributes: 
	- path: to put path inside
	- element" tells which element/component to load at this route
- components

````tabs
--- Link

- to link something to a route

```js
<Link to={"/"}>HELLO 🛒</Link>
```

--- Tab 2
Content for tab 2
````



In js arrow function:
##### 1. **Returning an Object in an Arrow Function**

To return an object directly in a concise arrow function, use `() => ({ ... })`:

```js
const getObject = () => ({ key: "value" });
console.log(getObject()); // Output: { key: "value" }
```


### .env

- to use .env file we have to download it's package called `dotenv`
	- after that we can import dotenv in the file where we want to use values from .env
- the next step is to config, it loads the variables in that file. By default `dotenv.config()` looks for .env file in the current director from where we ran the command to execute the file. 
- if the file is not in current directory then we have to specifiy the path inside config
```js

```


### zustand

- zustand helps us in creating a global state which we can use anywhere
- it saves us from a big chain of importing that state. 
![[Pasted image 20250404141621.png]]
- also only the component that uses it have to re-render and not the parent ones which just bacame a importing medium ( matlab yaar ek se dusri file mai import krenge toh woh saari files jisme yee state thi woh re-render hogi akar state change hui, pr akar apan zustand see ek global state banayenge toh sirf wahi component re-render hoga )
- humko haar jagha pass nhi krna padega woh state as a parameterr just because child ke child ke child ko woh state use krna hai




### JSON 

- `newProduct` is likely a **JavaScript object**, like:
```js
const newProduct = { name: "Shoe", price: 49.99 };
```

- But when sending data to the server, it **has to be in text format**, specifically **JSON string**.
- So `JSON.stringify(newProduct)` turns it into:
```js
'{"name":"Shoe","price":49.99}'
```
### lesson:

- **You're sending data** to the server, but the server only understands it if it’s a string (JSON), so you **stringify** it before sending.


### doubts

- default route not working. Like I have to mention `'/', ` as default but I remember it used to work because root directory is default.
- revise async and await
- export and import: 
	- learn `import { import function name } from "location`
	- learn default export thing
- see all the comments at the end
- remember get vs post method and what they used to get used for
- learn http methods:
	- put
	- post
	- get
	- delete

- to work with es6 (modern js ) file in js
	- we can include type: "module" in package.json
	- or we can use .mjs extension instead 





# Reference
`related link(if any)`

[MERN Stack Tutorial with Deployment – Beginner's Course - YouTube](https://youtu.be/O3BUHwfHf84?si=8RcMoo29wQAa69VZ)