---
status: newBorn
related-links: 
created: 2025-06-10T05:53
updated: 2025-06-10T06:21
---
---

- fetch have get method set by default. in axios we need to tell the method
- in fetch we have to attach another object to change method, in axios we can directly change it
```js
fetch('https://api.example.com/data', {
  method: 'POST',                      // method
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ name: 'John' }) // request body
});


const response = await axios.put('https://jsonplaceholder.typicode.com/todos/')
console.log(response.body.length);
```
- in fetch we have to take care of the type of data we are recieving like if we are receiving json then we use `.json()`, if we are receiving text then `.text()` but axios handles it for us
- in fetch we give method, data and header in same big object separated by small objects but in axios we give data in 2nd object and header in 3rd object
- we can't send body in a get request so in axios 2nd argument automatically becomes header
- we can also use axios directly without using `.get or put or post` or anything and then we can use one single object to send everything + data will be in data key of object
```js
// Send a POST request
axios({
  method: 'post',
  url: '/user/12345',
  data: {
    firstName: 'Fred',
    lastName: 'Flintstone'
  },
  headers: {
	  authorization: "Bearer 123"
  }
});
```

