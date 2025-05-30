---
status: newBorn
related-links:
  - "[[Core-Concepts-MOC]]"
created: 2025-02-12T18:47
updated: 2025-05-09T20:14
---
---

## Basic

Just like in time complexity, we don't measure space complxity of a program as this code takes 50kb or 100kb as the absolute space required by a code depend on multiple factors, input being one of them

**Definiton:** _Space complexity_ measures how the memory/space required by an algorithm grows as the size of the input increases ^kzlek3


- also gets written in O(value) format
- sum of 
	- auxilary space + input space
	- auzilary space: space you take to solve the problem
	- input space: space that you take to store the input
> ![[Pasted image 20250509201128.png]]

- here a and b are input space and c is auxilary space


### rules

- never touch/modify/tamper the input data unless necessary
	- example
		- to save space you write `b = a + b` instead of `c = a + b`. 
		- this might save space but you never know in a big software where else was b used so you want to avoid doing that


Example of time complexity:
- 100 number are given individually, we are to find sum of all 100 numbers.

Algorithms:
1. take input of all the numbers in variables and then performing a sum operation
	- space complexity of this algo is O(N). N here being number of inputs.
2. take 1st input and then when you get the second input, immediately add them and store the final value and erase the 1st and 2nd input ( kinda similar to how mind works ) and then after reciving 3rd input adding that to final value and storing new final value and deleting the 3rd.
	- space complexity of this algo will be O(1) as we are only storing final value.




## Reference
`related notes + source + link(if any)`
 
