---
status: newBorn
related-links:
  - "[[JS-MOC]]"
created: 2025-05-21T12:41
updated: 2025-06-03T12:58
---
---


## JavaScript `throw` – Q&A Notes with Code


### ❓What does `throw` do?

**✅** It stops execution and passes the error up the stack.

```js
throw new Error("Something went wrong");
```

---

### ❓Are we storing the object?

**✅** No. `new ApiError(...)` creates it, `throw` sends it.

```js
throw new ApiError(400, "All fields required");
```

---

### ❓What if `throw` is inside `try`?

**✅** It’s caught by `catch`.

```js
try {
  throw new Error("Oops");
} catch (err) {
  console.log(err.message); // "Oops"
}
```

---

### ❓What if there's no `try...catch`?

**✅** It crashes.

```js
function test() {
  throw new Error("Uncaught!");
}
test(); // Program stops
```

---

### ❓Can we re-throw inside `catch`?

**✅** Yes, after handling.

```js
try {
  throw new Error("First");
} catch (err) {
  console.log(err.message);
  throw err; // Re-throws
}
```




- `throw error` in a `catch` block **rethrows** the error after optional handling (like logging).
- It allows the error to **propagate up** to another `try...catch` or global handler.
- If you **don't throw**, the error is considered handled and won't bubble up.
- ✅ **Correct syntax**: `catch (error) { ... }`
- ❌ **Wrong syntax**: `catch { (error) => { ... } }` (invalid function syntax)
- Use rethrowing when you **log or partially handle** the error but can't fully resolve it.

