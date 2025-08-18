---
status: newBorn
related-links: "[[React-MOC]]"
created: 2025-04-25T15:33
updated: 2025-05-23T08:32
---
---


### passing fields as props


#### enclosing method
- without destructuring
```jsx
function Parent(props) {
  return props.children;
}

function App() {
  return (
    <Parent>
      <p>Hello!</p>
    </Parent>
  );
}
```
- here we have passed `p` tag as a children by enclosing it in parent tag


- with destructuring
```jsx
function Parent({ children }) {
  return children;
}

function App() {
  return (
    <Parent>
      <p>Hello!</p>
    </Parent>
  );
}
```


### passing another component as prop

#### direct method


```jsx

// without destructuring
// here we have simply passed another component as a prop in parent component

function Parent(props) {
  const ComponentToRender = props.component;
  return <ComponentToRender />;
}

function Child() {
  return <p>Hello from child!</p>;
}

function App() {
  return <Parent component={Child} />;
}

//with destructuring
function Parent({ component: ComponentToRender }) {
  return <ComponentToRender />;
}

function Child() {
  return <p>Hello from child!</p>;
}

function App() {
  return <Parent component={Child} />;
}

```

#### enclosing method
```jsx
//without destruturing
function Parent(props) {
  return props.children;
}

function Child() {
  return <p>Hello from child!</p>;
}

function App() {
  return (
    <Parent>
      <Child />
    </Parent>
  );
}


// with destructuring
function Parent({ children }) {
  return children;
}

function Child() {
  return <p>Hello from child!</p>;
}

function App() {
  return (
    <Parent>
      <Child />
    </Parent>
  );
}
```

# Reference
`related tags + notes + source + link(if any)`
 

- 