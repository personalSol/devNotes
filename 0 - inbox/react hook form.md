---
status: newBorn
related-links: 
created: 2025-07-25T01:05
updated: 2025-07-27T02:37
---
---

> hota kya hai ki register directly hamari input value ko apne andar uss value ko save krleta hai with key as the thing we entered inside register as first argument. 
> 
> uske baad hota ye hai ki jaise ki handleSubmit ek wrapper hai jisme register sare inputs ko line see save krdeta hu as elements of an object. and then handle submit woh pass krta hai uss handler function ko jisko humne form submit handle krne ke liye banaya hai
> 
> bas yahi hota hai
> 
> - register values leta hai bina useRef use kre ya onChange use kre
> - and handle submit woh sare data ka object banake hamare form submit wale function ko dedeta hai
> - easy hai thoda
> 
> ye saab maine reach hook form ka docs dekh kr samja


react hook form is kinda simple.
- from it we use useForm
- useForm returns us register and handlesubmit
- register (is an event, idk how ) used to take the data from an element of component
	- register first takes unique name of that data and secondly and object in which we can give properties like
		- `required: true` 
		- validate: it takes a callback function which has value as parameter and validates the value using regex otherwise give a desired string
- handlesubmit is also an event in which we wrap our form submit action function. idk how it works


[[ gpt react hook form explanation]]

