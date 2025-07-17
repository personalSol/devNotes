---
status: newBorn
related-links: 
created: 2025-07-14T13:07
updated: 2025-07-14T19:25
---
---

> all these three only work on sorted containers

### binary search
- only works on sorted things
- return true if exist else false


### lower_bound
- returns the address/iterator of element if we found
	- that's why we have to subtract the start address or iterator
- otherwise give the address of immdiate next element


### upper_bound
- returns the address/iterator of the next element if it founds the element we are searching
- same for if not found then gives the address of next bigger element



![[cpp - code block#code for binary search upper_bound lower_bound]]
