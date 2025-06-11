---
status: newBorn
related-links: 
created: 2025-06-11T06:10
updated: 2025-06-11T06:10
---
---

### Q: What is a cookie?

- A Cookie is a small piece of data a server sends to a client's web browser.
- **Client browser** stores the cookie and sends it back automatically on every matching request.
- Cookies will also stay saved even when you close and reopen your browser
- used to maintain sessions, track activity, or store temporary info.
- **Server** sets the cookie using the response (`res`) object.

---

### Q: How to manually set a cookie in Node.js (without libraries)?

```js
res.setHeader("Set-Cookie", "token=123456; HttpOnly; Path=/; Max-Age=3600");
```

This sets a raw HTTP header.

---

 ✅ Perfect for:

- Authentication
- Server-side needed data
- Cross-subdomain data
- User Tracking (yeah…)
- Small bits of data (4KB limit)

❌ Avoid for **(kinda)**:

- Large amounts of data (that’s why we have databases)
- Client-only data (local storage could do that for us, **but this depends on the situation**)
- Frequent updates (You’ll be transferring additional data to the server every time you make a request. More so if you are storing a lot of data into the cookies.)

Disclaimer: Cookies are honestly good for a lot of things, but it all depends on the situation.

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

