---
created: 2025-04-23T07:23:07
status: 
source: 
updated: 2025-04-25T18:36
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




```


# Reference
`related link(if any)`
[Every React Concept Explained in 12 Minutes - YouTube](https://youtu.be/wIyHSOugGGw?si=Oefb7j0uFgbIS5tz)
