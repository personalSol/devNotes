---
status: newBorn
related-links:
  - "[[CSS-MOC]]"
created: 2025-03-24T16:54
updated: 2025-05-23T08:27
---
---

units are of two types
- absolute
- relative

px - absolute

relative:
- vh/vw: changes according to viewport
	- vh - applied to height
	- vw - applied to width
- %: changes according to parent element
- em: 
    1em = 16px
    - **Relative to the font-size of the **parent** element.**
    - If a parent element has a font size of `20px`, then `1em` inside that element equals `20px`.
- rem
    - 1rem = 16px
    - **Relative to the font-size of the **root** element (`<html>`).**
    - `1rem` is always based on the root font size, regardless of nesting.



body tag doesn't have height by default because of infinite scroll.

body tag does have width which is equal to viewport
because body tag doesn't have defined height that's why if we apply percent to it's child then it doesn't work.



extra:

we can't give height and width to inline elements



# Reference
`related tags + notes + source + link(if any)`
 

- 