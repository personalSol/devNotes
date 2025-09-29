---
status: newBorn
related-links:
created: 1970-01-01T05:30
updated: 2025-09-28T19:13
---
---

- python in backend creates a byte code file
- this byte code ( .pyc ) file is then run on PVM ( python virtual machine )
- this process happens automatically and most of the time python delets the byte code ( mostly when we run top level file means we are not importing from any other file )
- when we import from other files then python creates and saves these byte code files in folder called `__pycache__` 
- also byte code obviously runs faster than normal python script
- byte code is not machine code or assembly code and is only optimized to run through PVM and cannot be run directly or through tools like `JVM`
- in python shell if we want it to reload an imported file on the go without closing the shell and opening it again and then importing then we can use a funciton called `reload(<module name which we want to reimported>` from `importlib` module.

