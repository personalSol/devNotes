---
status: newBorn
related-links: 
created: 2025-06-11T20:06
updated: 2025-06-11T20:06
---
---
## 📦 Bcrypt Hash Example
```text
$2b$10$CwTycUXWue0Thq9StjUM0uJ8KsZnp1A7s3Ufa4a6cQya6mUwR6jHm
```

### Breakdown:
| Part               | Example                      | Meaning                                 |
|--------------------|------------------------------|-----------------------------------------|
| Prefix             | `$2b$`                       | Algorithm version used (bcrypt version) |
| Cost Factor        | `10$`                         | Number of salt rounds (2^10 iterations) |
| Salt               | `CwTycUXWue0Thq9StjUM0u`     | 22-character base64-encoded salt        |
| Hashed Password    | `J8KsZnp1A7s3Ufa4a6cQya6mUwR6jHm` | Resulting hash of password + salt |

---

## ✅ Key Points:
- Salt is **embedded inside the hash string.**
- No need to store the salt separately.
- Cost factor controls hashing time (higher = more secure but slower).

---

### Hashing and Verifying (Callback Example)
```js
// this is just to explain the hash and compare process. We don't use compare inside hash in production level code

const bcrypt = require('bcrypt');

const password = 'mySecretPassword';
const saltRounds = 10;

bcrypt.hash(password, saltRounds, (err, hash) => {
    if (err) {
        console.error('Error hashing password:', err);
        return;
    }

    console.log('Hashed Password:', hash);

    // Verifying the password
    bcrypt.compare(password, hash, (err, result) => {
        if (err) {
            console.error('Error verifying password:', err);
            return;
        }

        if (result) {
            console.log('✅ Password is correct!');
        } else {
            console.log('❌ Password is incorrect.');
        }
    });
});
```

---

## 🔍 How Verification Works Internally

When you do:
```js
bcrypt.compare(userInput, storedHash)
```
1. **Extracts salt and cost factor** from `storedHash` automatically.
2. **Re-hashes the user input** with the extracted salt and cost.
3. Compares the **new hash** to the `storedHash`.
4. If both hashes match → ✅ Password is correct.

### Visual:
```text
User Input: "mySecretPassword" 
      ↓
bcrypt.compare("mySecretPassword", storedHash)
      ↓
Extract salt & cost from storedHash
      ↓
Re-hash input password with extracted salt
      ↓
Compare new hash with stored hash
      ↓
If they match → password is correct ✅
If not → password is incorrect ❌
```

---

## ✅ Why This Is Safe
- bcrypt stores all info (salt, cost) inside the hash.
- You never store plaintext passwords.
- You don’t need to manage the salt separately.
- Verification is automatic and secure.


