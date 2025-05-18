---
status: adult
related-links:
  - "[[Cheatsheets-MOC]]"
created: 2025-04-05T12:11
updated: 2025-05-18T10:07
---
---


### Install Mongoose

```bash
npm install mongoose
```

### Connect to MongoDB

```js
const mongoose = require('mongoose')

mongoose.connect('mongodb://localhost:27017/myDB', {
  useNewUrlParser: true,
  useUnifiedTopology: true
})
.then(() => console.log("Connected to MongoDB"))
.catch(err => console.error(err))
```

---

## 🏗️ Define a Schema & Model

```js
const userSchema = new mongoose.Schema({
  name: String,
  age: Number,
  email: { type: String, required: true, unique: true },
  createdAt: { type: Date, default: Date.now }
})

const User = mongoose.model('User', userSchema)
```

---

## ➕ Create Documents

```js
const newUser = new User({ name: "Alice", age: 25, email: "alice@email.com" })
await newUser.save()
```

Or directly:

```js
await User.create({ name: "Bob", age: 30, email: "bob@email.com" })
```

---

## 🔍 Read (Queries)

```js
const users = await User.find()              // Find all
const one = await User.findOne({ name: "Bob" })
const byId = await User.findById("id_here")
```

### With Filters

```js
User.find({ age: { $gte: 18 } })
User.find().sort({ age: -1 }).limit(10)
```

---

## ✏️ Update

```js
await User.updateOne({ name: "Alice" }, { age: 26 })

await User.findByIdAndUpdate("id_here", { name: "Updated" }, { new: true })
```

---

## ❌ Delete

```js
await User.deleteOne({ name: "Bob" })
await User.findByIdAndDelete("id_here")
```

---

## 🧠 Schema Options

| Type | Example |
|------|---------|
| `String`, `Number`, `Date`, `Boolean`, `Buffer`, `ObjectId`, `Mixed`, `Array` | `name: String`, `tags: [String]` |

### Add validation:

```js
email: {
  type: String,
  required: true,
  match: /.+\@.+\..+/
}
```

---

## 🔗 Relationships (Refs / Population)

### Reference another model:

```js
const postSchema = new mongoose.Schema({
  title: String,
  user: { type: mongoose.Schema.Types.ObjectId, ref: 'User' }
})
const Post = mongoose.model('Post', postSchema)
```

### Populate:

```js
Post.find().populate('user')
```

---

## 🧪 Middleware (Hooks)

```js
userSchema.pre('save', function(next) {
  this.name = this.name.trim()
  next()
})
```

---

## 🧰 Other Tips

### Check if connected:

```js
mongoose.connection.readyState
```

### Disconnect:

```js
mongoose.disconnect()
```

---

## 📌 Summary

- Use **Schema** to define structure  
- **Model** gives you access to the collection  
- Supports validation, middleware, and relationships  
- Query with `.find()`, `.findOne()`, etc.  
- Use `.populate()` for joins  
- Great with Express apps  

---

## 🧱 Coming From SQL?

| SQL | Mongoose |
|-----|----------|
| Table | Collection (Model) |
| Row | Document |
| Column | Field |
| Foreign Key | Ref + Populate |

---

## 🔗 Common Errors

- ❌ `E11000 duplicate key error`: duplicate unique value  
- ❌ ValidationError: required field missing  
- ❌ `MongooseError: Operation...buffering timed out`: DB not connected

---

## 🛠️ Tools

- **Mongoose Docs**: https://mongoosejs.com/docs/  
- **MongoDB Compass** for GUI exploration  
- **Postman** for testing Express APIs with Mongoose




# Reference
`related tags + notes + source + link(if any)`
 