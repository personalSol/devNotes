---
status: newBorn
related-links:
  - "[[Express-MOC]]"
created: 2025-05-28T10:37
updated: 2025-05-28T19:37
---
---

A middleware is **any function** with the signature: `(req, res, next) => { ... }`

It’s part of the request–response cycle and can:
- Modify `req` and `res`
- End the response
- Or call `next()` to pass control



there are mainly three types of middlewares:
- [[build-in middleware]]
- [[user defined middleware]]
- [[third party middleware]] ( eg. morgan )

**more info on middlewares**: it needs to be stopped by returning next() function ( next need to be added in callback parameters to work )
- only after the middleware stops that another one runs
- runs for every request

