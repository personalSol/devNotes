---
status: newBorn
related-links: 
created: 2025-06-10T15:16
updated: 2025-06-11T18:33
---
---

- registering the user ( storing data in variables )
	- adding validations to data - using zod
	- add salting
	- hash password
- storing data in database
- using stateless with jwt ( not storing the credentials in server )
- expiring old token and keeping only one valid token per user

---- next are assumptions -----
- tracking ip and browser fingerprinting to block same token access from different places

--- sure about these ones -----
- using google auth

