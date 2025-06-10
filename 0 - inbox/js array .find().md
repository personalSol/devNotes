---
status: newBorn
related-links: 
created: 2025-06-10T10:54
updated: 2025-06-10T10:54
---
---
### What is `.find()`?
The `.find()` function in JavaScript is used to **search for the first element in an array that matches a specific condition.**

---

### Syntax
```javascript
array.find(callback)
```
- **callback:** A function that returns `true` for the element you want to find.

---

### Key Points
- ✅ **Returns the first matching element.**
- ❌ If no match is found, it **returns `undefined`.**
- 🔍 It **does not return an array**. It returns a **single element.**
- 🛑 Stops as soon as it finds a match.

---

### Example 1: Simple Array
```javascript
const numbers = [10, 20, 30, 40];

const result = numbers.find((num) => num > 15);

console.log(result); // Output: 20
```
👉 It found the **first number greater than 15**, which is `20`.

---

### Example 2: Array of Objects
```javascript
const users = [
    { id: 1, name: 'John' },
    { id: 2, name: 'Jane' },
    { id: 3, name: 'Mike' }
];

const user = users.find((u) => u.id === 2);

console.log(user); // Output: { id: 2, name: 'Jane' }
```
👉 It found the **user with id 2.**

---

### Quick Summary
| Feature              | Description              |
|---------------------|---------------------------|
| Returns              | First matching element    |
| Return if not found  | `undefined`               |
| Stops at             | First match               |
| Changes array?       | No                        |


