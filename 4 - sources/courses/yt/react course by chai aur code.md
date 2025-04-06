---
created: 2025-03-03T21:10:27
status: 
source: 
updated: 2025-03-25T17:58
---
---

## till hooks

- npx is node package executer which allows us to execute package without installing them
- to use variables inside react, we use `expression or evaluated expression or {}` and write variable inside these curly braces in html code
	![[Pasted image 20250304141710.png]]
- 


#### ways to create a react app

- `npx create-react-app 01basicreact`: 
	- not used anymore
	- very bulky and have things that we might not require in every project
	- in this when we run build script through `npm run dev`
		- the build file that gets created is the file which browser recieves at the end
	- this package json comes from creating react app method 
	![[Pasted image 20250303211314.png]]
	here two main libraries are react and react dom. 
	- jest is used for testing
	- vitals is used for track things like speed an all in wesbite
- `npm create vite@latest`:
	- only installs react and react-dom library
	- fast compared to create-react-app

- react is used to mostly create SPAs ( single page applications ) as we don't want our website to load.
- just like browser create DOM of website, react also creates its own DOM which it updates and updating this DOM doesn't require us to render entire dom tree again. this react dom is called virtual dom
- react pages by default are not very SEO friendly because the contents load in them at last minute through virtual DOM of react
- when we create components, we make it in .jsx
- 




**Conventions to follow:**
- if you are creating a component which return html tags then it's best to name that file with .jsx and name start with capital letter.  
- also the function to start with capital letter
	- this convention is important because it helps us differentiate components from actual html elements as html elements are written in small letter.
- vite without these conventions give error and CRA doesn't give error but doesn't work without capital name function


#### react understanding
---
basically what react does is we create function which returns html.

those function are then imported to main.jsx and there all these functions get rendered inside a root div where all it's data gets stored. which then shows up on page

#### react methods
---


````tabs
--- createElement
```javascript
const reactEl = React.createElement(
  "a",
  { href: "https://www.google.com" },
  "chick here",
  evaluated_expression
);
```
all these three parameters are required.


````


#### **Why State Resets on Reload:**

- React state is **temporary** and stored in your browser’s memory (RAM) _while the app is running_.
- Reloading the page **clears the memory** and restarts the app, resetting all state to their initial values.



#### hooks
---
````tabs

--- Intro

- used to update content/variables in a page without reloading page or using normal DOM
- limitation: the state will go back to inital state if we refresh the page

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


#### terminologies
---

````tabs
--- eval express
evaluated expression: it is the expression which is evaluated. Means it doesn't have any computation to do. it's just like a variable only.

--- Fragements
the open and close tags without anything which are used to enclose multiple elements are called fragements

````



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

![[Recording 20250304163338.m4a]]


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

