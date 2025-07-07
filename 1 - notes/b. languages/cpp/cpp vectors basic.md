---
status: newBorn
related-links: 
created: 2025-06-28T10:11
updated: 2025-06-28T10:31
---
---

- is like a array which is dynamic in size
	- variable size
	- even if it's defined during declaration
- emplace vs push
	- both emplace and push only inserts one value at a time.
		- it can be a pair ( which in vector will be one value ) or a normal primitive one value
	- emplace_back is faster than push back
	- have to include `{}` in pair for push but in emplace we don't have to

- iterator:  ^bdu7yv
	- points to the memory where the element is
	- we make iterator by adding `::iterator` in `vector<datatype>::iterator` like this
	- we have:
		- `<vector_name>.begin()` iterator : points at address of zeroth value
		- `<vector_name>.end()` iterator : points at address of last value + 1 ( so we have to do it-- before accessing the value )
	- rarely used ones
		- `<vector_name>.rend()` iterator : points to zeroth - 1
		- `<vector_name>.rbegin()` iterator : points to last index, if we do ++ then it moves to last index - 1 
