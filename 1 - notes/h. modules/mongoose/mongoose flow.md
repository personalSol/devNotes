---
status: newBorn
related-links: "[[Mongoose-MOC]]"
created: 2025-05-18T15:26
updated: 2025-05-28T02:23
---
---

### 1. Install
```bash
npm install mongoose
```

### 2. Connect to MongoDB (config/db.js)
```js
const mongoose = require('mongoose');

const connectDB = async () => {
  await mongoose.connect(`${process.env.MONGO_URI}/${DB_NAME}`);
};

module.exports = connectDB;
```

### 3. Define Schema & Model (models/user.model.js)
```js
const mongoose = require('mongoose');

const userSchema = new mongoose.Schema({
  name: String,
  email: String,
  age: Number
});

const User = mongoose.model('User', userSchema);
module.exports = User;
```

### 4. Use in App (index.js)
```js
const express = require('express');
const connectDB = require('./config/db');
const User = require('./models/user.model');

const app = express();
app.use(express.json());
connectDB();

app.post('/users', async (req, res) => {
  const user = new User(req.body);
  await user.save();
  res.status(201).json(user);
});

app.listen(3000);
```


