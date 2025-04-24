---
status: newBorn
related-links: []
created: 2025-04-22T16:46
updated: 2025-04-23T07:27
---
---


**intro**
- use to update content/variables in a page without reloading the page or using normal DOM
- limitation: state will go to initial value if page reloads
- to use variables inside react, we use `expression or evaluated expression or {}` and write variable inside these curly braces
	![[Pasted image 20250304141710.png]]


## map of hooks:

![[Pasted image 20250423072234.png]]


## types of hooks:

- state management hooks:

````tabs
--- useState

Link: [useState – React](https://react.dev/reference/react/useState#adding-state-to-a-component)

- syntax: `const [state, setState] = useState(initialState)`
- setState: used to set new value to state
- **Two Update Styles**:
    - **Direct**: `setState(newValue)` → Replaces state.
    - **Functional**: `setState(prev => prev + 1)` → Uses previous state.
- **Initial Value**: Set once on first render (`useState(0)` → 0 is initial).
- **Async**: Updates batched; state doesn’t change immediately.
		- can check it by immediately logging state
		- but it does update which we can see on the second `console.log`
		- preState is like .then in promise. the next one works when the previous one completes
- **Batching**: Multiple `setState` calls in same event → merged.
	- **Reset on Reload**: State is in-memory → reload = reinitialize.
	- **Persist State**: Use `localStorage`/backend to save across reloads.

- it is prefered that we change or update the value of state directly inside setState and not first update it and then load it.

extras: [[Hooks - setState]]


````


	

# Reference
`related tags + notes + source + link(if any)`
 
- [[tG not-tagged]]
- 