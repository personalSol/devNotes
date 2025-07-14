---
status: newBorn
related-links: 
created: 2025-07-13T10:27
updated: 2025-07-13T10:43
---
---

### STL `list` in C++

- A `list` in STL is a contiguous container that allows:
  - Inserting and erasing elements in constant time.
  - Iterating in both forward and backward directions.
- It is implemented as a linear doubly linked list in memory.

---

### Syntax
```cpp
list<object_type> variable_name;
```

---

### Commonly Used Functions

1. **`push_back()`** – Inserts an element at the end.
```cpp
list<int> li;
li.push_back(110);
li.push_back(220);
```

2. **`push_front()`** – Inserts an element at the front.
```cpp
li.push_front(110);
li.push_front(220);
```

3. **`pop_back()`** – Deletes the last element.
```cpp
li.pop_back();
```

4. **`pop_front()`** – Deletes the front element.
```cpp
li.pop_front();
```

5. **`front()`** – Returns a reference to the first element.
```cpp
li.front();
```

6. **`back()`** – Returns a reference to the last element.
```cpp
li.back();
```

7. **`reverse()`** – Reverses the list + modifies it
```cpp
li.reverse();
```

8. **`sort()`** – Sorts the list in ascending order.
```cpp
li.sort();
```

9. **`size()`** – Returns the number of elements.
```cpp
li.size();
```

10. **`empty()`** – Checks if the list is empty.
```cpp
li.empty();
```

---

### Code Example
```cpp
#include <bits/stdc++.h>
using namespace std;

void printlist(list<int> li) {
    list<int>::iterator it;
    for (it = li.begin(); it != li.end(); it++) {
        cout << *it << " ";
    }
    cout << endl;

	// here auto can be of type int
	// it's a range based for loop
	// it directly refers to the value and not the iterator
	// hence we don't need pointer
    for (auto it : li) 
        cout << it << " ";
    cout << endl;
}

int main() {
    list<int> li;
    li.push_back(10);
    li.push_back(20);
    li.push_front(30);
    li.push_front(40);
    li.push_front(50);

    cout << "The elements in the list are: ";
    printlist(li);

    cout << "Reversing the list: ";
    li.reverse();
    printlist(li);

    cout << "Sorting the list: ";
    li.sort();
    printlist(li);

    cout << "The size of the list is: " << li.size() << endl;
    cout << "The first element in the list: " << li.front() << endl;
    cout << "Deleting the first element" << endl;
    li.pop_front();
    printlist(li);

    cout << "The last element of the list: " << li.back() << endl;
    cout << "Deleting the last element" << endl;
    li.pop_back();
    printlist(li);
}
```

