---
status: newBorn
related-links:
  - "[[Java-MOC]]"
created: 2025-04-20T11:12
updated: 2025-04-20T17:12
---
---

#### 1. **Static vs Non-Static**

- **Static methods** belong to the **class**, not an object.
- **Non-static methods** belong to **instances (objects)** of the class.

#### 2. **Why can't you call a non-static method from a static method directly?**

- Static methods don’t have access to `this` (no object context).
- Non-static methods need an object to run — they rely on `this`.
- Solution: either make the method static or call it using an object.

```java
MyClass obj = new MyClass();
obj.myMethod(); // ✅
```

#### 3. **Calling non-static from non-static (no issue)**

- Non-static methods are always called **on an object**.
- Inside non-static methods, Java gives you an automatic reference to the object: `this`.

### ✅ **What is `this`?**

- `this` is an **implicit reference** to the **current instance** of the class.
- It is available only inside **non-static methods or constructors**.
- It's used to:
    - Refer to current object's fields/methods.
    - Resolve naming conflicts.
    - Support method chaining.

```java
this.name = name; // distinguishes instance variable from parameter
```

### ✅ **Static methods don't have `this`**

- Because they’re not tied to any object.
- You must explicitly create an object to call any non-static members.

---

### ✅ Access Modifier Confusion (Clarified)

- Your error wasn’t due to the method being `default` (package-private).
- It was due to trying to call a **non-static method inside a static method** without an object.



# Reference
`related tags + notes + source + link(if any)`
 

- [[tG this keyword]]
- [[tG static vs non static]]
- [[tG static]]
- [[tG non static methods]]
- 