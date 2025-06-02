---
status: newBorn
related-links: 
created: 2025-06-01T23:11
updated: 2025-06-02T11:11
---
---

> best resource: [GitHub - expressjs/multer: Node.js middleware for handling \`multipart/form-data\`.](https://github.com/expressjs/multer#readme)


#### some quick add

```js
// in form
<form action="/profile" method="post" enctype="multipart/form-data">
  <input type="file" name="uploaded_file" />
</form>

// multer: this is to get the file from form into dest
const multer  = require('multer')
const upload = multer({ dest: './public/data/uploads/' })
app.post('/stats', upload.single('uploaded_file'), function (req, res) {
  // req.file is the name of your file in the form above, here 'uploaded_file'
  // req.body will hold the text fields, if there were any
  console.log(req.file, req.body)
});
```


- [[multer qna of concepts]]
- [[multer code]]
