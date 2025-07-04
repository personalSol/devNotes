---
status: newBorn
related-links: 
created: 2025-07-03T07:50
updated: 2025-07-03T08:05
---
---

- `sizeof` returns the size in **bytes**.
- The size of a class object includes:
    - All **non-static** member variables
    - **Padding** for alignment
- `sizeof` does **not** include dynamically allocated memory (e.g., if you use `new` or pointers inside the object).
- empty class's object has a by default size of 1 byte
- a basic rule: `sizeof` is always divisible by the byte size of biggest variable inside object's class. like if the biggest size variable inside class is int then all the sizeof of that object must be a mutiple of int

## 🧵 Padding for Alignment in C++

### 📌 What is Padding?

* Padding is extra memory added between struct/class members by the compiler.
* Ensures proper memory alignment as required by the CPU architecture.
* Improves performance and prevents misaligned access errors on certain platforms.

### ✅ Why Alignment Matters

* CPUs prefer data aligned to boundaries (like 2, 4, or 8 bytes).
* Misalignment can lead to slower access or runtime errors.
* Compilers insert padding to align members correctly.

### 🧠 Example: Misaligned Structure

```cpp
struct A {
    char c;     // 1 byte
    int i;      // 4 bytes
};
```

* `char c` starts at offset 0
* 3 bytes of padding inserted after `char`
* `int i` starts at offset 4
* **Total size = 8 bytes**

```cpp
sizeof(A); // returns 8
```

### 🔁 Reordering to Reduce Padding

```cpp
struct B {
    int i;      // 4 bytes
    char c;     // 1 byte
};
```

* Still requires padding after `char c` to make total size a multiple of 4.
* **Total size = 8 bytes**

### ⚡ Best Practice

Arrange members from **largest to smallest** to minimize padding:

```cpp
struct C {
    double d;   // 8 bytes
    int i;      // 4 bytes
    char c;     // 1 byte
};
```

### 🧪 Inspecting Padding with `offsetof`

```cpp
#include <iostream>
#include <cstddef>

struct A {
    char c;
    int i;
};

int main() {
    std::cout << offsetof(A, c) << "\n"; // 0
    std::cout << offsetof(A, i) << "\n"; // 4
    std::cout << sizeof(A) << "\n";      // 8
}
```

### 📦 Summary

* Use `sizeof` to check total size.
* Use `offsetof` to inspect member offsets.
* Padding is automatically handled by the compiler.
* Optimizing member order can reduce memory usage.


