---
status: newBorn
related-links: []
created: 2025-04-12T16:18
updated: 2025-04-12T21:50
---
---

## encapsulation

**Encapsulation** means **hiding the internal details** of how something works and only showing what’s necessary.

Think of it like a **TV remote** — you don’t know (or need to know) how it works inside. You just press buttons to control the TV.

---

### 💻 In Java terms:

- We **hide variables** inside a class using `private`
- We use **`get` and `set` methods** to access or change those variables

---

### ✅ Why use encapsulation?

- Protect data from being changed in the wrong way
- Control how data is accessed or updated
- Makes the code easier to manage and safer

---

### 📦 Simple Java Example:

```java
public class Person {
    // Private variable (hidden from outside)
    private String name;

    // Getter - to read the name
    public String getName() {
        return name;
    }

    // Setter - to change the name
    public void setName(String newName) {
        name = newName;
    }
}
```

🧪 Using the class:
```java
Person p = new Person();
p.setName("John");             // set the name
System.out.println(p.getName());  // get the name
```



## Inheritance

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
 
- [[tG not-tagged]]
- 