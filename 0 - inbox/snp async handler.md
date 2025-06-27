---
status: newBorn
related-links: 
created: 2025-06-27T09:55
updated: 2025-06-27T09:55
---
---

```js
const asyncHandler = (fn) => (req, res, next) => {
    Promise.resolve(fn(req, res, next)).catch((err) => (console.log(err)));
}

export { asyncHandler } 

// const asyncHandler = (fn) => {
//     return async (req, res, next) => {
//         try {
//             await fn(req, res, next)
//         } catch (err) {
//             res.status(err.code || 500).json({
//                 success: false,
//                 message: err.message
//             })
//         }
//     }
// }
```

