---
status: newBorn
related-links: 
created: 2025-06-01T10:28
updated: 2025-06-01T10:28
---
---

🔐 JWT Structure (always 3 parts):
- `<base64url-encoded header>.<base64url-encoded payload>.<signature>`

```php
example:

eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9. <-- header
eyJ1c2VySWQiOjEyM30.                 <-- payload
H8fdiuTnX1kAf9kl3hvn3g2kXg9QyYqduTyXl4CU0dA <-- signature
```

