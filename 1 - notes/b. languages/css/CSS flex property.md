---
status: newBorn
related-links:
  - "[[CSS Cheatsheet]]"
  - "[[CSS-MOC]]"
created: 2025-02-22T22:07
updated: 2025-02-24T23:33
---
---
in css, the `flex` property is a shorthand property for:
best explaination: [The most popular Flexbox property explained in 4 Minutes \| CSS flex shorthand - YouTube](https://youtu.be/ZOK-DU7vT0A?si=MUjbBHkJGRGSon_w)
- flex-grow
- flex-shrink
- flex-basis

![[Pasted image 20250222221006.png|400]]


default values: 
![[Pasted image 20250222221939.png|400]]


### flex-grow

if the container has items and space then flex-grow will make sure items grow in size enough to fill the container so there wouldn't be empty space anymore. Yani ki akar ek dabbe mai 4 item hai and jagha 6 ki hai toh `flex-grow: 1` krne see woh 4 items jyada space leke pura container full kredenge jaha 6 ki jagha thi.


### flex-shrink

when we want elements to be responsive we use flex-shrink: 1. this shrinks the box if space decreases.

we change it to 0 to have an element not shrink. 

### flex-basis

ye basically help krta hai in making elements take equal space if set to 0. `flex-basis: 0` means minimum width but with `flex-grow: 1` it takes the remaining space so somehow they all get equal space


question: mujhe ye samaj nhi aya ki akar woh minimum space lee bhi rahe hai toh bhi jo element bada hoga woh jyada minimum space lega naa....
# Reference
`related notes + source + link(if any)`
 
