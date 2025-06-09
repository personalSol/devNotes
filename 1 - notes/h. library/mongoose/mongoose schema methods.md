---
status: newBorn
related-links: 
created: 2025-06-01T18:43
updated: 2025-06-04T08:26
---
---

> remember:: mongoose custom schema methods are used on document object and not on schema itself. 

In Mongoose, `schema.methods` lets you define **instance methods**—custom methods that can be called on individual documents created from a model.

```js
const userSchema = new mongoose.Schema({
  name: String,
  email: String
});

// Define an instance method
userSchema.methods.sayHello = function () {
  return `Hello, my name is ${this.name}`;
};

const User = mongoose.model('User', userSchema);

// Usage:
const user = new User({ name: 'Alice', email: 'alice@example.com' });
console.log(user.sayHello()); // "Hello, my name is Alice"
```

### Key point:

- These methods are available **on document instances**, not on the model itself.
	- as they are not static methods
