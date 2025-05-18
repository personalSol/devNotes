---
status: newBorn
related-links:
  - "[[Express - MOC]]"
  - "[[express methods]]"
created: 2025-05-17T12:26
updated: 2025-05-17T12:26
---
---


- flow of program in detail
    it is a complete example showing how static files work with Express, focusing on the request flow.
    - code
        ```jsx
        // File structure:
        // project/
        //   ├── server.js
        //   ├── views/
        //   │   └── home.ejs
        //   └── public/
        //       └── css/
        //           └── style.css
        
        // server.js
        const express = require('express');
        const path = require('path');
        const app = express();
        
        // Set up static middleware
        app.use(express.static('public'));
        
        // Set up EJS
        app.set('view engine', 'ejs');
        
        // Route to render home page
        app.get('/', (req, res) => {
            console.log('1. Received request for homepage');
            res.render('home');
        });
        
        app.listen(3000, () => {
            console.log('Server running on port 3000');
        });
        
        // views/home.ejs
        <!DOCTYPE html>
        <html>
        <head>
            <title>Static File Demo</title>
            <link href="/css/style.css" rel="stylesheet">
        </head>
        <body>
            <h1>Welcome to the Demo</h1>
            <div class="styled-box">
                This box is styled using external CSS
            </div>
        </body>
        </html>
        
        // public/css/style.css
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        
        .styled-box {
            background-color: #f0f0f0;
            border: 2px solid #333;
            padding: 20px;
            margin-top: 20px;
            border-radius: 5px;
        }
        ```

    Here's how the request flow works when someone visits your website:

    1. Initial HTML Request:
        - Browser makes a GET request to `http://localhost:3000/`
        - Express matches the `/` route
        - `res.render('home')` processes the EJS template
        - Server sends back the HTML
    2. CSS Request:
        - Browser receives HTML and starts parsing
        - Browser finds `<link href="/css/style.css">`
        - Browser makes a new GET request to `http://localhost:3000/css/style.css`
        - Without `express.static()`, this second request would fail because Express doesn't know how to handle it
    
    You can verify this flow by watching browser's network tab in DevTools - you'll see two separate requests:

    - First for the HTML page
    - Second for the CSS file
	
	This is why static middleware is so important 
	- it automatically handles that second request for the CSS file
	- Without it, the browser would get a 404 error when trying to fetch the CSS file.

# Reference
`related tags + notes + source + link(if any)`
 

- 