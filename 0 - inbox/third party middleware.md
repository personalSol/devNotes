---
status: newBorn
related-links: 
created: 2025-05-28T19:36
updated: 2025-05-28T19:36
---
---

### morgan

- morgan is used for many purposes, server according to input argument
- needs to be installed and imported
- needs to be used inside `use()` middleware

code
```js
app.use(morgan('dev'))
// 'dev' logs the request type (get/post) and status code along with the time it took to fulfill the request
```

