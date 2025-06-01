---
status: newBorn
related-links: 
created: 2025-06-01T09:53
updated: 2025-06-01T10:29
---
---



- it is used in HMAC signature creation process where hmac uses header and payload with key to create signature 
- The **secret key is stored securely on the server** (e.g., in `.env`)
- It is used:
    - During token **creation** (to sign)
    - During token **verification** (to validate)
    - The secret key is **not stored in the token** and **not visible to the client** + never send to the user
