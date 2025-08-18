---
status: newBorn
related-links: 
created: 2025-07-21T12:22
updated: 2025-07-21T12:22
---
---

### JavaScript Hoisting

---

#### 🔼 What is Hoisting?

Hoisting is JavaScript's behavior where **variable declarations** are moved to the **top of their scope** (before code is executed).  
> It feels like variables are moved to the top, but actually, JavaScript **allocates memory first** before running the code.

---

#### 🧠 Why Hoisting Happens

JavaScript runs in **two phases**: for detailed explanation - [[js execution context]]

- **Creation Phase** (Memory Allocation Phase):
	- JS engine scans the code.
	- Allocates memory for:
		- Variables declared with `var`, `let`, `const`
	- **Only `var` is initialized to `undefined`**
	- `let` and `const` are hoisted but kept in the **Temporal Dead Zone (TDZ)** — they're declared but not initialized yet.

- **Execution Phase**:
	- Code runs line by line.
	- Assignments, logic, and function calls happen now.

---

#### 🔄 Why It Feels Like Variables Are "Moved to Top"

Because during the **creation phase**, JS already allocates memory for variables before any code runs.  
This gives the illusion that declarations are moved to the top.

---

#### 🧪 Example of `var` Hoisting

```js
console.log(a); // undefined
var a = 10;
```

Internally becomes:

```js
var a;           // hoisted and initialized to undefined
console.log(a);  // undefined
a = 10;
```

---

#### ❌ Example of `let` / `const` Hoisting

```js
console.log(b); // ReferenceError
let b = 5;
```

- `b` is hoisted but not initialized.
- Accessing `b` before its declaration causes a **ReferenceError** due to the TDZ.

