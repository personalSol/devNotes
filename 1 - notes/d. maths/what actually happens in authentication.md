---
status: newBorn
related-links: 
created: 2025-05-31T11:21
updated: 2025-05-31T11:21
---
---

#### 1. **User signs up:**

- They enter a password.
- The password is **hashed** (often using bcrypt, scrypt, or Argon2).
- The hash is stored in the database.

#### 2. **User logs in later:**

- They enter the password again.
- The same hash function is applied.
- The result is **compared to the stored hash**.
- If they match, the user is authenticated.

