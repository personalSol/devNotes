---
status: newBorn
related-links: 
created: 2025-07-13T11:00
updated: 2025-07-13T11:00
---
---

### STL `queue` in C++

- A **queue** is a linear data structure where:
  - Insertions happen at the **rear**.
  - Deletions happen at the **front**.
- It follows the **FIFO (First-In-First-Out)** principle.

---

### Syntax
```cpp
queue<object_type> variable_name;
```

---

### Commonly Used Functions

1. **`push()`** – Inserts an element at the rear.
```cpp
queue<int> q;
q.push(110);
q.push(220);
```

2. **`pop()`** – Removes the front element.
```cpp
q.pop();
```

3. **`front()`** – Returns a reference to the front element.
```cpp
q.front();
```

4. **`back()`** – Returns a reference to the rear element.
```cpp
q.back();
```

5. **`emplace()`** – Constructs and inserts an element at the rear.
```cpp
q.emplace(1);
q.emplace(2);
```

6. **`size()`** – Returns the number of elements in the queue.
```cpp
q.size();
```

7. **`empty()`** – Checks if the queue is empty.
```cpp
q.empty();
```

---

### Code Example
```cpp
#include <bits/stdc++.h>
using namespace std;

void printqueue(queue<int> q1) {
    queue<int> q2 = q1;
    while (!q2.empty()) {
        cout << q2.front() << "\n";
        q2.pop();
    }
}

int main() {
    queue<int> q;
    for (int i = 1; i <= 5; i++)
        q.push(i);

    cout << "The elements of the queue are:" << endl;
    printqueue(q);

    cout << "The size of the queue: " << q.size() << endl;
    cout << "The front element of the queue: " << q.front() << endl;
    cout << "The last element of the queue: " << q.back() << endl;
    cout << "Pop the front element: " << endl;

    q.pop();
    printqueue(q);
}
```


