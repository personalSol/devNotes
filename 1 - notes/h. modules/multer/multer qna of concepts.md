---
status: newBorn
related-links: 
created: 2025-06-02T11:08
updated: 2025-06-02T14:36
---
---

### ❓ What is Multer?
**Multer** is a middleware for handling `multipart/form-data`, which is mainly used for uploading files in Node.js with Express.

---

### ❓ What is the whole process when uploading a file with Multer?
1. Client sends a request with file(s) via `multipart/form-data`.
2. Multer middleware parses the request.
3. Multer stores the file:
   - On disk (if using `dest` or `diskStorage`)
   - In memory (if using `memoryStorage`)
4. File info is added to `req.file` or `req.files` for further handling.

---

### ❓ Why do we pass `dest` in `multer({ dest: '...' })`?
- `dest` tells Multer **where to store uploaded files**.
- It uses **default disk storage** with random filenames.
- Suitable for simple, non-customized file uploads.

---

### ❓ Do we need to pass `dest` when using `diskStorage()`?
**No.**
- `diskStorage()` allows full control over destination and filename.
- You define the `destination` function inside the storage config, so `dest` becomes unnecessary.

---

### ❓ Does the `destination()` function in `diskStorage` run for every file?
**Yes.**
- It runs for each file being uploaded.
- You can return different folders based on `file.fieldname`, `mimetype`, or other request data.

---

### ❓ What is `memoryStorage` in Multer?
- It stores uploaded files **in RAM** instead of saving to disk.
- Useful when you want to immediately process the file (e.g., upload to cloud).
- ⚠️ Avoid for large files due to memory limitations.

---

### ❓ Do methods like `upload.single()` work with both storage types?
**Yes.**
- `upload.single()`, `upload.array()`, `upload.fields()`, and `upload.none()` work with:
  - `dest`
  - `diskStorage`
  - `memoryStorage`

---

### 🔍 Here's why we don't export `storage` directly:

The `storage` object is just a **configuration** — it's **not usable on its own**.

The real thing you need is the `upload` middleware:

```js
const upload = multer({ storage });
```

This `upload` object is the **Multer middleware function** you can use in your routes like:

```js
app.post('/upload', upload.single('file'), (req, res) => {
  res.send('File uploaded!');
});
```

If you export just the `storage`, you'd still need to wrap it with `multer({ storage })` **again** in every file where you want to use it — which defeats the purpose of centralizing the config.

### ✅ Summary Table

| Question                                          | Answer                                                                 |
|--------------------------------------------------|------------------------------------------------------------------------|
| Use `dest` with Multer?                          | For simple uploads with default settings                              |
| Need `dest` with `diskStorage`?                  | ❌ No, handled via `destination` function                              |
| Does `destination()` run for each file?          | ✅ Yes                                                                 |
| Does `memoryStorage` use RAM?                    | ✅ Yes                                                                 |
| Can `.single()` and `.array()` work with any storage? | ✅ Yes                                                             |



