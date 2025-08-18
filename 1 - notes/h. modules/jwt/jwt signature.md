---
status: newBorn
related-links: 
created: 2025-05-31T23:19
updated: 2025-06-01T10:33
---
---

In **JWT (JSON Web Token)**, the **signature** is **not just the encoded secret key**. Instead, it is a **cryptographic hash** (usually using HMAC SHA256) of the **header and payload**, **signed** using the **secret key**.

**here is how signature get's created:**
```js
signature = HMAC-SHA256(
  base64urlEncode(header) + "." + base64urlEncode(payload),
  secret_key
)
```

### signature creation

signature is calculated:
- using HMAC which is an algorithm which uses header and payload with secret key 
- so signature contains header and payload which if tampered also changes the signature as signature as it was created using them

#### remember:
- signature is not encoded
- [[HMAC vs Hash]]