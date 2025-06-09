---
status: newBorn
related-links: 
created: 2025-06-04T10:28
updated: 2025-06-06T12:37
---
---

> my view: cookie is just a box which stores things. we can set cookies by res.cookie("valueName", value, options) and fetch them by req.cookies.valueName. pretty simple aye


### Q: What is a cookie?
A small piece of data stored on the client's browser, used to maintain sessions, track activity, or store temporary info.

---

### Q: Who sets and sends cookies?
- **Server** sets the cookie using the response (`res`) object via the `Set-Cookie` header.
- **Client browser** stores the cookie and sends it back automatically on every matching request.

---

### Q: How to manually set a cookie in Node.js (without libraries)?

```js
res.setHeader("Set-Cookie", "token=123456; HttpOnly; Path=/; Max-Age=3600");
```

This sets a raw HTTP header.

---

### Q: How to set cookies using Express?

```js
res.cookie("token", "123456", {
  httpOnly: true,
  maxAge: 3600000,
  secure: false
});
```

This uses Express’s built-in `res.cookie()` method.

---

### Q: What is `cookie-parser` used for?

- It is used to **read** cookies from incoming requests.
- Not required for setting cookies.

```bash
npm install cookie-parser
```

```js
import cookieParser from 'cookie-parser';
app.use(cookieParser());
```

Reading cookies:

```js
const token = req.cookies.token;
```

---

### Q: Full Express example of setting and reading cookies?

```js
import express from 'express';
import cookieParser from 'cookie-parser';

const app = express();
app.use(cookieParser());

app.get("/set-cookie", (req, res) => {
  res.cookie("token", "abc123", { httpOnly: true });
  res.send("Cookie has been set");
});

app.get("/get-cookie", (req, res) => {
  const token = req.cookies.token;
  res.send("Your token is: " + token);
});

app.listen(3000, () => {
  console.log("Server started on http://localhost:3000");
});
```

---

### 🔐 httpOnly and secure Cookie Options

---

### Q: What does the `httpOnly` option do?

- Prevents JavaScript from accessing the cookie (via `document.cookie`).
- Used to secure sensitive cookies like tokens.

```js
res.cookie("token", "abc123", { httpOnly: true });
```

---

### Q: What does the `secure` option do?

- Sends cookie only over HTTPS connections.
- Prevents leakage over insecure HTTP.

```js
res.cookie("token", "abc123", { secure: true });
```

---
