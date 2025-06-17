---
status: newBorn
related-links: 
created: 2025-05-28T03:59
updated: 2025-06-16T15:25
---
---

for quick reference -- [[cjs vs esm]]
 
- in default export, we are only exporting one thing from that file
- so when we import it then we can use a different name as well if we want ( like an alias )

```js
// db.js file
export default connectDB;

// index.js file
import db from './db/db.js' // writing db instead of connectDB
```
- here we have exported only one method which is connectDB
- The name after `import` can be anything you choose when importing a default export.
- `db` is just a local variable name for the default export (`connectDB`).


## ✅ Exporting in ES Modules

There are **two ways to export:**

- **Named Export**
    
- **Default Export**
    

---

## 1. 📤 Named Export

### 🔹 A. Declaring First, Exporting Later

```js
// file: math.js
const sum = (a, b) => a + b;
const subtract = (a, b) => a - b;
const multiply = (a, b) => a * b;

export { sum, subtract, multiply };
```

#### 👉 Import:

```js
// file: app.js
import { sum, subtract, multiply } from './math.js';
```

---

### 🔹 B. Direct Export While Declaring

```js
// file: math.js
export const sum = (a, b) => a + b;

export const subtract = (a, b) => a - b;

export const multiply = (a, b) => a * b;
```

#### 👉 Import:

```js
// file: app.js
import { sum, subtract, multiply } from './math.js';
```

---

### ❌ Incorrect: `export const { something }`

```js
// ❌ This is invalid in ES Modules:
export const { sum, subtract } = obj;
// You can't export destructured variables directly.
```

#### ✅ Reason:

- You can only export variables, functions, or classes.
    
- You cannot directly export destructured variables.
    

---

## 2. 📤 Default Export

### 🔹 A. Declaring First, Exporting Later

```js
// file: logger.js
function log(message) {
    console.log(message);
}

export default log;
```

#### 👉 Import:

```js
// file: app.js
import log from './logger.js';
```

---

### 🔹 B. Direct Export While Declaring

```js
// file: logger.js
export default function log(message) {
    console.log(message);
}
```

#### 👉 Import:

```js
// file: app.js
import log from './logger.js';
```

---

## 3. 📤 Mixed Export (Named + Default)

```js
// file: utils.js
export const greet = () => console.log("Hello");

export const sum = (a, b) => a + b;

export default function log(message) {
    console.log(message);
}
```

#### 👉 Import:

```js
// file: app.js
import log, { greet, sum } from './utils.js';
```

---

## ✅ Quick Summary Table

|Export Type|Syntax (Export)|Syntax (Import)|
|---|---|---|
|Named (Declare First)|`export { sum, subtract }`|`import { sum, subtract } from './file.js'`|
|Named (Direct Export)|`export const sum = () => {}`|`import { sum } from './file.js'`|
|Default (Declare First)|`export default log`|`import log from './file.js'`|
|Default (Direct Export)|`export default function log() {}`|`import log from './file.js'`|
|Mixed Export|`export const greet = ... export default log`|`import log, { greet } from './file.js'`|

---

## 🚫 Important Rules:

- ❌ **You cannot write:** `export const { something } = obj;`  
    Exporting destructured variables directly is invalid.
    
- 🔹 **File extension is mandatory** in import: `./file.js`
    
- 🔹 ES Modules **do not support `require` or `module.exports`**
    
- 🔹 For Node.js:
    
    - Use `"type": "module"` in `package.json`
        
    - Or use `.mjs` file extension