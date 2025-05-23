---
status: newBorn
related-links:
  - "[[React-MOC]]"
created: 2025-04-25T16:07
updated: 2025-05-23T09:01
---
---

- built-in prop in react
	- helps distinguising one component from another
	- often used with lists ( like generating same type of element or componen using loop like map )
	- it can be a:
		- unique string
		- unique number
	- sometimes used with map function
		- if you have a unique item then you can that
		- if not you can use index

```jsx

//with unique value
import React from 'react';

function ItemList() {
  const items = [
    { id: 1, name: 'Apple' },
    { id: 2, name: 'Banana' },
    { id: 3, name: 'Cherry' }
  ];

  return (
    <div>
      {items.map(item => (
        <Component key={item.id} />
      ))}
    </div>
  );
}

function Component({ key }) {
  return <div>Component with key: {key}</div>;
}

export default ItemList;


// without unique value

{items.map(item, index) => {
	<div key={index}>{item}</div>>
}	
}
```


# Reference
`related tags + notes + source + link(if any)`
 

- 