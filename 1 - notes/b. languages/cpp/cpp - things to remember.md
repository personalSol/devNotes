---
status: newBorn
related-links: "[[Cpp-MOC]]"
created: 2025-05-15T07:41
updated: 2025-07-14T19:06
---
---

### methods

- sizeof(`<datatype>`) || sizeof(`<any variable>`)
	- returns size of data type in bytes
	- can even give size of pointer
	```cpp
	#include <iostream>
	using namespace std;

	int main() {
	    cout << "Size of char: " << sizeof(char) << " byte(s)" << endl;
	    cout << "Size of int: " << sizeof(int) << " byte(s)" << endl;
	    cout << "Size of long: " << sizeof(long) << " byte(s)" << endl;
	    cout << "Size of float: " << sizeof(float) << " byte(s)" << endl;
	    cout << "Size of double: " << sizeof(double) << " byte(s)" << endl;
	    return 0;
	}

	```
- .size()
	- to get the length of array & vectors
	![[cpp arrays#^tmhsvv]]

- `#include<bits/stdc++.h>` is used for fast import of all libraries ^wcfomo
- sort in cpp
	- std::sort does not return a new array; it sorts the array in place and returns `void`.
	- You cannot assign the result of sort(b) to an array.


- by default all properties and methods in class are private
 

### other things

- ` == ` is the **only equality operator** used to compare values.
- There is **no ` === `** operator in C++.


# Reference
`related tags + notes + source + link(if any)`
 

- 