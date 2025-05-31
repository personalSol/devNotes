---
status: newBorn
related-links: 
created: 2025-05-31T13:35
updated: 2025-05-31T18:25
---
---

- **Stateless**: The server does **not** store session data.
- **[jsonwebtoken]** is the commonly used library for handling JWTs in Node.js.


==How it works==
- When a user logs in for the first time:
    - The server creates a **JWT (JSON Web Token)** using the user’s details and a **secret key**.
    - This token is sent back to the client (user's browser/app).
    - The server does **not** store the token — instead, it uses the secret key to **verify** the token on future requests.
- For every subsequent request:
    - The client sends the token (usually in the `Authorization` header).
    - The server **verifies** the token using the same secret key.
    - If valid, the server processes the request based on the token's payload.


Advantages:
- token can't be tampered without secret key for some reason
- memory efficient as we don't have to save user (idk what ) in database 
- supports serverless architecture
- can have long term authentication like fb

Disadvantage:
- it's difficult to validate and remove a particular user as we are directly storing tokens
- not as secured as sessions as your token can be stolen and used by hacker to impersonate
