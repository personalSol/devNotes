---
status: newBorn
related-links: 
created: 2025-06-16T15:45
updated: 2025-06-16T18:49
---
---
 
![[Pasted image 20250426142009.png||450]]
- it's written in a js file
- in 1st part, we have to export the AppContext before we can use it
	- can really use any name instead of `AppContext`
- in the provider when we use value like in 3rd
	- if it's a dynamic value then we obviously use `{}` to evalaute them
	- and if we are passing multiple values then we can use a normal js object and set multiple values inside it which we can then destructure when we import them using `useContext()`
	- in `useContext()` we have to tell it which context we want to use in out component and that's why we pass value inside it 




![[Recording 20250616183748.m4a]]

