---
status: newBorn
related-links:
  - "[[Cpp-MOC]]"
  - "[[cpp stl]]"
created: 2025-05-12T17:03
updated: 2025-06-07T09:51
---
---

- stores a pair
- element inside a pair can be a pair itself
- can we used as a datatype

```cpp
// Pairs
void explainPair() {
    pair<int, int> p = {1, 3};
    cout << p.first << " " << p.second << endl; // to access first and second elements
    pair<int, pair<int, int>> p2 = {1, {3, 4}};
    cout << p2.first << " " << p2.second.second << " " << p2.second.first << endl;
    pair<int, int> arr[] = { {1, 2}, {2, 5}, {5, 1} };
    cout << arr[1].second << endl;
}

```



# Reference
`related tags + notes + source + link(if any)`
 

- 