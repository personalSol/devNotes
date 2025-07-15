---
status: newBorn
related-links: 
created: 2025-07-15T09:48
updated: 2025-07-15T09:48
---
---

### STL `multimap` in C++

- A **multimap** is an associative container similar to `map`, but **allows duplicate keys**.
- Each key can map to **multiple values**.
- Elements are automatically sorted based on the key.

---

### Syntax
```cpp
multimap<object_type, object_type> variable_name;
```

---

### Commonly Used Functions

1. **`insert()`** – Inserts a key-value pair into the multimap.
```cpp
multimap<int, int> mp;
mp.insert({1, 10});
mp.insert({2, 20});
```

2. **`begin()`** – Returns an iterator to the first element.
```cpp
mp.begin();
```

3. **`end()`** – Returns an iterator to the theoretical element after the last.
```cpp
mp.end();
```

4. **`clear()`** – Removes all elements from the multimap.
```cpp
mp.clear();
```

5. **`find()`** – Returns an iterator to the first occurrence of a given key.
```cpp
if (mp.find(2) != mp.end())
    cout << "found";
```

6. **`erase()`** – Removes an element by key, iterator, or range.
```cpp
mp.erase(2);
mp.erase(mp.begin());
```

7. **`size()`** – Returns the number of elements.
```cpp
mp.size();
```

8. **`empty()`** – Checks if the multimap is empty.
```cpp
mp.empty();
```

---

### Code Example
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    multimap<int, int> mp;
    for (int i = 1; i <= 5; i++) {
        mp.insert({i, i * 10});
    }
    mp.insert({4, 40}); // duplicate key

    cout << "Elements present in the multimap: " << endl;
    cout << "Key\tElement" << endl;
    for (auto it = mp.begin(); it != mp.end(); it++) {
        cout << it->first << "\t" << it->second << endl;
    }

    for (auto it : mp) {
        cout << it.first << "\t" << it.second << endl;
    }

    int n = 2;
    if (mp.find(n) != mp.end())
        cout << n << " is present in multimap" << endl;

    mp.erase(mp.begin());
    cout << "Elements after deleting the first element: " << endl;
    cout << "Key\tElement" << endl;
    for (auto it = mp.begin(); it != mp.end(); it++) {
        cout << it->first << "\t" << it->second << endl;
    }

    cout << "The size of the multimap is: " << mp.size() << endl;

    if (!mp.empty())
        cout << "The multimap is not empty" << endl;
    else
        cout << "The multimap is empty" << endl;

    mp.clear();
    cout << "Size of the multimap after clearing all the elements: " << mp.size();
}
```


