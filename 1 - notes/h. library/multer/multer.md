---
status: newBorn
related-links: 
created: 2025-06-01T23:11
updated: 2025-07-18T22:45
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
- [[multer req.files vs req.file]]
- [[multer uploading single vs multiple files]]
- 
- to keep the extension with the file name, we have two ways
	- keep the file name original using `file.originalname` inside cb in diskStorage
	- extract the file extension using [[1 - notes/h. library/path#to get file extension]]
- 