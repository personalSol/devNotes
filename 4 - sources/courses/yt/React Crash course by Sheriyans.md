---
created: 2025-02-26T06:51:12
status: 
source: youtube video
updated: 2025-02-26T17:44
---
---

Objective: 
- learn to code on react
- skilled enough to give coding interview


### Whole story


 **before**
- facebook was facing a problem that they were not able to show notifications and reactions on real time. Everytime they had to reload page to get notifications and reactions because they were using php. in 2013, an engineer from fb created a library to solve this problem. The inner working of this library was different


**Problem in detail**: 
- browser have a nature, they refresh the entire DOM tree if there is anything that changes in DOM
	- even if you are doing a simple task of changing color of a button when pressed
- this made browser re-render the entire DOM ( not reload the page )
- this put burden on browser ( like for 1 lakh requests, it will have to refresh 1lakh times) and browser can crash



how react solved it:
- React was able to show things in real time
- react have it's own DOM called virtual DOM. So in react whenever any change occured, you didn't have to refresh the entire real dom
- but it changed only the virtual DOM which was the exact copy of real DOM. 
- so whenever we add a change to React Virtual DOM only that part changes and the whole DOM stays the same and doesn't get refreshed




what - js library to maintain the front end efficiently
why - efficient and lightweight
- very low page reloads ( unless you specifically have to )
- extreme use of reusable components
- efficient
how - create components, and make data if you need it, link the data and change data whenever you want, react will react jab bhi data change hogq
when - jab qqko ek thodq bade level par app create karna ho, jjsme.in khoob saari Gheeie.in ho rabi hai, and khoob saara reusable component structure hai



### code part

**component**: is basically a function which is returning JSX ( literally returning using return keyword )

**JSX**: is basically a react file in which we can write html like code. Behind the scene it gets converted into DOM code which then manages DOM.

ex: `<h1>hey</h1>` inside react will convert to `React.createElement('h1') and then (i am guessing this part) but here .innerHTML = 'hey'`


to run server in terminal: npm run dev

**Ways to style react:**
- module css
- tailwind css -- best and easy
- material UI


# Reference
`related link(if any)`
[ReactJs Crash Course: Master the Basics in One Video! Ignite Your Front-End Mastery Series! - YouTube](https://youtu.be/Xe8CkYZvCig?si=757vVjRs1o4hPxXc)
