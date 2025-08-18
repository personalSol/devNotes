---
status: newBorn
related-links: 
created: 2025-05-29T20:34
updated: 2025-06-10T16:38
---
---

![[Websites and Resources#^6pk24c]]


- [[why jwt]]
- [[jwt structure]]
- [[jwt header]] 
- [[jwt payload]]
- [[jwt signature]]
- [[generating jwt]]
- [[verifying jwt with jwt.verify()]]
- [[jwt methods]]

- signature is not encoded
- we don't add [[jwt secret keys]] to the token in any way
- jwt is json web token which works like a key to verify the user
- **UseCase of JWT**
	- a token which gets created after validating the user to:
		- keep the user logged in
		- saving him from logging again and again everytime user makes a request 
- It uses algorithms like **HS256** (HMAC + SHA-256) or **RS256** (RSA) to **sign** the token.
- Signing = encoding + adding a signature to prevent tampering.


When the server **creates a JWT**, it:

1. When the token comes back later in a request, the server uses the same **secret key** to **verify** that the signature hasn't been tampered with.
	- remember that server doesn't create the entire token. it just create the signature again and then compare it with the one user send in token