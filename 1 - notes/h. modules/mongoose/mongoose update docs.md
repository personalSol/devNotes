---
status: newBorn
related-links: 
created: 2025-06-04T09:11
updated: 2025-06-04T09:11
---
---

> case is we want to add new data with data fields in docs of an already existing user

```js
const user = <userModel>.findOne(<condition whatever>)
user.<new_field> = newValue;
await user.save({ validateBeforeSave: false });
```

what is does is:
- create user object
- set new field and value ( it should already be defined in schema )
- save the updated user without validating other fields 

