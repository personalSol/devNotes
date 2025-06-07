---
status: newBorn
related-links: 
created: 2025-06-06T15:44
updated: 2025-06-06T15:44
---
---

### req.files (Multiple Files)

- Used when `multer` is configured to handle multiple files
- Returns an object with arrays of files
- Structure looks like this:

```js
req.files = {
    avatar: [
        {
            fieldname: 'avatar',
            originalname: 'profile.jpg',
            encoding: '7bit',
            mimetype: 'image/jpeg',
            path: 'path/to/file',
            size: 12345,
            // ...other metadata
        }
    ],
    coverImage: [
        {
            fieldname: 'coverImage',
            originalname: 'cover.jpg',
            // ...similar properties
        }
    ]
}
```

- That's why we use `req.files.avatar[0].path`

### req.file (Single File)

- Used when `multer` is configured for single file upload
- Returns a single file object directly
- Structure looks like this:

```js
req.file = {
    fieldname: 'avatar',
    originalname: 'profile.jpg',
    encoding: '7bit',
    mimetype: 'image/jpeg',
    path: 'path/to/file',
    size: 12345
    // ...other metadata
}
```

- That's why we use `req.file.path` directly

### example config

```js
// For multiple files
const upload = multer().fields([
    { name: "avatar", maxCount: 1 },
    { name: "coverImage", maxCount: 1 }
])

// For single file
const upload = multer().single('avatar')
```