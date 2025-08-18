---
status: newBorn
related-links: 
created: 2025-05-29T11:44
updated: 2025-05-29T12:31
---
---

#### Purpose of `asyncHandler`

The **main purpose** of your `asyncHandler` function is to **automatically wrap your asynchronous route handlers with a `try...catch` block**, so you don’t have to manually write `try...catch` in every async function inside your Express routes.

> boleto apne ko apne route handler ko baar baar try and catch se wrap naa krna pade uske liye iss wrapper function ka use krte. yee apne liye error bhi handle krleta

- `asyncHandler` expects **to receive an async function** (or at least a function returning a promise)
- async handler syntax and explanation - [[asyncHandler syntax and explaination]]


---

##### Example without `asyncHandler` (repetitive `try...catch`):

```js
router.get('/users/:id', async (req, res) => {
  try {
    const user = await User.findById(req.params.id);
    res.json(user);
  } catch (err) {
    res.status(500).json({ error: err.message });
  }
});
```

##### Example with `asyncHandler` (simpler):

```js
router.get('/users/:id', asyncHandler(async (req, res) => {
  const user = await User.findById(req.params.id);
  res.json(user);
}));
```
