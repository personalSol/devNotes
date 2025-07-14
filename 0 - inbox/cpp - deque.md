---
status: newBorn
related-links: 
created: 2025-07-13T10:54
updated: 2025-07-13T10:54
---
---

### STL `deque` in C++

- A **Double Ended Queue (Deque)** is a queue data structure that allows:
  - Insertion and deletion at **both** the front and the rear ends.

---

### Syntax
```cpp
deque<object_type> variable_name;
```

---

### Commonly Used Functions

1. **`push_back()`** – Inserts an element at the end.
```cpp
deque<int> dq;
dq.push_back(110);
dq.push_back(220);
```

2. **`push_front()`** – Inserts an element at the front.
```cpp
dq.push_front(110);
dq.push_front(220);
```

3. **`pop_back()`** – Deletes the last element.
```cpp
dq.pop_back();
```

4. **`pop_front()`** – Deletes the front element.
```cpp
dq.pop_front();
```

5. **`front()`** – Returns a reference to the first element.
```cpp
dq.front();
```

6. **`back()`** – Returns a reference to the last element.
```cpp
dq.back();
```

7. **`size()`** – Returns the number of elements in the deque.
```cpp
dq.size();
```

8. **`empty()`** – Checks if the deque is empty.
```cpp
dq.empty();
```

---

### Code Example
```cpp
#include <bits/stdc++.h>
using namespace std;

void printdeque(deque<int> dq) {
    deque<int>::iterator it;
    for (it = dq.begin(); it != dq.end(); it++) {
        cout << *it << " ";
    }
    cout << endl;

    for (auto it : dq)
        cout << it << " ";
    cout << endl;
}

int main() {
    deque<int> dq;
    dq.push_back(10);
    dq.push_back(20);
    dq.push_front(30);
    dq.push_front(40);
    dq.push_front(50);

    cout << "The elements in the deque are: ";
    printdeque(dq);

    cout << "The size of the deque is: " << dq.size() << endl;
    cout << "The first element in the deque: " << dq.front() << endl;
    cout << "Deleting the first element" << endl;
    dq.pop_front();
    printdeque(dq);

    cout << "The last element of the deque: " << dq.back() << endl;
    cout << "Deleting the last element" << endl;
    dq.pop_back();
    printdeque(dq);
}


