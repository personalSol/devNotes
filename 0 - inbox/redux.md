---
status: newBorn
related-links: 
created: 2025-06-19T19:34
updated: 2025-06-21T02:14
---
---

redux is a js library which helps in state management on JS apps ( not react but any js code)
- it works with other libraries as well like vue etc
- for react, it created a separate library called - react redux
	- redux means managing state in an organized way
- a little history:
	- facebook created flux to solve this state problem
	- but in 2015, came a better solution in a conference which was redux
	- some famous outcomes:
		- never modify or mutate your state
		- all changes should be done through a pure function or `reducer` and not directly
- at last came [[redux toolkit]] with old version [[react redux]]
	- why two and both:
		- ab redux aaya tha to uske stepup me thoda jayada time lagta tha compare to contex api and debugging karne me v problem ja rhi thi. tab developers ne redux-toolkit introduce kiya jisme setUp or debugging easy ho gya kuchh redux functions ke dawara, isliye redux use karne ke liye ye dono libraries install karni jaruri hai.
- for redux with react we have to see
	- store: which basically stores all contexts ( there can be multiple context ) 
	- reducer: (from what i understood) it is the medium through which we modify state in store
		- basically we have multiple mini stores so what will update and how functionality is inside reducer
	- two hooks:
		- useSelector - [[react redux hook useSelector]]
		- useDispatch - [[react redux hook useSelector]]

