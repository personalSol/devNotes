---
status: newBorn
related-links: 
created: 2025-08-01T08:33
updated: 2025-08-01T08:33
---
---

- in recursion there are two types
	- parameterized 
		- where there is another spare variable in parameters which we can use to do calculations and return
		- in parameterized we can do print and return both
	- funcitonal
		- when we only have the limit variable ( one and only variable ). and because of that we have to use return of a function to store our answer
		- in this I think as we don't really have any variable to store and if printing can be complicated like first giving condition and then we will have to use the function inside printing as we don't store it anywhere so I don't think it's possible so
			- we return and not print

```cpp

// funcitonal
class Solution{	
	public:
		int NnumbersSum(int N){
			//your code goes here
            if(N<1){
                return 0;
            }
            return N + NnumbersSum(N-1);
		}
};
```

