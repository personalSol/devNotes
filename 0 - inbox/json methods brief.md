---
status: newBorn
related-links: 
created: 2025-06-09T15:40
updated: 2025-06-09T15:40
---
---

### 1. JSON.stringify()

- Converts a JavaScript object/value into a JSON-formatted string.
- Used to prepare JS objects for sending over networks or saving as text.
- Example:

```js
const obj = { name: "Alice", age: 25 };
const jsonString = JSON.stringify(obj); 
// jsonString: '{"name":"Alice","age":25}'
```

---

### 2. JSON.parse()

- Converts a JSON-formatted string back into a JavaScript object/value.
- Used to convert received JSON strings into usable JS objects.
- Example:

```js
const jsonString = '{"name":"Alice","age":25}';
const obj = JSON.parse(jsonString);
console.log(obj.name); // "Alice"
```

---

### 3. .json() method

- Has two main contexts:

  **a. Fetch API (browser):**

  - `response.json()` reads the HTTP response stream and **parses JSON asynchronously**.
  - Returns a Promise that resolves to a JS object.
  - Example:

  ```js
  fetch('https://api.example.com/data')
    .then(response => response.json()) // parses JSON string to JS object
    .then(data => console.log(data));
  ```

  **b. Express.js:**

  - `res.json()` is a method to **send** a JavaScript object as a JSON HTTP response.
  - Example:

  ```js
  app.get('/user', (req, res) => {
	    res.json({ name: "Alice", age: 25 }); // sends JSON response
  });
  ```

---

### 4. express.json()

- Express built-in **middleware** that **parses incoming JSON request bodies** into JS objects.
- Makes parsed data available on `req.body`.
- Needed to handle JSON data sent by clients in POST/PUT requests.
- Example usage:

```js
const express = require('express');
const app = express();

app.use(express.json());  // Middleware to parse JSON bodies

app.post('/user', (req, res) => {
  console.log(req.body); // Parsed JS object from JSON payload
  res.send('User data received');
});

app.listen(3000);
```

---

