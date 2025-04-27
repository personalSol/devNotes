---
created: 2025-04-23T07:23:07
status: adult
source: 
updated: 2025-04-26T15:18
---
---

- Components
	- building blocks of our react app
	- makes all the visible parts of out app
	- infinite rereusability
	- react components are javascript functions which returns markup
		- but they are not html mark ups
		- react functions return **jsx** which which underthehood is js
- jsx
	- jsx is optional but then we will have to use DOM. `createElement()`, `removeElement()`, etc which makes the code messy and is annoying to write
	- in this we write things in camelCase because it's js and not html
	 - html is static while jsx is dynamic
- curly braces
	- we can show dynamic data in react using curly braces
	- this is JSX syntax, which allows you to embed JavaScript expressions inside your JSX
	- anything inside these braces is treated as JavaScript
	- **Second set of curly braces `{}`**: This is the JavaScript object itself, where you define the CSS properties and their values as key-value pairs.
- fragement
	- js functions can return only one thing
	- so if we try to return multiple elements then we get errors
	- to solve this we have fragements `<> </>`
	- we can also cover them in div but we can use fragement if we don't want to add extra element
- props or properties
	- allows us to pass data into another component
	- props is basically an object which contain properties that we can access with `.`
	- we can also pass another component as a prop -- [[react props]]
	- properties  
		- steps
			1. make prop and give value: `<Greetings text={'Yo'}`
			2. use the prop (code below)
	- helps in composition
- composition : means organising our react components in most optimal way
- key prop - [[ react -  key prop]]
- **Rendering** = Create new Virtual DOM
- **Reconciliation** = Diffing **+** Updating the Real DOM
- State
	- like a snapshot of our app at any given time
	- can't use variables to store state as it doesn't make app re-render
	- we use special functions like 
		- useState()
		- useReducer()
- Controlled Components
	- perfect for forms
	- uses state value to have controlled behaviour
	- in this, when we put value in form
	- it gets stored in state variable and then we use setVariable to update the value
	- steps:
		- user types, setValue gets called
		- state gets updated
		- finally we read the updated state
	- great pattern to use as if we want to change the behaviour of component we just have to change it's state
- 5 main types of hook
	1. state hooks : helps manage state within react component
		- `useState()` ⭐
		- `useReducer()`
	2. Context hooks : lets us use data pass through `useContext()`
	3. ref hooks : like `useRef()` lets us reference things like html element ⭐
	4. effect hooks: like `useEffect()` lets us connect with external components like browser,  api, etc ⭐
	5. performance hooks : improves performance by preventing unnecessary work
		- `useMemo()`
		- `useCallback()`
- purity 
	- means a react component with same input should always return the same output
	- conditions
		- only return jsx
		- should not change any stuff that existed before rendering
- strict mode
	- to prevent errors, tells us about mistake in our components
	- gives us warning in console
	![[Pasted image 20250426151837.png||500]]
- effects
	- use when we want to interact with outside
	- effect is code that helps us reach outside of our react app
	- these effects are called side effects
	- best done in event handlers
	- ex: to submit an http request on form submission or click on a button
	- writing side effect without hook
		- we can write side effects without useEffect() hook too but it will cause problems
		- React might re-render your component many times, even for small changes
		- it could lead to:
			- Slow things down
			- Cause bugs
			- Do weird stuff when you have many components
	- using hook is better because:
		- it waits until the component is _done showing_, then do the side job
- ref
	- when we want to step out of react and interact with real DOM, we use ref hooks
	- we can't use DOM directly as change in structure can beak the app
	- we can directly use ref prop on any element to target it directly
	- Refs **don’t trigger re-renders** if they change
	- you use `.current` to get the actual thing it’s pointing to
- context - [[ react - context]]
- portals
	- portals are like context but for components
	- portals let us move react component into any html element we select
	- portals are perfect for components that can't be displayed properly becuase of their parent component style
	- ex: ![[Pasted image 20250426142312.png||400]]
	- ![[Pasted image 20250426142339.png||450]]
- suspense
	- special component
	- helps handle loading of component or it's data
	- ![[Pasted image 20250426142543.png||450]]
	- ![[Pasted image 20250426142629.png||450]]
	- it shows a dummy component until the real component loads with data
	- useful for lazily loading a component : means only loading the data when needed
	- ![[Pasted image 20250426142749.png||450]]
- error boundaries
	- react is basically js, errors that happen during rendering can break our app
	- error boundaries are used to catch app breaking error and show a fallback to use to show what happen
	- ![[Pasted image 20250426143114.png]]
	- ![[Pasted image 20250426143150.png]]





```jsx

// component : returns jsx and not html mark ups
function App() {
		  return (
		    <>
		      <h1>hello</h1>
		    </>
		  );
		}

// jsx : writing camelCase as it's not html
<h1 class="heading">HELLO</h1> // ❌
<h1 className="heading">HELLO</h1> ✅


// curly braces
	const planet = "Earth";
	<div>Hello {planet}</div>
	
	const src="/react.svg";
	<img src={src} />
	
	const background = 'red';
	<div style={{color: 'white'}} />
	<div style={{background}} /> 
	// here we are using two curly braces because style attribute expects a js object


//fragements : returning multiple elements using it
return (
	<>
		<h1 style={{color:'red', background: 'black'}}>HELLO</h1>
		<h2>WORLD</h2>
	</>
)

// -------------------------- props --------------------------
<Greetings text={'yo'} />;
function Greetings(props){
	return <h1> {props.text}</h1>
}

// ------------------------ controlled forms ------------------

import React, { useState } from 'react';

function SimpleInput() {
  const [inputValue, setInputValue] = useState(''); // State to hold the input value

  const handleChange = (event) => {
    setInputValue(event.target.value); // Update state with the new input value
  };

  return (
    <div>
      <input 
        type="text" 
        value={inputValue} // Controlled by state
        onChange={handleChange} // Update state on change
      />
      <p>You typed: {inputValue}</p> {/* Display the current input value */}
    </div>
  );
}

export default SimpleInput;

// uncontrolled form

import React, { useRef } from 'react';

function MyUncontrolledForm() {
  const inputRef = useRef(null);

  const handleSubmit = (event) => {
    event.preventDefault();
    alert('Input value: ' + inputRef.current.value); // Accessing value directly
  };

  return (
    <form onSubmit={handleSubmit}>
      <input type="text" ref={inputRef} /> {/* No value prop, uncontrolled */}
      <button type="submit">Submit</button>
    </form>
  );
}


// ----------- impure and pure components

let count = 0;
function cup(){
	count = count + 1; 
	return <h1> Cup {count} </h2>
}
// this will return the cup number in increasing order each time we run this

// ---------strict mode -----------

import {StrictMode} from 'react';

<StrictMode>
	<App />
</StrictMode>


// ------- side effects -----------

import { useState, useEffect } from "react";

function ClickCounter() {
  const [count, setCount] = useState(0);

  // This is the side effect
  useEffect(() => {
    document.title = `You clicked ${count} times`;
  }, [count]); // It runs every time count changes

  return (
    <div>
      <p>You clicked the button {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me!</button>
    </div>
  );
}

// what we should do is

function MyComponent() {
  document.title = "Hello"; // ❗ Bad idea

  return <h1>Hi</h1>;
}


// we can also use event handler

import { useState } from "react";

function ClickCounter() {
  const [count, setCount] = useState(0);

  const handleClick = () => {
    const newCount = count + 1;
    setCount(newCount);
    document.title = `You clicked ${newCount} times`; // ✅ fine here
  };

  return (
    <div>
      <p>You clicked the button {count} times</p>
      <button onClick={handleClick}>Click me!</button>
    </div>
  );
}


// --------- refs ----------

import { useRef } from "react";

function FocusInput() {
  const inputRef = useRef(null);

  const handleClick = () => {
    inputRef.current.focus(); // 🪄 Directly focus the input box
  };

  return (
    <div>
      <input ref={inputRef} type="text" />
      <button onClick={handleClick}>Focus the input</button>
    </div>
  );
}




```


# Reference
`related link(if any)`
[Every React Concept Explained in 12 Minutes - YouTube](https://youtu.be/wIyHSOugGGw?si=Oefb7j0uFgbIS5tz)
