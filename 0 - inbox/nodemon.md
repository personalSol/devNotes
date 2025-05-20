---
status: newBorn
related-links: 
created: 2025-05-20T10:00
updated: 2025-05-20T10:00
---
---

Why: Whenever we updata data in the server then we have to restart the server to see changes. Nodemon solves this problem.

Instead of running the file/server on node, we can run it on nodemon.

After running the server to stop it, we press **CTRL + C**

## Code

- install
    ```java
    npm i nodemon -g //this will install this globally which I don't want
    npm i nodemon // it's good enough.
    ```
- to run
    ```java
    nodemon <filename> // nodemon alone sometimes face permission problems so we can't run it directly
    npx nodemon <filename> // however we can use npx to run nodemon.
    ```
    - `nodemon app.js` would **not work** in the terminal or command line because we don't use local dependencies there but global packages. means:
    - in cmd we use global packages and as we have installed nodemon on our project only it’s a local dependency and not global package
    - What we can do is we can update our start script instead of node `<filename>` to nodemon `<filename>` and this will search for nodemon locally and it will find it and run it.

