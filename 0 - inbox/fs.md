---
status: newBorn
related-links: 
created: 2025-06-02T07:28
updated: 2025-06-02T09:27
---

> The `fs` (Filesystem) module in Node.js allows you to interact with the file system — reading, writing, and updating files.


### 📘 Basic Usage

> [!example]+ Basic `readFile` Usage
> ```js
> const fs = require('fs');
> const path = require('path');
>
> const filePath = path.join(__dirname, 'a.txt');
>
> fs.readFile(filePath, 'utf8', (err, data) => {
>   if (err) {
>     console.log(err);
>   } else {
>     console.log(data);
>   }
> });
> ```

---

### 📚 Methods in FS

> [!note]+ Docs
> 📄 [Node.js FS Documentation](https://nodejs.org/dist/v6.17.1/docs/api/fs.html#fs_fs_readfilesync_file_options)

---

#### 🔹 `fs.readFileSync()`

> [!summary]+ Description
> - **Synchronous**
> - Blocks execution until file is fully read
> - Returns a string (if encoding is specified) or a Buffer
> - No callback; use return value directly

> [!example]+ Code
> ```js
> const fs = require('fs');
>
> let var1 = fs.readFileSync('hello.txt', 'utf8');
> let var2 = fs.readFileSync('hello2.txt', 'utf8');
>
> console.log(var1);
> console.log(var2);
> ```

---

#### 🔹 `fs.readFile()`

> [!summary]+ Description
> - **Asynchronous**
> - Good for small files
> - Syntax: `fs.readFile(filename, encoding, callback)`
> - Callback:
>   - `err`: error info
>   - `data`: file contents

> [!example]+ Code
> ```js
> const fs = require('fs');
>
> function print(err, data) {
>   if (err) {
>     console.log(err);
>   } else {
>     console.log(data);
>   }
> }
>
> fs.readFile('helloo.txt', 'utf8', print);
> ```

---

#### 🔹 `fs.writeFileSync()`

> [!summary]+ Description
> - **Synchronous** write
> - Overwrites if file exists, creates otherwise
> - Returns `undefined`

> [!example]+ Code
> ```js
> const fs = require('fs');
>
> fs.writeFileSync('helloWorld.txt', 'this should be 2nd line');
> ```

---

#### 🔹 `fs.writeFile()`

> [!summary]+ Description
> - **Asynchronous** write
> - Overwrites file content (deletes old, writes new)

> [!example]+ Code
> ```js
> const fs = require('fs');
>
> fs.writeFile('helloWorld.txt', 'New content here', (err) => {
>   if (err) {
>     console.log(err);
>   } else {
>     console.log('File written successfully');
>   }
> });
> ```

#### 🔹 `fs.unlinkSync()`

> [!summary]+ Description
> - this unlinks the file from OS link - [[file unlinking in OS]]
> ```js
> fs.unlinkSync(localFilePath)
>```

