---
status: newBorn
related-links: 
created: 2025-05-31T11:14
updated: 2025-05-31T11:14
---
---

> means kisi ne data mai change to nhi kra jo nhi hona chayia tha


### 🔍 **Data Integrity Checking** means:

Making sure the **data has not been changed, tampered with, or corrupted** — either on purpose (maliciously) or by accident — during transmission or storage.


### 💡 In simple terms:

> “Did the data I receive match exactly what was originally sent?”


### 🧰 How is it usually done?

Using things like:

- **Hash functions** (e.g., SHA-256)
- **Message Authentication Codes (MACs)**
- **Digital signatures**

---

### 🔐 Example in HTTPS:

When a server sends you data:

1. It also sends a **hash** (a digital fingerprint).
2. Your browser checks:
    - “Does the data I got create the same fingerprint?”
3. If **yes**, then the data is **intact**.
4. If **no**, the data was likely **tampered with or corrupted**.

