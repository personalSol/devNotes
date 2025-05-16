---
status: newBorn
related-links:
  - "[[Cpp-MOC]]"
created: 2025-05-15T17:09
updated: 2025-05-15T23:29
---
---

# Struct vs Class in C++

  

## 🔹 What's a `struct`?

A `struct` is a user-defined data type that groups related variables. Originally used in C for simple data grouping.

```c

struct Student {
    int roll;
    char name[50];
    float marks;
};

```

  

## 🔹 `struct` vs `class` in C++

  

| Feature                | `struct`               | `class`                |
|------------------------|------------------------|------------------------|
| Default access         | `public`               | `private`              |
| Inheritance default    | `public`               | `private`              |
| Member functions       | ✅ Supported           | ✅ Supported           |
| Constructors/Destructors | ✅ Supported        | ✅ Supported           |


> In C++, `struct` and `class` are nearly identical in capability.  

---

## 🔧 Example: Same functionality in `struct` and `class`
  

### ✅ Using `struct`

```cpp
struct Student {
    int roll;
    string name;
  
    Student(int r, string n) : roll(r), name(n) {}

    void display() {
        cout << roll << " " << name << endl;
    }
};
```

### ✅ Using `class`

```cpp
class Student {
private:
    int roll;
    string name;
  
public:
    Student(int r, string n) : roll(r), name(n) {}

    void display() {
        cout << roll << " " << name << endl;
    }
};
```

---

## ✅ When to Use What?


- Use `struct` for **simple data containers** (e.g., `Point`, `RGB`)
- Use `class` for **encapsulation and behavior** (e.g., `StudentSystem`, `BankAccount`)

---
## 🧠 Final Takeaway


- `struct` is best for plain data with public access.
- `class` is best for complex types with hidden internals.