---
status: newBorn
related-links: 
created: 2025-06-09T14:41
updated: 2025-06-09T14:41
---
---
### ✅ 1. Route Parameters (`req.params`)
- Data is part of the URL path.
- Example: `/user/:id`
- Access with: `req.params`

```js
app.get('/user/:id', (req, res) => {
  const userId = req.params.id;
  res.send(`User ID is ${userId}`);
});
```

**URL Example:**
`/user/123` → `req.params = { id: '123' }`

---

### ✅ 2. Query Parameters (`req.query`)
- Data is sent after `?` in the URL.
- Example: `/search?q=node`
- Access with: `req.query`

```js
app.get('/search', (req, res) => {
  const searchTerm = req.query.q;
  res.send(`Search term is ${searchTerm}`);
});
```

**URL Example:**
`/search?q=express` → `req.query = { q: 'express' }`

---

### ✅ 3. Request Body (`req.body`)
- Data sent in the **body** of POST, PUT, PATCH requests.
- Requires body-parser or `express.json()` middleware.

```js
app.post('/user', (req, res) => {
  console.log(req.body);
  res.send('Data received');
});
```

**Usage Example:**
Sent via Postman body or frontend form.

---

### ✅ 4. Request Headers (`req.headers`)
- Data sent in HTTP request headers.
- Common for tokens, API keys, metadata.

```js
app.get('/secure', (req, res) => {
  const token = req.headers.authorization;
  res.send(`Token is ${token}`);
});
```

**Example Header:**
`Authorization: Bearer <token>`

---

### 🚀 Summary Table

| Method         | Example in URL/Header/Body              | Access With     | Common Use                 |
|----------------|----------------------------------------|-----------------|----------------------------|
| Params         | `/user/:id` → `/user/123`              | `req.params`    | Resource identification    |
| Query          | `/search?q=node`                       | `req.query`     | Filtering, search, options |
| Body           | Sent in POST/PUT body                  | `req.body`      | Form, JSON data submission |
| Headers        | `Authorization: Bearer <token>`         | `req.headers`   | Tokens, API keys           |


