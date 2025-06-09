---
status: newBorn
related-links:
  - "[[JS-MOC]]"
created: 2025-05-17T14:38
updated: 2025-06-09T17:45
---
---

It **seems** like `fetch` is only for _getting_ data, but actually...

##### 🤯 `fetch` can do both:

- ✅ **Get** data (with `method: "GET"`, which is the default)
- ✅ **Send** data (with `method: "POST"`, `"PUT"`, `"DELETE"`, etc.)

---
##### 🔧 Think of `fetch` like:

> A tool that talks to the server.  
> Depending on what you _tell it to do_, it can either:

- Ask for data
- Or send data

---

example:

```js
fetch("/api/products", {
  method: "POST",
  ...
})
```

You're saying:

> "Hey server, I want to **send** you a new product!"

---

🧠 So:
- `fetch()` = way to talk to a server
- `method: "POST"` = "I'm sending something!"


