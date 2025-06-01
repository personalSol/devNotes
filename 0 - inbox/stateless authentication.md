---
status: newBorn
related-links: 
created: 2025-05-31T13:35
updated: 2025-06-01T18:07
---
---

- **Stateless**: The server does **not** store session data.
- **[jsonwebtoken]** is the commonly used library for handling JWTs in Node.js.

==how it works==
- When a user logs in for the first time:
    - The server creates a **JWT (JSON Web Token)** using the user’s details and a **secret key**.
    - This token is sent back to the client (user's browser/app).
    - The server does **not** store the token — instead, it uses the secret key to **verify** the token on future requests.
- For every subsequent request:
    - The client sends the token (usually in the `Authorization` header).
    - The server **verifies** the token using the same secret key.
    - If valid, the server processes the request based on the token's payload.

> the entire process in detail in: [[authentication - entire stateless process]]


advantages:
- Tamper-proof: Tokens are **signed** with a secret key, making it difficult to alter the payload without invalidating the signature.
- Memory-efficient: No need to store session data in the server or database.
- Supports serverless architectures: Since tokens are self-contained, they work well with stateless services.
- Long-term authentication: Tokens can have extended expiration times (like "Remember Me" in Facebook).

disadvantage:
- **Token revocation is tricky**: Since tokens are stored on the client side and not tracked by the server, it’s hard to invalidate a specific token (e.g., during logout).
- **Less secure than sessions in some cases**: If a token is stolen (e.g., from local storage), a malicious user can impersonate the original user until the token expires.
