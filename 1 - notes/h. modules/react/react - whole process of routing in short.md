---
status: newBorn
related-links: 
created: 2025-06-16T17:40
updated: 2025-07-29T19:34
---
---

we use: `RouterProvider createBrowserRouter createRoutesFromElements Route Outlet` all from `'react-router-dom'`

- we start with replacing `<App />` form main.jsx strict mode
- we insider `RouterProvider` with a prop router with value router
- then we create this router function same in main.jsx in for which we use `createBrowserRouter`
	- inside this we can directly use array with objects
	- or we can use `createRoutesFromElements()` function
- inside this `createRoutesFromElements()` function we have to create a main `<Route />` with `'/'` which we connects with `<App />` or `<Layout />` or some say `<Root />`
- now inside `<Route path='' element={}` we can enclose more such routes
	- these enclosed routes will be passed as props to `App` 
	- inside this `<App />` we have `<Outlet />` which gets replaced by the prop route elements according to the route we hit

```jsx
// main.jsx
import React from "react";
import {createRoot} from "react-dom/client";
import {createBrowserRouter, Route, RouterProvider, createRoutesFromElements} from "react-router-dom";
import "./index.css";
import App from "./App.jsx";
import Home from "./components/home/Home.jsx";
import About from "./components/about/About.jsx";
import Contact from "./components/contact/Contact.jsx";
import User from "./components/User/User.jsx";
import Github, { loaderDataFetcher } from "./components/Github/Github.jsx";

const router = createBrowserRouter(
  createRoutesFromElements(
    <Route path='/' element={<App/>} >
      <Route path='' element={<Home />} />
      <Route path='about' element={<About />} />
      <Route path='contact' element={<Contact />} />
      <Route path='user/:userId' element={<User />} />
      <Route 
      loader = {loaderDataFetcher}
      path='github' 
      element={<Github />} 
      />
    </Route>  
  )
);

createRoot(document.getElementById("root")).render(
	<React.StrictMode>
		<RouterProvider router={router} />
	</React.StrictMode>
);

```