---
status: newBorn
related-links: 
created: 2025-06-28T10:14
updated: 2025-06-28T10:14
---
---



* **Input Iterator**

    * Can only read items one time.
    * Example: `istream_iterator`

  * **Output Iterator**

    * Can only write items one time.
    * Example: `ostream_iterator`

  * **Forward Iterator**

    * Can read and write.
    * Moves only forward.
    * Example: `forward_list::iterator`

  * **Bidirectional Iterator**

    * Can go forward and backward.
    * Example: `list::iterator`, `map::iterator`

  * **Random Access Iterator**

    * Can jump anywhere, supports +, -, \[].
    * Fastest type.
    * Example: `vector::iterator`, `deque::iterator`

* **Reverse Iterators**

  * These go backwards through the container.
  * You must use `reverse_iterator` type, not regular iterator.
  * Example:

```cpp
vector<int>::reverse_iterator rit = v.rbegin();
while (rit != v.rend()) {
    cout << *rit << " ";
    ++rit;
}

// This will not work:
vector<int>::iterator it = v.rend(); // ❌ wrong type
```
