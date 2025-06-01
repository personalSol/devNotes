---
status: newBorn
related-links: 
created: 2025-05-29T20:34
updated: 2025-06-01T01:01
---
---

![[Websites and Resources#^6pk24c]]



🔐 JWT Structure (always 3 parts):
- `<base64url-encoded header>.<base64url-encoded payload>.<signature>`

```php
example:

eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9. <-- header
eyJ1c2VySWQiOjEyM30.                 <-- payload
H8fdiuTnX1kAf9kl3hvn3g2kXg9QyYqduTyXl4CU0dA <-- signature

```

- jwt header: contains 
- [[jwt payload]]
- [[jwt signature]]

- jwt is json web token which works like a key to verify the user
- a token which gets created after varidating the user to:
	- keep the user logged in
	- saving him from logging again and again everytime user makes a request 
- It uses algorithms like **HS256** (HMAC + SHA-256) or **RS256** (RSA) to **sign** the token.
- Signing = encoding + adding a signature to prevent tampering.


When the server **creates a JWT**, it:
1. Takes a **header** (e.g., `{ alg: 'HS256', typ: 'JWT' }`)
2. Adds a **payload** (e.g., `{ userId: 123 }`)
3. the secret key is used to sign the [[jwt signature]] part of token by using header and payload
4. When the token comes back later in a request, the server uses the same **secret key** to **verify** that the signature hasn't been tampered with.
	- remember that server doesn't create the entire token. it just create the signature again and then compare it with the one user send in token