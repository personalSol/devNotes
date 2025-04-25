---
created: 2025-03-03T21:10:27
status: 
source: 
updated: 2025-04-25T11:21
---
---




#### **Why State Resets on Reload:**

- React state is **temporary** and stored in your browser’s memory (RAM) _while the app is running_.
- Reloading the page **clears the memory** and restarts the app, resetting all state to their initial values.



#### hooks
---





#### folder structure:
---
- for react the main file we have is `index.html` in CRA public folder.
	- one thing we can notice is that we are not injecting any js file in this index.html but JS is still coming.
	- we can check js by doing view page source and we can see there that the script comes probably comes from `react-scripts` dependencies
	- again this makes CRA heavy
- for veet, index.html is out and have js imported so no scripts needed hence saving it from getting heavy unnecessrily 


---


### other things that I need to know:

- inspect and page source are two diffferent things

## virtual dom, reconcillation and fibre


previouslu react's core algorithm was used but react-fibre is something that has stuff like proritize, add, abort requests. And now react-fibre is the core algorithm behind creating virtual DOM.

reconcilliation: or we can say reconsidering is something like thinking again that I should complete this request or abort and work on the updated request that came after this.

**reconciliation**: The algorithm React uses to diff one tree with another to determine which parts need to be changed.

##### analogy i created to understand this
---
here teacher -> browser
higher ups -> user request
class arrangement -> page render through DOM




##### fibre

a primary goal of Fiber is to enable React to take advantage of scheduling. Specifically, we need to be able to

- pause work and come back to it later.
- assign priority to different types of work.
- reuse previously completed work.
- abort work if it's no longer needed.


## props + tailwind - variables

- in tailwind 4.0 it assumes that you already have a react project and just want to install tailwind in it.
- in jsx we use className to put tailwind classes inside a file as `class` word is already reserved

how tailwind works:
- first we install tailwind
- then we config it in vite.config.js file
- then at last we import tailwind in the css file we want to use it in 

## Props or variables in component:

props means properties: which means passing data from parent to child
- to pass values in props
	- we write the component name and then the prop name which is equal to curly braces with data inside which we want to pass.
	- `<ClrButton updatedColor={"black"} setBgClr={setColor} />`
- to declare and use props in component
	- in component, 
		- we declare the props in function parameter + pass default value if there is any
	- to use it we pass the props/variable inside curly braces `{}`
		- if we are already inside curly braces ( like when we are inside double curly braces in style ) then we don't have to use curly braces again

```js
const ClrButton = ({ updatedColor, setBgClr }) => {
  return (
    <>
      <button
        onClick={() => setBgClr(updatedColor)}
        className="text-white rounded-full p-2 m-2"
        style={{ backgroundColor: updatedColor }}
      >
        {updatedColor}
      </button>
      <br />
    </>
  );
};
```


# to use css inside react

- to use css inside jsx, we use `style` attribute with double curly braces ( using double curly braces is syntax)
- we can use variables inside directly now as we are already inside curly braces
```jsx
<div style={{backgroundColor: variable}}> </div>
```


# onClick

remember that in js, onclick requires reference of functiona and to pass value in function we can directly use arrow function like this
`onClick={() => setBgClr(updatedColor)}`
# Reference
`related link(if any)`

