---
status: newBorn
related-links: 
created: 2025-07-13T11:06
updated: 2025-07-13T11:06
---
---

### STL `priority_queue` in C++

- A **priority queue** is a container adaptor that provides constant time lookup of the largest (or smallest) element.
- It can be used as a **max-heap** (default, for the largest) or a **min-heap**.( for the smallest)

---

### Syntax
```cpp
// Max-heap (default)
priority_queue<object_type> variable_name;

// Min-heap
priority_queue<object_type, vector<object_type>, greater<object_type>> variable_name;
```

---

### Commonly Used Functions

1. **`push()`** – Inserts an element into the priority queue.
```cpp
priority_queue<int> pq;
pq.push(110);
pq.push(220);
```

2. **`pop()`** – Removes the top element (highest for max-heap, lowest for min-heap).
```cpp
pq.pop();
```

3. **`top()`** – Returns the top element.
```cpp
pq.top();
```

4. **`emplace()`** – Constructs and inserts an element.
```cpp
pq.emplace(1);
pq.emplace(2);
```

5. **`size()`** – Returns the number of elements.
```cpp
pq.size();
```

6. **`empty()`** – Checks if the priority queue is empty.
```cpp
pq.empty();
```

---

### Code Example
```cpp
#include <bits/stdc++.h>
using namespace std;

void printpriorityqueue(priority_queue<int> pq) {
    priority_queue<int> pq2 = pq;
    while (!pq2.empty()) {
        cout << pq2.top() << "\n";
        pq2.pop();
    }
}

int main() {
    priority_queue<int> pq;
    for (int i = 1; i <= 5; i++)
        pq.push(i);

    cout << "The elements of the priority queue are:" << endl;
    printpriorityqueue(pq);

    cout << "The size of the priority queue: " << pq.size() << endl;
    cout << "The top element of the priority queue: " << pq.top() << endl;
    cout << "Pop the top element: " << endl;

    pq.pop();
    printpriorityqueue(pq);
}
```


