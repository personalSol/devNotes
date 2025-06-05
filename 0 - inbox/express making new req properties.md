---
status: newBorn
related-links: 
created: 2025-06-05T15:30
updated: 2025-06-05T15:30
---
---

- it's very easy to make a new property in a middlware
- you can just write 
```js
req.name = something // and then use it.
```
- you can also pass it to another function by using router and next. just make sure that before that function in which you need that property, you run the middleware and then next.
- we did it in auth user verification before login in chai aur code backend series