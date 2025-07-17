---
status: newBorn
related-links: 
created: 2025-07-13T10:57
updated: 2025-07-13T10:57
---
---

### STL `stack` in C++

- A **stack** is a non-primitive linear data structure.
- It follows **LIFO (Last-In-First-Out)** principle:
  - The element inserted last is the first to be removed.
- All operations are performed at **one end**: the **top of the stack (TOS)**.

---

### Syntax
```cpp
stack<object_type> variable_name;
```

---

### Commonly Used Functions

1. **`push()`** – Inserts an element on the top of the stack.
```cpp
stack<int> s;
s.push(110);
s.push(220);
```

2. **`pop()`** – Removes the top element.
```cpp
s.pop();
```

3. **`top()`** – Returns the element at the top.
```cpp
s.top();
```

4. **`emplace()`** – Constructs and inserts an element at the top.
```cpp
s.emplace(1);
s.emplace(2);
```

5. **`size()`** – Returns the number of elements.
```cpp
s.size();
```

6. **`empty()`** – Checks if the stack is empty.
```cpp
s.empty();
```

---

### Code Example
```cpp
#include <bits/stdc++.h>
using namespace std;

void printstack(stack<int> s1) {
    stack<int> s2 = s1;
    while (!s2.empty()) {
        cout << s2.top() << "\n";
        s2.pop();
    }
}

int main() {
    stack<int> s;
    for (int i = 1; i <= 5; i++)
        s.push(i);

    cout << "The elements of the stack are:" << endl;
    printstack(s);

    cout << "The size of the stack: " << s.size() << endl;
    cout << "The top element of the stack: " << s.top() << endl;
    cout << "Pop the top element: " << endl;

    s.pop();
    printstack(s);
}


