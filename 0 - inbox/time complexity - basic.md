---
status: newBorn
related-links: 
created: 2025-07-17T15:19
updated: 2025-07-17T15:19
---
---

**Definition:** _Time complexity_ is a measure of how the running time of an algorithm grows as the size of the input increases. ^dcei01


Ex: finding sum of number till "n"
possible ways:
1. using a loop till n and adding i in a variable
	- time complexity of Big O Notation O(n)
2. using formula n * ( n+1 )/2 <- standard formula derived from {n/2 * (2a + (n-1) * d)} 
	- will have O(1) time complexity

### what we don't do

- measuring time in absolute value
	- like time complexity of this code is 18 sec.
- reason:
	- because the execution time will be different for different:
		- Devices
		- Programming Languages
		- Set of Inputs

and so on...

### how we calculate:

We know the worse the time complexity, the more time the code takes to execute given the same input.

So, given:
- constraints
- time limit of a problem

we'll have to calculate:
- the worst-case time complexity our code

to get better time complexity, we must find:
- good algorithm 
	- that pass all test cases


### rules for TC

- always measure it in worst case scenario
	- reason: prepare for worst and to generally keep in mind that our system will be scalable
- avoid constants
	- means avoid fix numbers, imagine a code with big time complexity and then you are also adding small numbers. Those numbers will be insignificant so we don't add them to reduce the complexity of code
- avoid lower values
	- we also avoid lower power values like `O(4n^3 + n^2)`
	- here we will avoid n^2 as it's not that significant


### different methods to measure

- upper bound or worse case
	- measured in Big-Oh
- average complexity
	- measured in theta
- lower bound or best case
	- measured in Omega



