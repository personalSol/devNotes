---
status: newBorn
related-links: 
created: 2025-06-24T16:31
updated: 2025-07-25T00:39
---
---

> so basically if we have input component created somewhere else but we want to take it's value in the main component after importing it then we can't by using ref hook directly because it will point to the component and not the input html tag inside it. and we can't use ref.current.focus() to get the input value
 > 
> so to solve this react came up with forward reference or in short `forwardRef` with this we can use ref in out main component and pass `ref` as a prop which will directly give us refernce of input tag inside it
> 
> we can also use another simiple prop to do the work but if we want to specifically pass ref as prop then we have to use `forwardRef`

 
- [[react forwardRef explaination]]


