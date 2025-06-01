---
status: newBorn
related-links: 
created: 2025-05-18T15:31
updated: 2025-06-01T18:43
---
---
### 🔹 What is a Schema?
- Blueprint for documents in a MongoDB collection.
- Defines structure, data types, validation, and default values.

### 🔹 Define a Schema
```js
const mongoose = require('mongoose');

const userSchema = new mongoose.Schema({
  name: String,
  age: Number,
  email: { type: String, required: true, unique: true },
  isAdmin: { type: Boolean, default: false },
  createdAt: { type: Date, default: Date.now }
});
```

### 🔹 Common Schema Types
- `String`
- `Number`
- `Date`
- `Boolean`
- `Array`
- `ObjectId` – for references
	- Used to link documents across collections.
	- Reference another model like this:
	- `type: ObjectId` specifies the field will store an ID.
	- `ref: "User"` should match the first argument in `mongoose.model("User", ...)` 
	- Best practice: keep the variable name and model name consistent.
``` js

```

### 🔹 Schema Options

- `timestamps`: adds `createdAt` & `updatedAt`
- `versionKey: false`: disables `__v` field

### 🔹 Validation

_validation_ means checking if the data meets **certain rules or constraints** before saving to the database. These rules can include range checks, but also more.

##### ✅ Validation Can Include:

- **Required check**: Is the field present?
- **Type check**: Is the value a string, number, etc.?
- **Range check** (for numbers): e.g. `min`, `max`
- **Length check** (for strings): e.g. `minlength`, `maxlength`
- **Format check**: e.g. using `match` with RegExp
- **Custom logic**: using `validate` with a function

---

## 🧾 Common Schema Field Options

| **Option**  | **Description**                                            | **Example**                             |
| ----------- | ---------------------------------------------------------- | --------------------------------------- |
| `type`      | Data type of the field                                     | `type: String`                          |
| `required`  | Makes the field mandatory                                  | `required: true`                        |
| `default`   | Sets a default value                                       | `default: Date.now`                     |
| `unique`    | Ensures unique value in the collection                     | `unique: true`                          |
| `minlength` | Minimum string length                                      | `minlength: 3`                          |
| `maxlength` | Maximum string length                                      | `maxlength: 50`                         |
| `min`       | Minimum number value                                       | `min: 18`                               |
| `max`       | Maximum number value                                       | `max: 99`                               |
| `enum`      | Allowed values for a string                                | `enum: ['admin', 'user', 'guest']`      |
| `match`     | Regex pattern validation                                   | `match: /@gmail\.com$/`                 |
| `validate`  | Custom validation function                                 | `validate: val => val.length % 2 === 0` |
| `select`    | Include/exclude field from query results                   | `select: false`                         |
| `immutable` | Prevent changes after initial set                          | `immutable: true`                       |
| `alias`     | Alternate name for field                                   | `alias: 'n'` (use `doc.n` for `name`)   |
| index ⭐     | used to help index things better, only used when necessary | `index: true`                           |
| trim        | used to remove leading and trailing whitespaces            | `trim: true`                            |



### code

```js
// options
const schema = new mongoose.Schema({}, { timestamps: true, versionKey: false });

// validation of value
name: { type: String, required: true, minlength: 2, maxlength: 50 }

// --------------- referencing --------------
createdBy: {
            type: mongoose.Schema.Types.ObjectId,
            ref: "User"
}


// for having `n` number of values, we use array⭐
orderItems: {
        type: [orderItemsSchema]
}
// this is when we need multiple options

orderItems: [orderItemsSchema]
// this is when we don't need options


// we can declare it on schema or directly write the object inside array
// means when we want to use another schema. we can create it separately and them import it or we can directly create object which we create in schema
const orderItemsSchema = mongoose.Schema({
    products: {
        type: mongoose.Schema.Types.ObjectId,
        ref: "Product"
    },
    quantity: {
        type: Number,
        required: true
    }
})

// directly writing object inside array like this
SubTodo: [{
            type: mongoose.Schema.Types.ObjectId,
            red: "SubTodo"
        }]

// ----------- model creation --------------
const User = mongoose.model('User', userSchema);

// custom methods
// must be used with object/instance of the model attached (userSchema here)
userSchema.methods.sayHi = function () {
  console.log(`Hi, I'm ${this.name}`);
};

// -------------- virtuals -------------
userSchema.virtual('info').get(function () {
  return `${this.name} (${this.age})`;
});
```



