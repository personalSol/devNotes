---
status: newBorn
related-links:
  - "[[Express - MOC]]"
created: 2025-05-17T10:48
updated: 2025-05-17T12:26
---
---

- `.static()` -- for more detail: [[express static method]]
    - The `static` method in Express is used to serve static files, like images, CSS files, JavaScript, and HTML files, directly from a specified folder
    - useful for web applications that need to serve frontend assets to clients.
    - basically helps us handle browser requests for static file
    ```jsx
    app.use(express.static(path.join(__dirname, "public")));
    ```




# Reference
`related tags + notes + source + link(if any)`
 

- 