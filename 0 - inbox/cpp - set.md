---
status: newBorn
related-links: 
created: 2025-07-14T12:06
updated: 2025-07-14T12:06
---
---

### STL `set` in C++

- A **set** is an STL container that stores 
	- **unique elements** 
	- in a **sorted (ascending) order**.
- Each operation (insert, delete, find) takes **O(log n)** time on average.
- behind the scene it's mantained in a tree structure ( will learn more about this as we go )

---

### Syntax
```cpp
set<object_type> variable_name;
```

---

### Commonly Used Functions

1. **`insert()`** – Inserts an element into the set.
```cpp
set<int> s;
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

4. **`count()`** – Returns `1` if the element exists, else `0`.
```cpp
s.count(2); // returns 1 if 2 is in the set
```

5. **`clear()`** – Removes all elements from the set.
```cpp
s.clear();
```

6. **`find()`** – Returns iterator to the element if found, else `end()`.
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

9. **`empty()`** – Checks if the set is empty.
```cpp
s.empty();
```

---

### Code Example
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    set<int> s;
    for (int i = 1; i <= 10; i++) {
        s.insert(i);
    }

    cout << "Elements present in the set: ";
    for (auto it = s.begin(); it != s.end(); it++) {
        cout << *it << " ";
    }
    cout << endl;

    for (auto it : s)
        cout << it << " ";
    cout << endl;

    int n = 2;
    if (s.find(n) != s.end())
        cout << n << " is present in set" << endl;

    s.erase(s.begin());
    cout << "Elements after deleting the first element: ";
    for (auto it = s.begin(); it != s.end(); it++) {
        cout << *it << " ";
    }
    cout << endl;

    cout << "The size of the set is: " << s.size() << endl;

    if (!s.empty())
        cout << "The set is not empty" << endl;
    else
        cout << "The set is empty" << endl;

    s.clear();
    cout << "Size of the set after clearing all the elements: " << s.size();
}
```

