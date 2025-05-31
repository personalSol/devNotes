---
status: newBorn
related-links: 
created: 2025-05-31T10:58
updated: 2025-05-31T10:58
---
---

Hashing is a process of converting data (like a file or a message) into a fixed-size string of characters, which typically appears random. It is a process that transforms input data (of any size) into a fixed-size string of characters.

- doesn't require any type of key
- **Examples:** SHA-256, MD5, bcrypt.

![[image 2.png||400]]

**Key Characteristics**:
1. **Deterministic**: The same input will always produce the same output.
2. **Fast computation**: The hash value can be quickly computed for any given data.
3. **Pre-image resistance**: It should be computationally infeasible to reverse the hash function (i.e., find the original input given its hash output).
4. **Small changes in input produce large changes in output**: Even a tiny change in the input should drastically change the hash output.
5. **Collision resistance**: It should be computationally infeasible to find two different inputs that produce the same hash output.

JS Code to generate Sha-56 of any value
```js
const crypto = require('crypto');

const input = "100xdevs";
const hash = crypto.createHash('sha256').update(input).digest('hex');

console.log(hash)
```

**Use Cases:**
- Password storage (hashing + salting).
- Data integrity checks (e.g., file checksums).
- Digital signatures.



