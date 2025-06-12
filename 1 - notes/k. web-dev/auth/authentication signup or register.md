---
status: newBorn
related-links: 
created: 2025-06-01T10:12
updated: 2025-06-11T18:57
---
---

Here’s what happens **when a user signs up**:

1. User sends data:  
    `{ name, email, password }`
2. Server:
    - Hashes the password using **bcrypt**:
	```js
	const hashedPassword = bcrypt.hash(password, saltRounds);
	```
	- Stores the user in the database: `{ name, email, hashedPassword }`
- ✅ No JWT is used here. JWT comes **after** login.

> something to add: saltRound which is the second argument here takes number and the higher the number the more computational power it takes to generate hash

- ❌ **It doesn't create a more complicated salt.**
- ✅ **It takes more time to hash because of more computation (iterations).**