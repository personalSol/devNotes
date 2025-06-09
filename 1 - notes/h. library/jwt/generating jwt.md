---
status: newBorn
related-links: 
created: 2025-06-01T10:01
updated: 2025-06-01T10:01
---
---

1. Takes a **header** (e.g., `{ alg: 'HS256', typ: 'JWT' }`)
2. Adds a **payload** (e.g., `{ userId: 123 }`)
3. the secret key is used to sign the [[jwt signature]] part of token by using header and payload
4. then whole token which includes: `<base64(header)>.<base64(payload)>.<signature>` is send to the user

