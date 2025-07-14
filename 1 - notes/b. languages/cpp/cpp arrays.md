---
status: newBorn
related-links:
  - "[[Cpp-MOC]]"
created: 2025-05-09T08:55
updated: 2025-07-14T12:59
---
---

- fixed in size
- stores similar type of data
- zero based indexing
- location of first ( zeroth index ) can be anywhere
	- but the second ( 1st index ) will be right after zeroth and so on
- in a array which is not initialized, c++ throws a random garbage value
- `.size()` and any other array function cannot be used by plain array. for that we must use class array ^tmhsvv

![[cpp call by reference and call by value#^fqmpwk]] 



code
```cpp
// this is plain array
int arr1[5] // 1d array of size 5 from 0 to 4
int arr2[2][10] // 2d array of 2 rows and 10 columns

// this is class array
array<double, 5> arr3 = {1,2,3,4,5};

// initialization
int a[3] = {1, 2, 3};
float b[] = {1.1, 2.2, 3.3};  // size is inferred
char c[4] = {'a', 'b', 'c', '\0'};

// to find length in normal plain array
cout << (sizeof(a) / sizeof(a[0]));

```



# Reference
`related tags + notes + source + link(if any)`
 

- 