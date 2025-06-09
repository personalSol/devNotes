---
status: newBorn
related-links: 
created: 2025-06-06T23:07
updated: 2025-06-06T23:07
---
---

```js
// for single upload
router.route('/update-avatar').patch(
    verify_JWT,
    upload.single("avatar"),
    updateUserAvatar
)

// for multiple files
router.route('/register').post(
    upload.fields([
        {
            name: "avatar",
            maxCount: 1
        },
        {
            name: "coverImage",
            maxCount: 1
        }
    ])
    , registerUser);
```


