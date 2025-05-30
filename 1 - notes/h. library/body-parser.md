---
status: newBorn
related-links:
  - "[[Node-JS-MOC]]"
  - "[[npm packages]]"
created: 2025-05-28T08:51
updated: 2025-05-28T10:34
---
---


> [!NOTE] Warning
> body parser now comes by default in express so we don't really need to install it

Use:
- helps us parse( or convert ) the data we get to something useful
```jsx
const bodyParser = require('body-parser');
app.use(bodyParser.urlencoded({extended: false}));
```

- 2nd line is a middleware and used like that because it will parse any and all incoming form requests with urlencoded() method

#### `urlencoded() method`

- used
    - used to format data we get in URL which is the default format for form submissions in HTML.
        - both get and post + web api
    - makes it into Js object associated with input name(if any)
- have arguments
    - **`extended: false`**:
        - When set to **`false`**, the **`querystring`** library is used to parse the URL-encoded data. This means that the data will be parsed into a simple key-value object.
        - For example, if the form data is **`username=JohnDoe&age=30`**, it will be parsed into:
            
            ```jsx
            {
              username: 'JohnDoe',
              age: '30'
            }
            ```
            
        - This is suitable for most simple use cases where you just need to extract basic form data.
    - **`extended: true`**:
        - When set to **`true`**, the **`qs`** library is used instead of **`querystring`**. This allows for richer parsing, including support for nested objects and arrays.
        - For example, if the form data is **`user[name]=JohnDoe&user[age]=30`**, it will be parsed into:
            
            ```jsx
            {
              user: {
                name: 'JohnDoe',
                age: '30'
              }
            }
            ```
            
        - This is useful when you need to handle more complex data structures.