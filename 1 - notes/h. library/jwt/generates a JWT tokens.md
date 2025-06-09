---
status: newBorn
related-links: 
created: 2025-06-01T19:45
updated: 2025-06-01T19:55
---
---

### syntax
```js
const jwt = require('jsonwebtoken');

const token = jwt.sign(
  { userId: 123 },              // payload
  'your-secret-key',            // secret
  { expiresIn: '1h' }           // options
);
```

`expireIn` automatically add an `exp` (expiration) field to the **payload**, **not the header**.



```js
userSchema.methods.generateAccessToken = async function () {
    return jwt.sign(
        {
            _id: this._id,
            fullName: this.fullName,
            email: this.email,
            username: this.username
        },
        process.env.ACCESS_TOKEN_SECRET,
        {
            expiresIn: process.env.ACCESS_TOKEN_EXPIRY
        }
    );
};

userSchema.methods.generateRefreshToken = async function () {
    return jwt.sign(
        {
            _id: this._id
        },
        process.env.REFRESH_TOKEN_SECRET,
        {
            expiresIn: process.env.REFRESH_TOKEN_EXPIRY
        }
    );
};

```