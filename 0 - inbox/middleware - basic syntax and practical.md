---
status: newBorn
related-links: 
created: 2025-06-09T14:48
updated: 2025-06-09T15:06
---
---

- global middlewares which we direcly declare on top with `app.use` work before every request

## Normal Function Example in Express (Not Middleware)

```js
const express = require('express');
const app = express();

// Normal function (not middleware)
function logUrl(url) {
    console.log(`Request made to: ${url}`);
}

app.get('/', (req, res) => {
    // Call the normal function manually
    logUrl(req.url);
    res.send('Home Page');
});

app.get('/about', (req, res) => {
    // Again, manually call the function
    logUrl(req.url);
    res.send('About Page');
});

app.listen(3000, () => console.log('Server running on port 3000'));
```

### Key Points:

- Called **manually** inside each route.
    
- ❌ Not part of the middleware chain.
    
- ❌ Cannot automatically run on every request.
    

---

## Middleware Function Example in Express

```js
const express = require('express');
const app = express();

// Middleware function
function logUrl(req, res, next) {
    console.log(`Request made to: ${req.url}`);
    next(); // Passes control to the next middleware or route handler
}

// Global middleware
app.use(logUrl);

app.get('/', (req, res) => {
    res.send('Home Page');
});

app.get('/about', (req, res) => {
    res.send('About Page');
});

app.listen(3000, () => console.log('Server running on port 3000'));
```

### Key Points:

- ✅ Automatically runs for **every request**.
    
- ✅ Part of the Express middleware chain.
    
- ✅ Uses `next()` to continue to the next handler.
    

---

## Middleware Applied Directly to Specific Routes

```js
app.get('/', logUrl, (req, res) => {
    res.send('Home Page');
});

app.get('/about', logUrl, (req, res) => {
    res.send('About Page');
});
```

### Key Points:

- ✅ Middleware can be attached **per route**.
    
- ✅ Runs only for the specified routes.
    

---

## Multiple Middlewares on a Single Route

```js
app.get('/', middleware1, middleware2, (req, res) => {
    res.send('Home Page');
});
```

### Key Points:

- ✅ Middlewares are executed in order.
    
- ✅ Each middleware must call `next()` to move to the next.
    

---

## Summary

|Feature|Normal Function|Middleware Function|
|---|---|---|
|Call Style|Manually inside each route|Automatically runs via `app.use` or directly in route|
|Parameters|Custom|`(req, res, next)`|
|Flow Control|No `next()`|Must call `next()`|
|Scope|Limited|Can be global or per-route|

---

### Conclusion:

- **Normal functions**: Best for simple utilities or calculations.
    
- **Middleware functions**: Best for processing requests, logging, authentication, and controlling flow in Express.js.

