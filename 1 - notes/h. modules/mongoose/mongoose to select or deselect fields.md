---
status: newBorn
related-links: 
created: 2025-06-03T17:46
updated: 2025-06-03T17:46
---
---

> User is model. `user` is saved data + stored. 
> `.select()` in this we use `-` before field to deselect it ( very similar to obsidian search )


- the reason we don't select directly is we want to save the data. and this updated user is what we will give to client/user himself


```js
const user = await User.create({
        username: username.toLowerCase(),
        email,
        fullName,  
        avatar: avatar.url,
        coverImage: coverImage?.url || "",
        password
    })

const updatedUser = await User.findById(user._id).select(
        "-password -refreshToken"
    )
```

