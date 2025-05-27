---
status: newBorn
related-links: 
created: 2025-05-28T03:59
updated: 2025-05-28T03:59
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
