---
status: newBorn
related-links:
  - "[[Cpp-MOC]]"
  - "[[cpp stl]]"
created: 2025-05-12T17:03
updated: 2025-06-28T09:30
---
---
![[cpp - library#^7775xh]]
- stores a pair
- element inside a pair can be a pair itself
- we can also make an array of type paid where each element of array will be a pair
  * Pair is used to combine together two values that may be of different data types.
  * It provides a way to store two heterogeneous objects as a single unit.
  * Useful for storing tuples.
  * Consists of two data elements or objects.

* **Syntax**
  ```cpp
  pair<data_type1, data_type2> pair_name;
  ```

* **Most Used Functions**
  * **make\_pair()**
    * Creates a value pair without explicitly specifying data types.
    * **Syntax**:
  * **swap()**
    * Swaps the contents of one pair object with another.
    * Pairs must be of the same kind.
    * **Syntax**:

**CODE**

```cpp
void explainPair() {
    pair<int, int> p = {1, 3};
    cout << p.first << " " << p.second << endl; // to access first and second elements
    pair<int, pair<int, int>> p2 = {1, {3, 4}};
    cout << p2.first << " " << p2.second.second << " " << p2.second.first << endl;
    pair<int, int> arr[] = { {1, 2}, {2, 5}, {5, 1} };
    cout << arr[1].second << endl;

	// methods
	pair1 = make_pair(data1, data2);
	pair1.swap(pair2);
}
```

