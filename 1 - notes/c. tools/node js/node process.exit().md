---
status: newBorn
related-links: 
created: 2025-05-28T03:07
updated: 2025-05-28T03:07
---
---



#### 🔧 What is `process.exit()`?

`process.exit([code])` is a built-in Node.js function that **ends the current process**. You can pass an **exit code** to indicate whether the program completed successfully or encountered an error.

##### 📘 Syntax

```js
process.exit(code)
```

- **`code`** *(optional)*: A number that tells the operating system **why** the process is exiting.
  - Default: `0` if you don’t provide anything.

---

#### 🟢 Common Exit Code Values

| Code  | Meaning                             | Usage                                       |
|-------|-------------------------------------|---------------------------------------------|
| `0`   | Success                             | Everything went fine                        |
| `1`   | General error                       | Catch-all for unspecified errors            |
| `2`   | Misuse of shell builtins (Linux)    | Rarely used in Node                         |
| `127` | Command not found                   | A script tried to run something missing     |
| `126` | Command invoked cannot execute      | Permissions issue or wrong binary           |
| `130` | Script terminated by Ctrl+C         | SIGINT signal                               |
| `137` | Script killed (e.g., out of memory) | SIGKILL or OOM (Linux)                      |

> ✅ **Best Practice:** Use `0` for success and `1` for general errors unless you have a specific convention.

---

#### 🧠 Example: Success vs Failure

```js
if (everythingIsFine) {
  process.exit(0); // Exits with success
} else {
  process.exit(1); // Exits with error
}
```

---

#### ⚠️ Things to Know

- The process **stops immediately**.
- No code after `process.exit()` will run.
- Make sure to **clean up (e.g., close DB, log errors)** before calling it.

---

#### 🧪 Pro Tip: Check exit code from the terminal

If you run a Node script and want to check how it exited:

```bash
node myscript.js
echo $?  # prints the exit code
```



