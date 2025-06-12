---
status: newBorn
related-links: 
created: 2025-05-31T11:21
updated: 2025-06-11T18:25
---
---

- **Passwords should never be encrypted and stored**, because encryption is reversible — if someone gets the private key of server, they can get every user’s password.
- Instead, we **hash** passwords and **compare hash values**.

### 🔄 Do We Ever Use Encryption in Authentication?

Yes — but **not for storing passwords**:

- **HTTPS (SSL/TLS)** uses encryption to securely **transmit** credentials from client to server.
- **JWTs (JSON Web Tokens)** might be encrypted or signed — signing uses hashing and keys (HMAC or RSA).


|Task|Hashing|Encryption|
|---|---|---|
|Storing passwords|✅ Yes|❌ No|
|Transmitting passwords securely|❌ No|✅ Yes (via HTTPS)|
|Verifying user identity|✅ Yes|❌ No|
|Protecting communication|❌ No|✅ Yes|

#### 6. 🧠 Final Takeaways

- ✅ Use **encryption** for **protecting data** during transit (e.g., HTTPS).
- ✅ Use **hashing** (like `bcrypt`) for **password storage**.
- ❌ Never store passwords with `crypto.createHash()` or reversible encryption.