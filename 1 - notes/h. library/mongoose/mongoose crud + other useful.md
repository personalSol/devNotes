---
status: newBorn
related-links: 
created: 2025-06-12T17:34
updated: 2025-06-12T17:34
---
---

## Setup
```js
const mongoose = require('mongoose');

const userSchema = new mongoose.Schema({
  name: String,
  age: Number,
  minor: Boolean,
});

const User = mongoose.model('User', userSchema);
```

---

## 1. Create

### Method: `create` - Adds a new document to the collection.
```js
User.create({ name: "John", age: 30 });
```

### Method: `save` - Saves a newly created document.
```js
const user = new User({ name: "John", age: 30 });
user.save();
```

---

## 2. Read

### Method: `find` - Retrieves all matching documents.
```js
User.find({});
```

### Method: `findOne` - Retrieves the first matching document.
```js
User.findOne({ name: "John" });
```

### Method: `findById` - Retrieves a document by its ID.
```js
User.findById('user_id_here');
```

---

## 3. Update

### Method: `updateOne` - Updates the first matching document.
```js
User.updateOne({ name: "John" }, { age: 35 });
```

### Method: `updateMany` - Updates all matching documents.
```js
User.updateMany({ age: { $lt: 18 } }, { minor: true });
```

### Method: `findByIdAndUpdate` - Updates a document by ID.
```js
User.findByIdAndUpdate('user_id_here', { name: "Johnny" }, { new: true });
```

---

## 4. Delete

### Method: `deleteOne` - Deletes the first matching document.
```js
User.deleteOne({ name: "John" });
```

### Method: `deleteMany` - Deletes all matching documents.
```js
User.deleteMany({ minor: true });
```

### Method: `findByIdAndDelete` - Deletes a document by ID.
```js
User.findByIdAndDelete('user_id_here');
```

---

## Other Useful Methods

### Method: `insertMany` - Inserts multiple documents at once.
```js
User.insertMany([
  { name: "Alice", age: 25 },
  { name: "Bob", age: 28 },
]);
```

### Method: `countDocuments` - Counts the number of matching documents.
```js
User.countDocuments({ age: { $gte: 18 } }).then(count => console.log(count));
```

### Method: `exists` - Checks if any document matches the condition.
```js
User.exists({ name: "John" }).then(exists => console.log(exists));
```

### Method: `replaceOne` - Replaces the entire document.
```js
User.replaceOne(
  { name: "Alice" },
  { name: "Alicia", age: 26, minor: false }
);
```


