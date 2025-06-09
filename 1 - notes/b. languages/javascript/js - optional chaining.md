---
status: newBorn
related-links: 
created: 2025-06-03T16:15
updated: 2025-06-03T16:15
---
---

### Q: What is optional chaining in JavaScript?
**A:** Optional chaining (`?.`) is a feature that allows you to safely access deeply nested properties without having to check if each level exists. If a reference is `null` or `undefined`, it short-circuits and returns `undefined` instead of throwing an error.

---
### Q: How do you use optional chaining?
**A:** You use `?.` before a property or method that might not exist.  
Example:
```js
const avatar = req.files?.avatar;
```
If `req.files` exists, it returns `req.files.avatar`. If not, it returns `undefined` safely.

### Q: What's the benefit of optional chaining?
**A:** It simplifies code and prevents runtime errors from trying to access properties on `undefined` or `null` values, making your code cleaner and safer.

### Q: Where can optional chaining be used?
**A:** 
- Object properties: `obj?.prop`
- Array elements: `arr?.[0]`
- Function calls: `obj.method?.()`

---
