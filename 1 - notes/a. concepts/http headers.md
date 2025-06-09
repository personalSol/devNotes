---
status: newBorn
related-links: 
created: 2025-06-02T14:45
updated: 2025-06-09T13:11
---
---

- headers are meta data which are in key: value pair format.
- This is the data about the data or file we are sending. Yes data about data.
- It includes data like name of the file, size of the file, last time created, last time updated, etc.

Both request and response data we use in express also have header files in it. Response includes data like which thing we used to send data, was that postman, from browser, thundercloud, also errors like 404 not found, etc.

`usecase`
- caching
- authentication ( to hold tokens like session key, refresh token, etc )
- state of user ( to see if the user is a guest or logged in or if he has something in cart, etc )
- etc, etc


### Why not use body?

Even though you can use body for everything, it is a good idea to use `headers` for sending data that isn’t directly related with the `application logic`.

For example, if you want to create a new TODO, you will send the TODO payload in the body

```json
{
   description: "Go to gym"
}
```
But the `Authorization` information in the `headers`
```json
Authorization: sanskar
```

#### unofficial category of headers
---

Although there is no official category of header, Hitesh sir has made his own categories which are:

- Request header - data came from client
- Response header - from server  ( like sending code 200 for everything going okay and 404 for not found, it’s not compulsory to have 404 for not found but it’s a standard practice)
- Representation header - encoding / compression  (it’s used when we have representation data like graphs and charts)
- Payload header - data

there can be more and multiple types of headers, that depends on the source we are learning from.

#### most common headers
![[Pasted image 20250602151157.png||500]]

- these are the different types of data we send when we send different types of data
- **`Accept: application/json`** is sent by the **client** (usually the **frontend**) in a **request**.
	- It tells the **server**: “Send me the response in JSON format.”
	- The server then replies in JSON (if it supports that format).
- user-agent: tells us where we got request from like from postman or browser + OS used
- authorization: we send autherization token like `bearer: <jwt token>`

