---
status: newBorn
related-links: 
created: 2025-06-01T10:51
updated: 2025-06-01T10:51
---
---


## 7. Refresh Tokens

- Used to obtain a new access token when the current one expires.
- **Separate** from access tokens; usually:
  - Stored securely (e.g., HttpOnly cookie)
  - Not a JWT (often just a random string)
- Not included inside the JWT payload.

### Flow:
1. Server returns access and refresh tokens on login.
2. Client uses access token for requests.
3. When access token expires, client sends refresh token to `/refresh`.
4. Server verifies and issues a new access token.


