---
status: newBorn
related-links: 
created: 2025-07-21T21:38
updated: 2025-07-21T22:44
---
---

```js
userSchema.pre('save', async function (next){
    if(!this.isModified("password")) return next(); 
    this.password = await bcrypt.hash(this.password, 10);
})

userSchema.methods.checkPassword = async function (pass) {       
    return await bcrypt.compare(pass, this.password)  
}

userSchema.methods.generateAccessToken = function() {
    return jwt.sign({username: this.username, email: this.email}, process.env.JWT_SECRET_KEY);
}

userSchema.methods.generateRefreshToken = function() {
    return jwt.sign({username: this.username}, process.env.JWT_SECRET_KEY);
}
```

