---
status: newBorn
related-links: 
created: 2025-06-14T19:53
updated: 2025-08-15T17:35
---
---
> use to control one axis at a time

- is a flexible box
- use to target child tags of parent element 
- so we set on parents and it gets applied to child

flex and only flex box terminologies
![[Pasted image 20250614223215.png]]

- justify-content - Main Axis ke upar khel sakta hu
	- justify content basically regardless of which axis it is on controls ki kitna space hoga items kee beech mai
- align-items - Cross Axis ke upar khel sakta hu
	- align items regardless of axis controls position kya hogi of content perpendicular to main axis. 

> means akar humko ek vertical sidebar banana hai jisme we want the items to have space between, then we can't use align items to do that because align items is just to set position level ki top pr hoga ya bottom pr hoga ya center, it doesn't set space. and items hamare horizontally hii ayenge flex lagane pr. So here we can set flex-direction to be column. ye batata hai flex ko ki jo items hai woh row items nhi column items ke format mai lagane hai


```css
.sidebar {
  display: flex;
  flex-direction: column; /* Natural flow is top to bottom */
  justify-content: space-between; /* Push top and bottom items apart */
}

.sidebar {
  display: flex; /* main axis = horizontal */
  align-items: space-between; /* ❌ Not even valid — align-items doesn't take space-between */
}
```

when we do `flex-direction: column` then it tilts the thing. justify content still works on main axis but abb main axis ka direction hi change ho gaya hai.
- same goes for cross axis

![[Pasted image 20250615141020.png||500]]