---
status: newBorn
related-links: 
created: 2025-05-22T15:02
updated: 2025-05-22T15:02
---
---

### 🔧 What a Destructor Does:

- It's a **special function** that runs **automatically when an object is destroyed**.
- It's used to **clean up resources**, like memory, files, etc.

### ❗ Why the `~` symbol?

- The `~` (tilde) means it's a **destructor**.
- So `~Engine()` means “the destructor of the `Engine` class”.

```cpp
~Engine() {
    cout << "Engine: Destructor called." << endl;
}
```

This line tells us when the `Engine` object is being deleted (destroyed), just for visibility.