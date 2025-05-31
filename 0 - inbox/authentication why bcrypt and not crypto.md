---
status: newBorn
related-links: 
created: 2025-05-31T11:24
updated: 2025-05-31T11:24
---
---

#### 🔥 Why `bcrypt` is Preferred for Passwords:

- Specifically made for **password hashing**.
- Adds **salt** automatically.
- Intentionally **slow** — resists brute-force attacks.
- Widely used and tested.

#### ⚠️ Why `crypto` is Not Ideal:

- Designed for general cryptography (not authentication).
- Hashes like `SHA-256` are **too fast** — easy to brute force.
- Manual salting required.
- Can be used with `pbkdf2`, but more complex.

|Feature|`bcrypt`|`crypto`|
|---|---|---|
|Designed for auth|✅ Yes|❌ No|
|Slow and secure|✅ Yes|❌ No|
|Salt included|✅ Yes|❌ No (manual)|
|Password hashing|✅ Recommended|❌ Not safe by default|