---
status: newBorn
related-links:
  - "[[Java-MOC]]"
created: 2025-04-12T16:18
updated: 2025-04-20T11:09
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


## Polymorphism

**Polymorphism** means "**many forms**". In Java, it allows **objects to behave differently based on their actual type**, even when they’re accessed through a common interface or superclass.

In simple terms:

> You can use **one method name**, but it can do **different things** depending on the object.

---

### ☕ Types of Polymorphism in Java

#### 1. **Compile-time Polymorphism** (a.k.a. Method Overloading)

- Same method name, **different parameters**
- Decided at **compile time**
```java
class Calculator {
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }
}
```
Both methods are called `add`, but they take different types of arguments.

#### 2. **Runtime Polymorphism** (a.k.a. Method Overriding)

- A subclass **overrides** a method from its superclass
- The actual method that runs is based on the **object type**, not the reference type
- Happens at **runtime**
- we use `@Override` at top of method when we rewrite the same method in different class. it's not complusory but preffered. 

```java
class Animal {
    void makeSound() {
        System.out.println("Some animal sound");
    }
}

class Dog extends Animal {
	@Override
    void makeSound() {
        System.out.println("Bark");
    }
}

class Cat extends Animal {
	@Override
    void makeSound() {
        System.out.println("Meow");
    }
}

public class Test {
    public static void main(String[] args) {
        Animal a;

        a = new Dog();
        a.makeSound();  // Output: Bark

        a = new Cat();
        a.makeSound();  // Output: Meow
    }
}
```


## Abstraction

> "Show only what’s important, and hide the messy details."

You **focus on _what_ an object does**, not _how_ it does it.

- You use abstract classes or interfaces to create abstraction.
- can create fields, constructor and full functions in abstract class.

```java
interface Animal {
    void makeSound();  // No details here
}

class Dog implements Animal {
	@Override
    public void makeSound() {
        System.out.println("Bark");
    }
}
```

- The `Animal` interface says: "Every animal can make a sound" — but **doesn’t say how**.
- Each animal (like `Dog`) decides **how** it makes that sound.

---

### ✅ Why Use Abstraction?

- Makes code **cleaner** and easier to understand
- Hides **unnecessary complexity**
- Helps in designing **reusable and flexible** code

## abstraction vs encapsulation

| Feature      | Encapsulation                     | Abstraction                           |
| ------------ | --------------------------------- | ------------------------------------- |
| Hides        | Data (fields)                     | Implementation details (logic)        |
| Focuses on   | Data protection & access control  | Functionality design & simplification |
| Achieved via | `private` fields, getters/setters | `abstract` classes, `interface`s      |
| Goal         | Safely expose the internals       | Show only necessary parts to the user |

```java

// encapsulation

class Account {
    private double balance;  // hidden data

    public void deposit(double amount) {
        if (amount > 0) balance += amount;
    }

    public double getBalance() {
        return balance;
    }
}


// abstraction

abstract class Animal {
    abstract void makeSound();  // No implementation
}

class Dog extends Animal {
    void makeSound() {
        System.out.println("Bark");
    }
}

```


# Reference
`related tags + notes + source + link(if any)`
 

- 