---
status: newBorn
related-links: 
created: 2025-06-10T17:23
updated: 2025-06-11T06:26
---
---

- there are two types of tokens:
	- access token
	- refresh token
- both are created in same way but refresh token have one or two data in payload + longer expiry
- there are two main ways to store these tokens
	- headers
	- cookies -- [[cookies]] - [[cookies syntax]]
```js
// ✅ Set headers in Express
res.header('Header-Name', 'Header-Value');

// ✅ Access header data from request
req.headers['header-name']; // or
req.headers.headername;
```

> way to remember: for access we have multiple options so we use `s` but for setting we only set one at a time so we don't use `s`. 

^3xzlbb