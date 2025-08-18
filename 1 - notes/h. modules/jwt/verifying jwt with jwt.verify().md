---
status: newBorn
related-links: 
created: 2025-06-01T10:03
updated: 2025-06-10T17:05
---
---

![[jwt.verify()]]


#### example
- let's say token is: 
```js
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOjEyM30.H8fdiuTnX1kAf9kl3hvn3g2kXg9QyYqduTyXl4CU0dA
```

Split it into:
- **Header** (base64): `eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9` → decoded: `{ alg: 'HS256', typ: 'JWT' }`
- **Payload** (base64): `eyJ1c2VySWQiOjEyM30` → decoded: `{ userId: 123 }`
- **Signature**: `H8fdiu...`

Server then:
1. **Decodes header and payload** (no secret key needed).
2. **Recomputes signature** using: `HMAC_SHA256(header + '.' + payload, secret_key)`
3. Compares it with the signature sent by the client.
If they match → token is valid.  
If not → token is tampered or fake.


![[jwt - is verifying signature memory intensive]]