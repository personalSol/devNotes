---
status: newBorn
related-links:
  - "[[react-MOC]]"
created: 2025-04-22T16:08
updated: 2025-04-24T21:54
---
---



**before**
- facebook was facing a problem that they were not able to show notifications and reactions on real time. Everytime they had to reload page to get notifications and reactions because they were using php.

**Problem in detail**: 
- browser have a nature, they refresh the entire DOM tree if there is anything that changes in DOM
	- even if you are doing a simple task of changing color of a button when pressed
- this made browser re-render the entire DOM ( not reload the page )
- this put burden on browser ( like for 1 lakh requests, it will have to refresh 1lakh times) and browser can crash


in 2013, an engineer from fb created a library to solve this problem. The inner working of this library was different


how react solved it:
- React was able to show things in real time
- react have it's own DOM called virtual DOM. So in react whenever any change occured, you didn't have to refresh the entire real dom
- but it changed only the virtual DOM which was the exact copy of real DOM. 
- so whenever we add a change to React Virtual DOM only that part changes and the whole DOM stays the same and doesn't get refreshed



### what, why, how and when

**what:**
- it's a libarary to maintain the front end
- This library works with two environments:
	- **react-dom** for web apps
	- **react-native** for Android (and iOS) apps
**Why**
- efficient and lightweight
- very low page reloads ( unless you specifically have to )
- extreme use of reusable components
- efficient
**when** 
- to create a big level app where we can benefit from reusability


# Reference
`related tags + notes + source + link(if any)`
 

- Source: Sheriyans crash course on react