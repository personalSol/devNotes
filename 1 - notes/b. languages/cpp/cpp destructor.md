---
status: newBorn
related-links: 
created: 2025-05-22T15:02
updated: 2025-07-07T17:27
---
---


> [!SUMMARY] Summary
> - both constructor and destructuure should be in public access modifier
> - used to release heap memory as stack memory gets automatically freed when the program ends
> - also use to close file that we opened using constructor
> - only one in a class
> - gets automatically called so we don't need to call it
> - it doesn't run for dynamic objects which we create using `new` keyword
> 	- so to release their memory we hav to use `data <objName>` manually in main and that calls the destructor 


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