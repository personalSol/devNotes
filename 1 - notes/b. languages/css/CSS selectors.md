---
status: newBorn
related-links:
  - "[[CSS-MOC]]"
created: 2025-03-19T17:21
updated: 2025-04-11T10:45
---
---

there are total of 5 types of selectors

1. simple selectors: 5 types
	types are:
	- id: `#`
		- there is only one id in each element
		- it's unique to that element only
	- class: `.`
		- used to target multiple elements at same time
		- a simple element can also have multple classes separated by space
	- element: `tagName`
		- works on all tags in that document
	- group: `,`
		- to combine and target different ids or class together, we use group selector
	- universal: `*`
2. combination selector: 4
	- decendant: (empty space)
		- targets all child elements inside the parent element
		- if `section div` is there then all the divs inside section will be targeted
	- child: >
		- only target immediate childs
	- adjacent: + 
		- only target the first element after that tag
		- `section+div` will target only first immediate div if that is there
	- general: ~
		- works on all tags after closing of that tag
3. psuedo class: 5 - 6 
	1. Link: used to target links which are not visited
	2. Visited: to target link which we have not visited
	3. Hover: when we hover
	4. Active: when we click then to target for that specific point
	5. first-child
	6. last-child
	7. nth-child
	8. first-of-type
	9. last-of-type
	10. nth-of-type
	link visited and active are used for anchor tag. active can also be used for button
	hover can be used at many places
4. psuedo elements: 5 - 6
	1. . First Letter
	2. First Line
	3. Before
	4. After
	5. Selection
	6. Marker
5. attribute: 7 // not very imp and can be skipped


# Reference
`related tags + notes + source + link(if any)`
 

- 