---
status: newBorn
related-links: 
created: 2025-05-28T10:11
updated: 2025-05-28T10:28
---
---


##### **Origin**
An origin is defined by **protocol + domain + port**.  
So these are **different origins**:

- `http://example.com`
- `https://example.com` (different protocol)
- `https://api.example.com` (different subdomain)
- `https://example.com:3000` (different port)

##### what we do using it
- in cors we set, "Yes, I allow this origin to access my resources."
- You **don’t fix CORS from the frontend**. You have to:
	- Modify the **server** to send proper CORS headers.
	- Use middleware like **`cors` in Express.js**:
```js
const cors = require('cors');
app.use(cors({
  origin: 'http://localhost:3000',
  credentials: true
}));
```
- `credentials: true` tells the browser to **include cookies, authorization headers, or TLS client certificates** in the request.
- `origin`: we can also set origin to `*` which means from anywhere
