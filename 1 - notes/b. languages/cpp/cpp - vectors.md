---
status: newBorn
related-links: []
created: 2025-05-12T17:27
updated: 2025-06-08T10:02
---
---

- is like a array which is dynamic in size
	- variable size
	- even if it's defined during declaration
- emplace vs push
	- emplace_back is faster than push back 
	- have to include `{}` in pair for push but in emplace we don't have to
- iterator: points to the memory where the element is. 
	- we make iterator by adding `::iterator` in `vector<datatype>::iterator` like this
	- we have:
		- <vector_name>.begin() iterator : points at address of zeroth value
		- `vector_name>.end()` iterator : points at address of last value + 1 ( so we have to do it-- before accessing the value )
		- rarely used ones
			- `<vector_name>.rend()` iterator : points to zeroth - 1
			- `<vector_name>.rbegin()` iterator : points to last index, if we do ++ then it moves to last index - 1 

```cpp
void explainVector() {

    vector<int> v;

    v.push_back(1);
    v.emplace_back(2);

    vector<pair<int, int>> vec;

    v.push_back({1, 2});
    v.emplace_back(1, 2);

    vector<int> v(5, 100);

    vector<int> v(5);

    vector<int> v1(5, 20);
    vector<int> v2(v1);

    vector<int>::iterator it = v.begin();

    it++;
    cout << *(it) << " ";
}

```


# Reference
`related tags + notes + source + link(if any)`
 

- 