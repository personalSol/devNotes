---
status: newBorn
related-links:
  - "[[Cpp-MOC]]"
  - "[[cpp oops]]"
created: 2025-05-15T19:58
updated: 2025-05-18T17:39
---
---

### ✅ Compile-Time Polymorphism
Function/Operator overloading.

```cpp
class Printer {
public:
    void print(int i) {}
    void print(std::string s) {}
};
```

### ✅ Runtime Polymorphism (Virtual Functions)
Use `virtual` in base class, override in derived.

```cpp
class Animal {
public:
    virtual void speak() { std::cout << "Animal"; }
};

class Dog : public Animal {
public:
    void speak() override { std::cout << "Dog"; }
};

Animal* a = new Dog();
a->speak(); // Outputs: Dog
```

---


# Reference
`related tags + notes + source + link(if any)`
 

- 