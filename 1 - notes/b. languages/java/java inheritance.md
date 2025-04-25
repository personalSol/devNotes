---
status: newBorn
related-links:
  - "[[Java-MOC]]"
created: 2025-04-20T18:11
updated: 2025-04-24T21:52
---
---

**Inheritance** means one class **inherits** or **gets** the properties and behaviors (methods) of another class.
It’s like how a **child inherits features from a parent** — like eye color or hair type.

- java have single inheritance
- multiple inheritance
- java doesn't support multilevel inheritance
	- the solution is interfaces


---

### 🧱 In Java terms:

- A **child class** (also called _subclass_) gets everything from a **parent class** (also called _superclass_)
- We use the keyword `extends` to do this

---

### ✅ Why use inheritance?

- **Reusability**: Don’t repeat code — just reuse the parent class
- **Organization**: Keep common features in one place
- **Flexibility**: You can add or change behavior in the child class
    

---

### 📦 Simple Java Example:

```java
// Parent class
public class Animal {
    void makeSound() {
        System.out.println("Some generic sound");
    }
}

// Child class
public class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks");
    }
}
```

🧪 Using the classes:
```java
Dog d = new Dog();
d.makeSound();  // Inherited from Animal
d.bark();       // From Dog class

// output:
// Some generic sound
// Dog barks
```




# Reference
`related tags + notes + source + link(if any)`
 

- 