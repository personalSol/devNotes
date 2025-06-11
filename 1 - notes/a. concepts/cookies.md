---
status: newBorn
related-links: 
created: 2025-06-04T10:28
updated: 2025-06-11T06:11
---
---

> my view: cookie is just a box which stores things. we can set cookies by res.cookie("valueName", value, options) and fetch them by req.cookies.valueName. pretty simple aye

- [[cookies concept]]
- [[cookie-parser]]
- [[cookies syntax]]



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


#### Q: What does the `httpOnly` option do?

- Prevents JavaScript from accessing the cookie (via `document.cookie`).
- Used to secure sensitive cookies like tokens.

```js
res.cookie("token", "abc123", { httpOnly: true });
```

---

#### Q: What does the `secure` option do?

- Sends cookie only over HTTPS connections.
- Prevents leakage over insecure HTTP.

```js
res.cookie("token", "abc123", { secure: true });
```

---
