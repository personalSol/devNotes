---
status: newBorn
related-links:
  - "[[React-MOC]]"
created: 2025-04-22T16:46
updated: 2025-06-16T19:47
---
---


**intro**
- use to update content/variables in a page without reloading the page or using normal DOM
- limitation: state will go to initial value if page reloads
- to use variables inside react, we use `expression or evaluated expression or {}` and write variable inside these curly braces
- hooks are basically functions which return something
	![[Pasted image 20250304141710.png]]


## map of hooks:

![[Pasted image 20250423072234.png|||500]]


## types of hooks:

- state management hooks:
	- [[Hooks - useState]]

- effect hooks
	- [[hooks - useEffect]]
	- 
- performance hooks
	- `useCallback()`
		- use to optimize the function and not execute it
		- **memoizes** the function, meaning it creates a new version of the function only when its dependencies change.
		- it only stores the values in cache and not run them
		- it is used for function and prevents it from being recreated and only recreates when one of the dependencies of useCallBack changes
- ref hooks
	- use it when we want to work directly with DOM
	- ![[Pasted image 20250426203121.png]]
	- in this we first import it
	- create a variable and assisiate it to `useRef(<initial_value`) 
	- then we use `ref={variable}` to associate that variable with the element that we write it inside
	- after that we can perform any actions on that element using that variable
- Random hooks
	- useID
		- use to generate random id which can be use.
		- shouldn't be use to generate keys
	- [[react hook - useNavigate]]
	- 



# Reference
`related tags + notes + source + link(if any)`
 

- 