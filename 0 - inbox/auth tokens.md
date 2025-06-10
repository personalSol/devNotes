---
status: newBorn
related-links: 
created: 2025-06-10T17:23
updated: 2025-06-10T18:12
---
---

- there are two types of tokens:
	- access token
	- refresh token
- both are created in same way but refresh token have one or two data in payload + longer expiry
- there are two main ways to store these tokens
	- headers
	- cookies -- [[cookies]]
```js
// ✅ Set headers in Express
res.header('Header-Name', 'Header-Value');

// ✅ Access header data from request
req.headers['header-name']; // or
req.headers.headername;

// ✅ Access cookies from request
req.cookies.cookieName;

// ✅ Set cookies in response
res.cookie('cookieName', 'cookieValue', { 
    maxAge: 900000, // optional: cookie expiry in ms
    httpOnly: true  // optional: cookie not accessible via client-side JS
});
```

> way to remember: for access we have multiple options so we use `s` but for setting we only set one at a time so we don't use `s`. 