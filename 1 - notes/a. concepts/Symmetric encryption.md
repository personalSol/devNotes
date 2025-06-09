---
status: newBorn
related-links: 
created: 2025-05-31T10:38
updated: 2025-05-31T10:38
---
---

Symmetric encryption uses the same key for both encrypting and decrypting data. It’s like using a single key to both lock and unlock a door.

> symmetric means symmetric or same

![[Pasted image 20250531103809.png]]

### code
```js
const crypto = require('crypto');

// Generate a random encryption key
const key = crypto.randomBytes(32); // 32 bytes = 256 bits
const iv = crypto.randomBytes(16); // Initialization vector (IV)

// Function to encrypt text
function encrypt(text) {
    const cipher = crypto.createCipheriv('aes-256-cbc', key, iv);
    let encrypted = cipher.update(text, 'utf8', 'hex');
    encrypted += cipher.final('hex');
    return encrypted;
}

// Function to decrypt text
function decrypt(encryptedText) {
    const decipher = crypto.createDecipheriv('aes-256-cbc', key, iv);
    let decrypted = decipher.update(encryptedText, 'hex', 'utf8');
    decrypted += decipher.final('utf8');
    return decrypted;
}

// Example usage
const textToEncrypt = 'Hello, World!';
const encryptedText = encrypt(textToEncrypt);
const decryptedText = decrypt(encryptedText);

console.log('Original Text:', textToEncrypt);
console.log('Encrypted Text:', encryptedText);
console.log('Decrypted Text:', decryptedText);
```

### Use Case:

- **File Encryption**: When you encrypt a file on your computer using symmetric encryption, the same password (key) you used to lock the file is required to unlock it.
- 