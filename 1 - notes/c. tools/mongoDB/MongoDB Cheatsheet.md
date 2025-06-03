---
status: newBorn
related-links:
  - "[[Cheatsheets-MOC]]"
created: 2025-04-05T12:07
updated: 2025-06-03T16:14
---
---

## 🧱 Basics

| Command | What It Does |
|--------|-----------------------------|
| `mongosh` | Opens the MongoDB shell |
| `show dbs` | Lists all available databases |
| `use myDB` | Switches to or creates a database named `myDB` |
| `show collections` | Lists all collections (like tables) in the current DB |
| `db` | Tells you which database you're currently in |

---

## 📦 CRUD Operations

### ➕ Create

```js
db.<collection_name>.insertOne({ name: "Alice", age: 25 })
```
👉 Adds one document to the collection.

```js
db.<collection_name>.insertMany([{ name: "Bob" }, { name: "Carol" }])
```
👉 Adds multiple documents at once.

---

### 🔍 Read

```js
db.<collection_name>.find()
```
👉 Shows all documents.

```js
db.<collection_name>.find({ age: 25 })
```
👉 Finds documents where age is 25.

```js
db.<collection_name>.findOne({ name: "Alice" })
```
👉 Finds the first match for name "Alice".

---

### ✏️ Update

```js
db.<collection_name>.updateOne({ name: "Alice" }, { $set: { age: 26 } })
```
👉 Updates Alice’s age to 26.

```js
db.<collection_name>.updateMany({}, { $inc: { age: 1 } })
```
👉 Increases everyone's age by 1.

---

### ❌ Delete

```js
db.<collection_name>.deleteOne({ name: "Bob" })
```
👉 Deletes the first Bob found.

```js
db.<collection_name>.deleteMany({ age: { $gt: 30 } })
```
👉 Deletes all documents where age > 30.

---

## 🔍 Query Operators

| Operator | Meaning |
|----------|---------|
| `$gt` | Greater than |
| `$lt` | Less than |
| `$gte` | Greater than or equal to |
| `$lte` | Less than or equal to |
| `$eq` | Equal to |
| `$ne` | Not equal |
| `$in` | Value exists in array |
| `$nin` | Value does not exist in array |
| `$and`, `$or` | Logical operators for combining conditions |

```js
db.<collection_name>.find({ age: { $gt: 20, $lt: 30 } })
```
👉 Finds users aged between 21 and 29.

---

## 🔧 Projections

```js
db.<collection_name>.find({}, { name: 1, _id: 0 })
```
👉 Show only the `name` field, hide `_id`.

---

## 🎯 Aggregation (Advanced Data Analysis)

Aggregation is like using formulas and filters in a spreadsheet or `GROUP BY` in SQL.

```js
db.<collection_name>.aggregate([
  { $match: { age: { $gt: 20 } } },
  { $group: { _id: "$city", total: { $sum: 1 } } },
  { $sort: { total: -1 } }
])
```

**Explanation:**
- `$match` filters documents
- `$group` groups them by city and counts them
- `$sort` sorts the result by count (descending)

Other useful aggregation operators:
- `$avg`: average
- `$sum`: sum
- `$max` / `$min`: maximum / minimum
- `$push`: collect values into arrays
- `$project`: select or reshape fields

---

## 🏃 Indexing

```js
db.<collection_name>.createIndex({ name: 1 })
```
👉 Speeds up queries using the `name` field.

```js
db.<collection_name>.dropIndex({ name: 1 })
```
👉 Removes the index.

---

## 🛠️ Useful Admin Commands

| Command | What It Does |
|---------|-------------------------|
| `db.stats()` | Shows stats about the current database |
| `db.<collection_name>.stats()` | Shows stats for a specific collection |
| `db.dropDatabase()` | Deletes the whole database ⚠️ |
| `db.<collection_name>.drop()` | Deletes the collection ⚠️ |

---

## 🔐 User Authentication

```js
use admin
db.createUser({
  user: "admin",
  pwd: "password123",
  roles: ["userAdminAnyDatabase", "readWriteAnyDatabase"]
})
```
👉 Creates an admin user with full DB access.

---

## 🔗 Connection String

```bash
mongodb://username:password@localhost:27017/myDB
```
👉 Use this to connect from Node.js, Mongoose, or any app.

---

## ✅ Quick Recap

- **Collections** = SQL tables  
- **Documents** = rows (but in JSON format)  
- **No schema needed** – MongoDB is flexible  
- **Aggregation** = powerful tool for reports and analytics  
- **Indexes** = make searches fast, especially on big collections  



# Reference
`related tags + notes + source + link(if any)`
 

- 