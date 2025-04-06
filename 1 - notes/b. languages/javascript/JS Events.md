---
status: newBorn
related-links:
  - "[[JavaScript-MOC]]"
  - "[[Javascript Cheatsheet]]"
created: 2025-02-24T19:26
updated: 2025-02-24T23:24
---
---

- basic ^j3wtkf
	- can add multiple event listeners to one element
	- add using `addEventListener()` method
	- can easily remove an event listener by using the `removeEventListener()` method
	- `e` stores all the details around the event
		- one of the details is e.target which holds data around the element which triggered the event

A simple example idhar could be a ul and you applied 'click' event on ul. Now jab bhi koi li inside that ul will be clicked, the even will trigger. But to know which li triggered the event. We can use e.target.tagName ( which gives the tag name in caps ) or e.target.id ( if the target element had any id )

```javascript
document.querySelector('#task-list').addEventListener('click', function(e){
    if(e.target.tagName == 'SPAN'){
        e.target.parentNode.remove();
    } else if(e.target.tagName == 'LI'){
        e.target.setAttribute('class', 'checked');
    }
})
```

REMEMBER: event variable e and e.target are different. target is a part of data that gets stored inside e

akar if you want to check all the elements that get storied inside e then log e as a result of an event occuring.







# Reference
`related notes + source + link(if any)`
 
