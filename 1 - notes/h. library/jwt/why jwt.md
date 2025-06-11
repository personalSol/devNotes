---
status: newBorn
related-links: 
created: 2025-06-10T15:46
updated: 2025-06-10T15:46
---
---

the reason why jwt is because:
- stateful storage of tokens in database requires calling database at each request
	- this infinitely increases the number of database calls
	- which slows the server
	- plus increase cost and load on database

