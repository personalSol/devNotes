---
status: newBorn
related-links: 
created: 2025-07-14T20:03
updated: 2025-07-14T20:03
---
---

- for 99% of things it's time complexity is O(1)
- for very very rare worst case it's O(n)

### STL `unordered_multiset` in C++

- An **unordered_multiset** is an STL associative container similar to a `multiset`, but stores elements in **no particular order**.
- It allows **duplicate elements**.
- Internally implemented using **hash tables**.
- Most operations have **average-case O(1)** time complexity.

---

### Syntax
```cpp
unordered_multiset<object_type> variable_name;
```

---

### Commonly Used Functions

1. **`insert()`** – Inserts an element into the container.
```cpp
unordered_multiset<int> s;
s.insert(1);
s.insert(2);
```

2. **`begin()`** – Returns an iterator to the first element.
```cpp
s.begin();
```

3. **`end()`** – Returns an iterator to the theoretical element after the last.
```cpp
s.end();
```

4. **`count()`** – Returns the number of occurrences of a specific element.
```cpp
s.count(2); // returns 1 or more depending on occurrences
```

5. **`clear()`** – Removes all elements from the container.
```cpp
s.clear();
```

6. **`find()`** – Returns an iterator to the first occurrence of the element.
```cpp
if (s.find(2) != s.end())
    cout << "found";
```

7. **`erase()`** – Erases a single element or a range.
```cpp
s.erase(s.begin());
```

8. **`size()`** – Returns the number of elements.
```cpp
s.size();
```

9. **`empty()`** – Checks if the container is empty.
```cpp
s.empty();
```

---

### Code Example
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    unordered_multiset<int> s;
    for (int i = 1; i <= 10; i++) {
        s.insert(i);
    }
    s.insert(5); // duplicate

    cout << "Elements present in the unordered multiset: ";
    for (auto it = s.begin(); it != s.end(); it++) {
        cout << *it << " ";
    }
    cout << endl;

    for (auto it : s) {
        cout << it << " ";
    }
    cout << endl;

    int n = 2;
    if (s.find(n) != s.end())
        cout << n << " is present in unordered multiset" << endl;

    s.erase(s.begin());
    cout << "Elements after deleting the first element: ";
    for (auto it = s.begin(); it != s.end(); it++) {
        cout << *it << " ";
    }
    cout << endl;

    cout << "The size of the unordered multiset is: " << s.size() << endl;

    if (!s.empty())
        cout << "The unordered multiset is not empty" << endl;
    else
        cout << "The unordered multiset is empty" << endl;

    s.clear();
    cout << "Size of the unordered multiset after clearing all the elements: " << s.size();
}
```


