---
status: newBorn
related-links: 
created: 2025-06-28T10:51
updated: 2025-06-28T10:51
---
---

### Most Used Vector Functions in C++

* **begin()** – Returns an iterator pointing to the first element of the vector.

```cpp
auto iterator = itr;
itr = v1.begin();
```

* **end()** – Returns an iterator pointing to the element *after* the last element of the vector.

```cpp
auto iterator = itr;
itr = v1.end();
```

* **push\_back()** – Inserts the given element at the end of the vector.

```cpp
vector<int> v1;
v1.push_back(1);
```

* **insert()** – Inserts an element at a specified position.
	* (position, number of times ( optional ), number)

```cpp
auto it = v1.begin();
v1.insert(it, 5); // inserting 5 at the beginning
v1.insert(it+1, 3, 10) // inserting 10, 10, 10 from 2nd position
```

* **erase()** – Removes an element from a specific position.

```cpp
vector<int> v1;
auto it = v1.begin();
v1.erase(it); // erasing the first element
```

* **pop\_back()** – Deletes the last element.

```cpp
v1.pop_back();
```

* **front()** – Returns a reference to the first element.

```cpp
v1.front();
```

* **back()** – Returns a reference to the last element.

```cpp
v1.back();
```

* **clear()** – Removes all elements from the vector.

```cpp
v1.clear();
```

* **empty()** – Checks whether the vector is empty.

```cpp
v1.empty();
```

* **size()** – Returns the number of elements in the vector.

```cpp
v1.size();
```


