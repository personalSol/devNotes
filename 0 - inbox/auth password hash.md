---
status: newBorn
related-links: 
created: 2025-06-11T18:54
updated: 2025-06-11T18:54
---
---

syntax:
```js
const hashedPassword = bcrypt.hash(password, saltRounds);
```

![[Screenshot_2024-09-15_at_6.43.20_PM.webp||500]]
```js
// example
bcrypt.hash(password, 10) // Will hash faster
bcrypt.hash(password, 12) // Will hash slower (more secure)
```