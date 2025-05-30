---
status: newBorn
related-links:
  - "[[React-MOC]]"
created: 2025-03-03T18:32
updated: 2025-05-22T18:21
---
---

- used to mostly create SPAs ( single page applications ) as we don't want our website to load.
- **component**: is basically a function which is returning JSX ( literally returning using return keyword ). we make them in `.jsx`
- **JSX**: is basically a react file in which we can write html like code. 
	- Behind the scene it gets converted into DOM code which then manages DOM.
	- ex: `<h1>hey</h1>` inside react will convert to `React.createElement('h1') and then (i am guessing this part) but here .innerHTML = 'hey'`
- virtual dom: just like real dom which browser creates
	- react creates it's own dom
	- when any changes come, it compares that with the previous virtual dom
	- and only renders the updated part
	- this doesn't require page to reload
- **eval express**: evaluated expression: it is the expression which is evaluated. Means it doesn't have any computation to do. it's just like a variable only.
- **Fragements**: `<> </>`
	- helps exporting multiple things

**Cons of react**
- pages are not seo friendly as their content renders on last minute through virtual dom


to run server in terminal: npm run dev

**Ways to style react:**
- module css
- tailwind css -- best and easy
- material UI

# Reference
`related tags + notes + source + link(if any)`
 
a
- 