---
status: newBorn
related-links: 
created: 2025-05-29T14:29
updated: 2025-05-29T14:29
---
---

#### ✅ `super()` and Inheritance

##### 🔹 What is `super()`?

- `super()` calls the parent class's constructor.
- Must be used **before** accessing `this` in a subclass constructor.

```js
class Animal {
  constructor(name) {
    this.name = name;
  }
}

class Dog extends Animal {
  constructor(name, breed) {
    super(name);        // Call to parent constructor
    this.breed = breed; // Subclass property
  }
}
```

##### 🔹 Purpose of `super()`

| Purpose                      | Explanation                                   |
| ---------------------------- | --------------------------------------------- |
| Initialize parent properties | Inherits values set in the parent constructor |
| Enable parent logic          | Parent may contain setup code                 |
| Prevent error                | Using `this` before `super()` throws an error |

---

#### ✅ Calling Parent Methods with `super.method()`

- You can call parent class methods using `super.methodName()`.

```js
class Animal {
  speak() {
    console.log("Animal sound");
  }
}

class Dog extends Animal {
  speak() {
    super.speak();     // Calls Animal's speak
    console.log("Dog barks");
  }
}
```

---


