---
status: newBorn
related-links:
  - "[[npm packages for web dev]]"
  - "[[Node-JS-MOC]]"
created: 2025-05-17T14:47
updated: 2025-07-29T17:21
---
---

- for syntax: read: [[fetch vs axios]]
- axios, `withCredentials: true`, allows backend send cookies to be set in frontend site

## What is Axios?

**Axios** is a JavaScript library that helps you **make HTTP requests**—which means getting or sending data to a server. For example, getting data from an API.

---

## Why Use Axios Instead of `fetch`?

You can use JavaScript’s built-in `fetch`, but **Axios makes things easier**. Here's how, in **very simple terms**:

| Feature | `fetch` | Axios |
|--------|--------|-------|
| **Easier syntax** | Not always | ✅ Yes |
| **Handles JSON automatically** | ❌ You have to write `.json()` | ✅ Yes, auto |
| **Handles errors better** | ❌ You have to check manually | ✅ Gives clear errors |
| **Works well with older browsers** | ❌ Not supported in all | ✅ Works in more cases |
| **Cancel requests** | 🟡 Tricky | ✅ Easy |
| **Automatic timeouts** | ❌ Manual | ✅ Built-in option |

---

## Example

### With `fetch`:
```js
fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error(error));
```

### With **Axios**:
```js
import axios from 'axios';

axios.get('https://api.example.com/data')
  .then(response => console.log(response.data))
  .catch(error => console.error(error));
```

Notice: Axios skips `.json()`—it's simpler.

---

## Summary

Axios is like a **helper tool** that makes working with web requests **cleaner, simpler, and safer**, especially when your code grows more complex.



