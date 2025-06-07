---
status: newBorn
related-links: 
created: 2025-06-06T23:26
updated: 2025-06-06T23:26
---
---

#### Q: What are route params in Express?
**A:** Route params are named URL segments prefixed with `:` used to capture values from the URL.

**Example:**  
`/users/:id` → captures the value in place of `:id`

---

#### Q: How do we define a route with params in Express?
```js
router.get('/users/:id', (req, res) => {
  const userId = req.params.id;
  res.send(`User ID is ${userId}`);
});
```

---

#### Q: What does `req.params` contain?
**A:** It's an object containing all route parameters as key-value pairs.

```js
// GET /users/42
req.params = { id: "42" }
```

---

#### Q: Can we use multiple params?
**A:** Yes.

```js
router.get('/posts/:postId/comments/:commentId', (req, res) => {
  const { postId, commentId } = req.params;
  res.send(`Post: ${postId}, Comment: ${commentId}`);
});
```

---

#### Q: Can route param values be numbers?
**A:** Yes. All route params come as **strings** by default, but you can convert them.

```js
const id = parseInt(req.params.id);
```

---

#### Q: Can we use params inside `express.Router()`?
**A:** Yes. Works same as in `app.get()`.

```js
const router = require('express').Router();

router.get('/product/:productId', (req, res) => {
  res.send(req.params.productId);
});
```

---

#### Q: How to handle routes like `/user/:id/edit` and `/user/new` separately?
**A:** Place static routes first.

```js
router.get('/user/new', ...);         // static
router.get('/user/:id/edit', ...);    // param
```

Otherwise, `new` will be treated as `id`.

---

#### Q: How to validate param (e.g., only numbers)?
**A:** Use regex in route path.

```js
router.get('/user/:id(\\d+)', (req, res) => {
  res.send(`Numeric ID: ${req.params.id}`);
});
```

---

#### Q: How to define a middleware that runs for specific param?
**A:** Use `router.param()`.

```js
router.param('id', (req, res, next, id) => {
  console.log('Called only when :id present');
  next();
});
```


