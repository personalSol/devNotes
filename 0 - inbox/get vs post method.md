---
status: newBorn
related-links: 
created: 2025-05-28T09:09
updated: 2025-05-28T09:09
---
---
## 🔍 GET — "Read" or Retrieve Data

- **Purpose**: Request data from the server.
- **How**: Sends data via **URL query parameters**.
- **Visible?** Yes (in the URL).
- **Changes Server?** No — it's a **read-only** request.
- **Example**:
	- `GET /search?query=cats`

- **Analogy**: Pressing a vending machine button — you're *asking* for something, not changing anything.

---

## 🛠️ POST — "Create" or Submit Data

- **Purpose**: Send data to the server to **create** or process something.
- **How**: Sends data in the **request body** (hidden from the URL).
- **Visible?** No (data not shown in URL).
- **Changes Server?** Yes — it might create a record, process a payment, etc.
- **Example**: 
```js
POST /register  
Body: { "name": "Sara", "email": "sara@example.com" }
```

- **Analogy**: Inserting money and pressing a combo in a vending machine — you're **doing** something that changes the machine’s state.

---

---

## 🔐 Reminder: Use HTTPS for Security
Even though POST hides data from the URL, it's **not encrypted unless you use HTTPS**. Always use HTTPS to protect sensitive info.

---


