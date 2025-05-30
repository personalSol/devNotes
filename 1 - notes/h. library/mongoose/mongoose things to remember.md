---
status: newBorn
related-links: 
created: 2025-05-18T15:22
updated: 2025-05-27T21:22
---
---

- `User` becomes `users` in MongoDB.
	- Mongoose automatically pluralizes & lowercases the model name.
	- but if you write `users` instead of `User`, mongoose will understand it and not try to convert it into plural
	- You can override it:
```js
mongoose.model('User', schema, 'custom_collection_name');
```

- if we don't connect to a 
