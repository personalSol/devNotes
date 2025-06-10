---
status: newBorn
related-links: 
created: 2025-06-10T16:50
updated: 2025-06-10T17:07
---
---

### What `jwt.verify` Does (Step-by-Step)

`jwt.verify(token, secret)` performs the following operations internally:

---

#### 1. Split the Token

- JWT is split into three parts: `header.payload.signature`
- These are separated by periods (`.`)

---

#### 2. Decode Header and Payload

- Base64Url-decodes the **header** and **payload** to extract information.
- Header contains metadata (e.g., algorithm used)
- Payload contains claims (e.g., user ID, exp, iat)

---

#### 3. Recompute the Signature

- Using the algorithm specified in the header (commonly `HS256`), and the provided secret key:

```js
HMAC-SHA256(secret, base64UrlEncode(header) + "." + base64UrlEncode(payload))
```

- This generates a **new signature** on the server side.

---

#### 4. Compare the Signatures

```js
if (recalculated_signature === signature_from_token) {
  // Token is authentic
} else {
  // Token is invalid or tampered
}
```

- If they match, token is valid.
- If they don’t match, the token is rejected.

---

#### 5. Validate Standard Claims (if present)

- `exp` → Rejects the token if **expired**. - [[jwt - token expiry]]
	- **Check if the token has expired** based on the `exp` field.
	- **Throw an error** if the token is expired. The error is usually something like:  
			    `TokenExpiredError: jwt expired`
- `nbf` → Rejects the token if used **before allowed time**.
- `iat` → (Issued At) Can be used for auditing or logic, but not strictly required.
- `aud` (audience)

✅ These validations are **done automatically** by `jwt.verify()`.

---

### Final Notes

- No need to manually check expiration — it's handled internally.
- Works similarly for other algorithms (like `RS256`), using public/private key instead of secret.

---

Use `try...catch` to handle verification errors gracefully in code:

```js
const jwt = require('jsonwebtoken');

try {
    const decoded = jwt.verify(token, secretKey);
    console.log('Token is valid', decoded);
} catch (err) {
    if (err.name === 'TokenExpiredError') {
        console.log('Token has expired');
    } else {
        console.log('Invalid token', err.message);
    }
}
```

