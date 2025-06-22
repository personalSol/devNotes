---
status: newBorn
related-links: 
created: 2025-06-21T01:33
updated: 2025-06-21T01:33
---
---

### Arrow Function Notes

- **Implicit Return:**
  - If the function has only one expression, you can omit `{}` and `return` keyword.
  - Example: `const add = (a, b) => a + b;`

- **Block Body:**
  - If you use `{}`, you must explicitly use the `return` keyword.
  - Example: `const add = (a, b) => { return a + b; }`

- **Returning Objects:**
  - To return an object directly from an arrow function without using `return`, wrap the object in `()`.
  - Example: `const getUser = () => ({ name: "John" });`

- **Why Parentheses?**
  - Without `()`, JavaScript thinks `{}` is a function block, not an object.
  - Example: `const getUser = () => { name: "John" };` // This will not work.

---

### Arrow Function Code Examples

```js
// Implicit Return Example
const add = (a, b) => a + b; // Single expression, no braces, no return keyword

// Block Body Example
const add = (a, b) => { // Using braces requires explicit return
    return a + b;
}

// Returning Object (Correct Way)
const getUser = () => ({ // Parentheses tell JS this is an object, not a block
    name: "John"
});

// Returning Object (Incorrect Way)
const getUser = () => { // Without parentheses, JS thinks this is a block, not an object
    name: "John"
}; // This will return undefined

```

