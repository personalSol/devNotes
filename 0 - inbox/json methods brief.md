---
status: newBorn
related-links: 
created: 2025-06-09T15:40
updated: 2025-06-10T17:15
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

  - `response.json()` reads the HTTP response stream and **parses JSON asynchronously**. So need to use await.
  - Returns a Promise that resolves to a JS object.
✅ What `fetch(...).then(res => res.json())` Does:
- Sends a **network request**.
- `res.json()`:
    - Parses the **JSON response body**.
    - Converts it into a **JavaScript object** or **array**, depending on what the server sends.

|JSON from Server|`res.json()` returns|Can use `.length`?|
|---|---|---|
|`[ {...}, {...} ]` (Array)|Array of objects|✅ Yes|
|`{ key: value }` (Object)|JavaScript object|❌ No (use `Object.keys(obj).length`)|

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

- Express built-in **middleware** that 
	- takes json data
	- **parses incoming JSON request bodies** into JS objects.
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

