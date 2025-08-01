---
status: newBorn
related-links: 
created: 2025-08-01T01:16
updated: 2025-08-01T01:16
---
---

- to remove something from querry output
```js
const user = await User.findById(decoded.id).select("-password -refreshToken");
req.user = user;
```

