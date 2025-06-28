---
status: newBorn
related-links: 
created: 2025-06-27T18:16
updated: 2025-06-27T18:16
---
---

**Atomicity (in DBMS)**

**Atomicity** means that a **transaction must be all or nothing**.  
Either **all operations** within the transaction are completed successfully, or **none of them are**.

---

✅ If it succeeds:

All steps of the transaction are committed.

❌ If it fails (due to crash, error, etc.):

All changes made during the transaction are **rolled back**, leaving the database unchanged.

---

📦 Example:

A bank transfer from Account A to B involves:

1. Deduct ₹500 from Account A
2. Add ₹500 to Account B

**Atomicity ensures:**

- If both steps succeed → changes are saved
- If step 1 succeeds but step 2 fails → step 1 is undone

