---
status: newBorn
related-links: 
created: 2025-05-18T15:22
updated: 2025-05-18T15:22
---
---

- `User` becomes `users` in MongoDB.
- Mongoose automatically pluralizes & lowercases the model name.
- You can override it:
```js
mongoose.model('User', schema, 'custom_collection_name');
```


