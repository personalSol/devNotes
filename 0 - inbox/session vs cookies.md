---
status: newBorn
related-links: 
created: 2025-05-31T13:28
updated: 2025-05-31T13:28
---
---

| Feature          | Cookies                                                                     | Sessions                                                      |
| ---------------- | --------------------------------------------------------------------------- | ------------------------------------------------------------- |
| **Storage**      | Stored in the **browser (client-side)**                                     | Stored on the **server-side**                                 |
| **Statefulness** | **Stateless** (just stores data like a token or session ID)                 | **Stateful** (server keeps user data)                         |
| **Security**     | Can be tampered with (unless secured with `HttpOnly`, `Secure`, `SameSite`) | More secure since data stays on the server                    |
| **Typical use**  | Store tokens, user preferences, or session IDs                              | Store actual session data like user info, cart contents, etc. |
| **Size limit**   | ~4KB                                                                        | Depends on server memory                                      |

