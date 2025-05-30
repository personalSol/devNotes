---
status: newBorn
related-links: 
created: 2025-05-31T11:07
updated: 2025-05-31T22:33
---
---

In **authentication**, we primarily use **hashing**, **not encryption**.

---

- [[authentication - why not encryption and when]]
- [[what actually happens in authentication]]
- [[authentication - hash vs encrypt]]
- [[authentication why bcrypt and not crypto]]
- [[authentication patterns]]
- [[entire authentication process]]
- 


#### 6. 🧠 Final Takeaways

- ✅ Use **encryption** for **protecting data** during transit (e.g., HTTPS).
- ✅ Use **hashing** (like `bcrypt`) for **password storage**.
- ❌ Never store passwords with `crypto.createHash()` or reversible encryption.