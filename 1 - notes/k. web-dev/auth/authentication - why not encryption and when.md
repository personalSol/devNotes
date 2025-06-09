---
status: newBorn
related-links: 
created: 2025-05-31T11:21
updated: 2025-05-31T11:21
---
---

- **Passwords should never be encrypted and stored**, because encryption is reversible — if someone gets the private key of server, they can get every user’s password.
- Instead, we **hash** passwords and **compare hash values**.

### 🔄 Do We Ever Use Encryption in Authentication?

Yes — but **not for storing passwords**:

- **HTTPS (SSL/TLS)** uses encryption to securely **transmit** credentials from client to server.
- **JWTs (JSON Web Tokens)** might be encrypted or signed — signing uses hashing and keys (HMAC or RSA).
