---
status: newBorn
related-links:
  - "[[Basic-Concepts-MOC]]"
created: 2025-05-28T09:05
updated: 2025-06-09T12:56
---
---

there are several **HTTP methods**, each designed for a specific purpose in client-server communication — especially useful in web development and APIs.

- **HTTP methods define the _intent_ of a request**, not just how data is sent.

![[Screenshot_2024-08-25_at_7.13.12_PM.webp||400]]

![[Pasted image 20250602152025.png||500]]

---

- [[get vs post method]]
- 


### ✅ **1. GET**

- **Purpose:** Retrieve data from the server.
- **Safe:** ✅ (Doesn’t change anything)
- **Data in URL:** ✅ (Visible)
- **Example:** Viewing a blog post

---

### ✅ **2. POST**

- **Purpose:** Send data to the server (e.g., to create something).
- **Safe:** ❌ (Can change server state)
- **Data in Body:** ✅ (Hidden from URL)
- **Example:** Submitting a form, creating a new user

---

### 🔄 **3. PUT**


- **Purpose:** Replace/update an existing resource completely.
- **Idempotent:** ✅ (Sending it multiple times has the same effect)
- You generally need to **send all fields**, even unchanged ones.
- **Example:** Updating a profile with new data

```js
PUT /users/123
{
  "name": "Alice",
  "email": "alice@example.com"
}
```

---

### 🔄 **4. PATCH**

- **Used to update _part_ of a resource (document)**.
- **Purpose:** Partially update a resource.
- **Idempotent:** ✅ (Like PUT, but only changes part of the data)
- Does NOT require sending the full object.
- **Example:** Updating just the `email` field of a user.

```js
PATCH /users/123
{
  "email": "new@example.com"
}
```

---

### ❌ **5. DELETE**

- **Purpose:** Remove a resource.
- **Idempotent:** ✅ (Deleting something twice has the same outcome — it's gone)
- **Example:** Deleting a post or comment

---

### ❓ **6. HEAD**

- **Purpose:** Like GET, but returns only headers (no body).
- **Use case:** Check if a resource exists or test speed

---

### 🔎 **7. OPTIONS**

- **Purpose:** Ask the server what methods are allowed for a URL.
- **Use case:** Preflight checks in CORS (Cross-Origin Resource Sharing)


## 🧠 Easy Way to Remember

| Method | Mnemonic        | Action      | Data Location | Server Change? |
|--------|------------------|-------------|---------------|----------------|
| GET    | "Give me info"   | Read        | URL           | ❌ No          |
| POST   | "Post it there"  | Create      | Request Body  | ✅ Yes         |
| PUT    | "Put it back"    | Replace     | Request Body  | ✅ Yes         |
| PATCH  | "Patch it up"    | Update Part | Request Body  | ✅ Yes         |
| DELETE | "Delete it"      | Remove      | URL/Body      | ✅ Yes         |
