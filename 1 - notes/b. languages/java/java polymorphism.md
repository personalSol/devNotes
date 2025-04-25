---
status: newBorn
related-links:
  - "[[Java-MOC]]"
created: 2025-04-20T18:11
updated: 2025-04-24T21:53
---
---

**Polymorphism** means "**many forms**". In Java, it allows **objects to behave differently based on their actual type**, even when they’re accessed through a common interface or superclass.

In simple terms:

> You can use **one method name**, but it can do **different things** depending on the object.

---

### ☕ Types of Polymorphism in Java

#### 1. **Compile-time Polymorphism** (a.k.a. Method Overloading)

- Same method name
- but, different parameters
	- different parameter types
		- we may or may not have to change the return type. we can explicitly change type or it may change implicitly
	- different number of parameters
	- doesn’t depend solely on return type
	    - Means you can’t create two different methods with everything same and just return type as the difference.
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

[[@Override in detail]]

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




# Reference
`related tags + notes + source + link(if any)`
 

- 