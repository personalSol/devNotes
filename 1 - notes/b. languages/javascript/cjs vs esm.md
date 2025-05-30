---
status: newBorn
related-links:
  - "[[Node-JS-MOC]]"
created: 2025-05-28T03:44
updated: 2025-05-28T03:44
---
---

## 📥 Imports

| What You Want to Do        | CommonJS                             | ESM                                |
|---------------------------|--------------------------------------|------------------------------------|
| Import default export      | `const x = require('x')`            | `import x from 'x'`                |
| Import named export        | `const { foo } = require('x')`      | `import { foo } from 'x'`          |
| Import whole module        | `const x = require('x')`            | `import * as x from 'x'`           |
| Dynamic import             | `const x = require('x')`            | `const x = await import('x')`      |

## 📤 Exports

| What You Want to Do        | CommonJS                             | ESM                                |
|---------------------------|--------------------------------------|------------------------------------|
| Export default             | `module.exports = x`                | `export default x`                 |
| Export multiple named      | `exports.foo = foo; exports.bar = bar` | `export const foo = foo; export const bar = bar` |
| Export inline named        | N/A (not supported)                 | `export function foo() {}`         |
| Export object              | `module.exports = { foo, bar }`     | `export { foo, bar }`              |

## ⚙️ Environment & Config

| Task                       | CommonJS                             | ESM                                |
|---------------------------|--------------------------------------|------------------------------------|
| File extension             | `.js` (default)                     | `.mjs` or `.js` + `"type": "module"` |
| `package.json` config      | No special config needed            | Add: `"type": "module"`            |
| Use top-level `await`      | ❌ Not allowed                      | ✅ Allowed                         |

## ⚠️ Interop Gotchas

| From → To        | Behavior |
|------------------|----------|
| CJS importing ESM | ❌ Cannot use `require()` – must use dynamic `import()` |
| ESM importing CJS | ✅ Works, but `default` is the entire `module.exports` object |

## 📌 Example Conversion

### CJS Version
```js
// add.js
function add(a, b) {
  return a + b;
}
module.exports = add;

// index.js
const add = require('./add');
console.log(add(2, 3));
```

### ESM Version
```js
// add.js
export default function add(a, b) {
  return a + b;
}

// index.js
import add from './add.js';
console.log(add(2, 3));
```
