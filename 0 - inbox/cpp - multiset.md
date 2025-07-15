---
status: newBorn
related-links: 
created: 2025-07-14T20:02
updated: 2025-07-14T20:02
---
---

### STL `multiset` in C++

- A **multiset** is an STL associative container similar to a `set`, but **allows duplicate elements**.
- Elements are automatically sorted in ascending order.
- Most operations take **O(log n)** time.

---

### Syntax
```cpp
multiset<object_type> variable_name;
```

---

### Commonly Used Functions

1. **`insert()`** – Inserts an element into the multiset.
```cpp
multiset<int> s;
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

4. **`count()`** – Returns the count of a particular element.
```cpp
s.count(2); // returns 1 or more depending on how many 2s exist
```

5. **`clear()`** – Removes all elements from the multiset.
```cpp
s.clear();
```

6. **`find()`** – Returns iterator to the first occurrence of the element.
```cpp
if (s.find(2) != s.end())
    cout << "found";
```

7. **`erase()`** – Removes all occurrences of a value or by iterator.
```cpp
s.erase(s.begin());
```

8. **`size()`** – Returns the number of elements.
```cpp
s.size();
```

9. **`empty()`** – Checks if the multiset is empty.
```cpp
s.empty();
```

---

### Code Example
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    multiset<int> s;
    for (int i = 1; i <= 10; i++) {
        s.insert(i);
    }
    s.insert(5); // duplicate element

    cout << "Elements present in the multiset: ";
    for (auto it = s.begin(); it != s.end(); it++) {
        cout << *it << " ";
    }
    cout << endl;

    for (auto it : s) {
        cout << it << " ";
    }
    cout << endl;

    int n = 2;
    if (s.find(2) != s.end())
        cout << n << " is present in multiset" << endl;

    s.erase(s.begin());
    cout << "Elements after deleting the first element: ";
    for (auto it = s.begin(); it != s.end(); it++) {
        cout << *it << " ";
    }
    cout << endl;

    cout << "The size of the multiset is: " << s.size() << endl;

    if (!s.empty())
        cout << "The multiset is not empty" << endl;
    else
        cout << "The multiset is empty" << endl;

    s.clear();
    cout << "Size of the multiset after clearing all the elements: " << s.size();
}
```


