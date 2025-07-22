---
status: newBorn
related-links: 
created: 2025-05-18T15:22
updated: 2025-07-22T20:02
---
---

- `User` becomes `users` in MongoDB.
	- Mongoose automatically pluralizes & lowercases the model name.
	- but if you write `users` instead of `User`, mongoose will understand it and not try to convert it into plural
	- You can override it:
```js
mongoose.model('User', schema, 'custom_collection_name');
```

- The `new` keyword is necessary because [Schema](vscode-file://vscode-app/d:/Program%20Files/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html) is a constructor function in Mongoose that creates new schema instances. Without `new`, you would be calling the function directly instead of constructing a new instance, which would not work correctly.
- middlewares and methods are directly attached to schema and not to model
![[mongodb things to remember#^zevslo]]