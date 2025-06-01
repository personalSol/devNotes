---
status: newBorn
related-links: 
created: 2025-06-01T10:19
updated: 2025-06-01T10:19
---
---

The **signature is tightly tied to the exact content** of the header and payload **AND** the secret key.

### ❌ What happens if a hacker changes the payload?

Say they decode the token and try to change:

```js
{ "userId": 123, "isAdmin": false }
```
to: `{ "userId": 123, "isAdmin": true }`

Now they re-encode it to base64 and build a new token:
```js
<header>.<modified-payload>.<old-signature>
```
🧨 Problem: The **signature is now invalid**, because it was generated using the old payload.