---
status: newBorn
related-links: 
created: 2025-06-02T11:11
updated: 2025-06-02T11:11
---
---

full code example of using **Multer** that demonstrates:

- `dest` usage (default disk storage)
- `diskStorage` with dynamic `destination` and `filename`
- `memoryStorage` for in-RAM processing
- Handling different upload types (`single`, `array`, `fields`)

#### 📁 Folder structure (assumed)
```pgsql
project/
├── uploads/
│   ├── avatars/
│   └── docs/
├── index.js
```

`index.js`
```js
const express = require('express');
const multer = require('multer');
const app = express();

// ========== 1. Simple dest usage (default disk storage) ==========
const simpleUpload = multer({ dest: 'uploads/' });

app.post('/simple-upload', simpleUpload.single('file'), (req, res) => {
  console.log(req.file); // File info with random filename
  res.send('Simple file uploaded');
});

// ========== 2. Custom diskStorage ==========
const diskStorage = multer.diskStorage({
  destination: (req, file, cb) => {
    if (file.fieldname === 'avatar') {
      cb(null, 'uploads/avatars/');
    } else if (file.fieldname === 'document') {
      cb(null, 'uploads/docs/');
    } else {
      cb(null, 'uploads/'); // default fallback
    }
  },
  filename: (req, file, cb) => {
    const timestamp = Date.now();
    const originalName = file.originalname;
    cb(null, `${timestamp}-${originalName}`);
  }
});

const customUpload = multer({ storage: diskStorage });

app.post('/custom-upload', customUpload.fields([
  { name: 'avatar', maxCount: 1 },
  { name: 'document', maxCount: 2 }
]), (req, res) => {
  console.log(req.files); // Each field's files
  res.send('Custom files uploaded');
});

// ========== 3. Memory storage ==========
const memoryUpload = multer({ storage: multer.memoryStorage() });

app.post('/memory-upload', memoryUpload.single('file'), (req, res) => {
  console.log(req.file.buffer); // File stored in RAM
  res.send('Memory upload done (not saved to disk)');
});

app.listen(3000, () => {
  console.log('Server running on http://localhost:3000');
});
```


> [!summary] summary
> |Route|Purpose|Storage|
|---|---|---|
|`/simple-upload`|Basic file upload with `dest`|Default disk|
|`/custom-upload`|Dynamic folder & name via `diskStorage`|Custom disk|
|`/memory-upload`|Stored in memory (RAM)|Memory storage|
