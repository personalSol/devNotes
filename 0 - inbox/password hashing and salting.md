---
status: newBorn
related-links: 
created: 2025-06-11T18:31
updated: 2025-06-11T18:54
---
---

## Why should you hash passwords?

Password hashing is a technique used to securely store passwords in a way that makes them difficult to recover or misuse. Instead of storing the actual password, you store a hashed version of it.

## salt

A popular approach to hashing passwords involves using a hashing algorithm that incorporates a salt—a random value added to the password before hashing. This prevents attackers from using precomputed tables (rainbow tables) to crack passwords.

**rainbow tables**: rainbow table as harkirat explained is a table in which hackers store a general list of passwords ( maybe around 10+ ) with their hashed values. And then compare the leaked database passwords with their ranbow table hashes. if a hash match then they know that hash's original value which they can use to login and impersonate that person

- salting also prevents from having two similar hashes for two same passwords
	- as it adds a random salt value as a prefix with each password before hashing

### saltRounds

- **The salt itself is not more complicated when you increase the salt rounds.**
- **What actually increases is the number of hashing iterations.**

##### Detailed Explanation:

- In libraries like **bcrypt**, `saltRounds` (or "cost factor") controls **how many times** the hashing algorithm is run.
- The salt is just a random string that is added to the password to make hashes unique. Its complexity doesn't change based on `saltRounds`; it's randomly generated each time.
- **Higher saltRounds = more iterations = more time to compute the hash.**  
    This makes it harder for attackers to brute-force because each guess takes longer to compute.

## bcrypt

**Bcrypt**: It is a cryptographic hashing algorithm designed for securely hashing passwords. Developed by Niels Provos and David Mazières in 1999, bcrypt incorporates a salt and is designed to be computationally expensive, making brute-force attacks more difficult.

