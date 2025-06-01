---
status: newBorn
related-links: 
created: 2025-06-01T10:50
updated: 2025-06-01T10:50
---
---

## 6. Token Expiration (`exp` claim)

- `exp` is a Unix timestamp (in **seconds**) indicating the expiration time.
- `Date.now()` returns time in **milliseconds** → divide by 1000 to compare.
- Example:
  ```
  if (Math.floor(Date.now() / 1000) > token.exp) {
    // Token expired
  }
  ```
- Libraries like `jsonwebtoken` allow setting:
  ```js
  jwt.sign(payload, secret, { expiresIn: '15m' });
  ```
