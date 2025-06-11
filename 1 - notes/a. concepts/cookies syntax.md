---
status: newBorn
related-links: 
created: 2025-06-11T06:13
updated: 2025-06-11T06:27
---
---

```js
// ✅ Access cookies from request
req.cookies.cookieName;

// ✅ Set cookies in response
res.cookie('cookieName', 'cookieValue', { 
    maxAge: 900000, // optional: cookie expiry in ms
    httpOnly: true  // optional: cookie not accessible via client-side JS
});

// to clear cookies
req.status(200)
.clearCookie("accessToken")
```

![[auth tokens#^3xzlbb]]