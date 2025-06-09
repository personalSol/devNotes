---
status: newBorn
related-links: 
created: 2025-06-01T09:56
updated: 2025-06-01T19:56
---
---

we first have to varidate user using [[bcrypt]] and then create a token for him using [[jwt]] to help him stay logged in


## 🧩 1. During **Login**: We use bcrypt

When a user is logging in, this happens:
1. The user enters **email + password**.
2. The server:
    - Finds the user in the **database by email**.
    - Takes the **password entered by user** and compares it to the **hashed password in DB** using **bcrypt.compare()**.
3. If correct:
    - Server [[generates a JWT tokens]] using user data.
    - Sends JWT back to the client.
        - User stores token (typically in `localStorage` or `cookie`)
4. If wrong:
    - Responds with "invalid credentials".

✅ So **here**, we **do know** the original data (email + password). This is **not** the JWT part yet — it’s standard authentication.

![[generating jwt]]
