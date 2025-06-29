---
status: newBorn
related-links: 
created: 2025-06-28T10:17
updated: 2025-06-28T10:17
---
---

* **What is an Iterator?**

  * An iterator is not a basic data type like `int` or `float`.
  * It is an object that works like a pointer.
  * It helps you go through the elements of containers like `vector`, `map`, `set`, etc.

* **How to Define an Iterator**

  * Each container has its own type of iterator.
  * Example:

```cpp
vector<int>::iterator it;             // for vector
map<string, int>::iterator it;        // for map
```

* **Using an Iterator**

  * Start from `begin()` and stop at `end()`.
  * Example:

```cpp
vector<int> v = {1, 2, 3};
for (vector<int>::iterator it = v.begin(); it != v.end(); ++it) {
    cout << *it << " ";
}
```

![[cpp vectors basic#^bdu7yv]]

