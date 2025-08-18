---
status: newBorn
related-links:
  - "[[Express-MOC]]"
created: 2025-05-28T10:37
updated: 2025-06-09T14:48
---
---

- A middleware is **any function** with the signature: `(req, res, next) => { ... }`
- it's like a dalal which does things with request before we give response
	- help us **process incoming requests and shape outgoing responses**.
- We can use **multiple middleware functions**, and they run in sequence.
	- The **order of middleware** matters — they execute in the order they are defined.
- It’s part of the request–response cycle and can:
	- Modify `req` and `res`
	- End the response
	- Or call `next()` to pass control
		- in Express.js, **if a middleware function does not call `next()` (or end the response with something like `res.send()`, `res.end()`, or `res.redirect()`), the request will hang** and never move forward.

- [[middleware - basic syntax and practical]]

there are mainly three types of middlewares:
- [[build-in middleware]]
- [[user defined middleware]]
- [[third party middleware]] ( eg. morgan )

**more info on middlewares**: it needs to be stopped by returning next() function ( next need to be added in callback parameters to work )
- only after the middleware stops that another one runs
- runs for every request

