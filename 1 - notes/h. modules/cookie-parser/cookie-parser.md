---
status: newBorn
related-links: 
created: 2025-05-28T21:03
updated: 2025-06-11T06:13
---
---

> ✅ **To read (parse) cookies sent by the client in the HTTP request header** and make them easily accessible in your Express app via `req.cookies`.

`cookie-parser` is a middleware used to **parse cookies** attached to the client request object. It makes it easy to read cookies sent by the browser.

### What It Does:

- Parses `Cookie` header in incoming requests.
- Populates `req.cookies` with an object keyed by the cookie names.
- Not required for setting cookies.
- If a **secret** is provided, it can also parse **signed cookies** and populate `req.signedCookies`.


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

```js
const express = require('express');
const cookieParser = require('cookie-parser');

const app = express();

// Use cookie-parser middleware
app.use(cookieParser('mySecretKey'));

app.get('/', (req, res) => {
  // Access cookies
  console.log(req.cookies);
  console.log(req.signedCookies);
  
  res.send('Check your cookies!');
});
```
