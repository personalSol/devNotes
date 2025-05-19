---
status: newBorn
related-links:
  - "[[Cpp-MOC]]"
created: 2025-05-09T08:55
updated: 2025-05-19T09:56
---
---

- fixed in size
- stores similar type of data
- zero based indexing
- location of first ( zeroth index ) can be anywhere
	- but the second ( 1st index ) will be right after zeroth and so on
- in a array which is not initialized, c++ throws a random garbage value
![[cpp call by reference and call by value#^fqmpwk]]



code
```cpp
int arr1[5] // 1d array of size 5 from 0 to 4
int arr2[2][10] // 2d array of 2 rows and 10 columns

// initialization
int a[3] = {1, 2, 3};
float b[] = {1.1, 2.2, 3.3};  // size is inferred
char c[4] = {'a', 'b', 'c', '\0'};

```



# Reference
`related tags + notes + source + link(if any)`
 

- 